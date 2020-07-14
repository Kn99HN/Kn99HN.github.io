---
title: "CDCL Algorithm"
date: 2020-06-03T22:04:13-04:00
draft: false
---

# Formal Verification

I had the fortunate to carry out an independent study with Dr. Wies about formal verification starting this Spring. I found the field quite interesting. Some might call it "glorfied testing" but I think there are some interesting aspect to the field. 

Formal verification is about using mathematical proof to verify the correctness of a program. With any program, procedure or function, we can define a "contract" which must be upheld each time an user use said program.

By using Hoare logic, which is made up of pre-condition, command and post-condiction, we can express the correctness of a program. 

## Conflict Driven Clause Learning (CDCL)

CDCL algorithm is one of the most powerful algorithm used to implement some of the fastest SAT solvers out there. It is based on [DPLL](https://en.wikipedia.org/wiki/DPLL_algorithm) algorithm, which is another SAT algorithm. 

Both utilize heuristic strategy, which assign randomly a boolean value to each variable in CNF (conjunction normal form) formula. CNF refers to conjuction of disjunction, i.e (x1 || x2) && (x3 || ~x1).

Both use the backtracking strategy. In DPLL, the backtracking scheme is to revert back a level and changing the boolean value assigned at that level. For CDCL, the backtracking scheme is more sophisticated. It uses clause learning to aid in the understanding of the backtracking level.

## CDCL Idea

We assume the input is a CNF formula, which is a set of disjunction.

Each variable have these properties:
- Name
- Value
- Antecedent (The clause at which the variable is implied)

A variable can be assigned False, True or Unassigned. 

So, while there are unassigned variable in the formula, we decide to choose a random literal in the clause and also assign it a randomly boolean value.

We then carry out unit propagation. Unit propagation sounds scarry but I think the concept can be explained as this. But first, let's define what is an unit clause. Unit clause is a disjunction clause such that there exist only one variable that is undefined and the rest is False. Unit propagation, in this case, will find this unit clause if there is one and force assign the undefined literal the appropriate truth value such that the clause become True.

Carrying out propagation can certainly conflict because we might contradict another clause in the formula. This is where the backtracking kicks in. To do so, we use a graph, specifically called an Implication Graph. It is a acyclic directed graph. The only special thing about it is that the edge now contains the antecedent, i.e the clause at which a node is arrived at. For instance, if we have a clause x1 || x3. We assign x1 to be False. We then, by unit propagation, can conclude that x3 must be True. By doing so, we have a graph with vertices: x1, x3 and edges x1 => x3 with antecedent is 1.

We use a dummy node k to indicate if we have arrive at a conflict. If so, we make a cut, which is sometimes called UIP, which leads to the conflict. We then can identify the clause that leads to a contradiction. We then negate the clause and find the appropriate level to "backtrack". I called it "backtrack" because it is not similar to "backtracking" I think about in algorithm. It's more similar to removing the nodes in the graph that leads to the conflict and changing truth value of the correct literal.

By repeatedly doing so, we can guarantee that the formula either is SAT or UNSAT by finding if a model exists.

## My implementation

I want to write down my implementation in this blog post so that if I go back from the future, I might recognize any mistake and optimize on it.

### Step 1: Parsing
We first parse the CNF in the file format.

We store the CNF as a dictionary with the key being the index for the clause. This will make our lives easier in the future when processing them adding to the implication graph.

The value of the dictionary is a set of literal. For the literal, we will store them as a Node object, which has the following properties:
- Name
- Value
- Decision Level
- Antecedent
- Negation

### Step 2: Unit Propagation
We now need to create lots of helper function and when I say lots, I mean it. 

```
decide(formula) 
```
Take in the formula and deciding for the literal that is not assigned the value False/True.

```
update_formula(node, formula)
```
Since we sometimes decide on a literal but then hasn't update all its occurences in the formula. This function take the node and formula, updating them accordingly.

```
has_unassigned(formula)
```
Check if there are still unassigned variable in the formula.

```
check_unit(formula)
```
Check if there is any unit clause in the formula. If there is, we return the index in the dictionary. If there is a conflict, we would also return the conflict node. Otherwise, return unresolved.

```
unit_prop(formula, graph, dl)
```
Unit Propagation. We first check if there is any unit clause in the formula. While there is an unit clause in the formula, we then update the unassigned literal in the unit clause to be True. We also have a levels dict, keeping track of the literals assigned at each levels. The forced variable, one which we assign True, is then added to the implication graph. 

### Step 3: Analyze Conflict
Analyze Conflict also requires quite a few helper function. So here are the one we need to define:

```
last_assigned_lit(d, levels)
```
Return the last literal assigned at level d, using levels dict. We then remove it from the list.

```
resolve(first, second, value)
```
Resolving two clauses. The idea is that if x | ~x is in the same clause then they are resolved, meaning their truth value is always True.

```
asserting_level(clause)
```
Once we got the conflict clause, we would need to assert its level. If it is an unary clause then we return 0. Otherwise, we get the second highest level in the clause and it will be the level we need to backtrack to.

```
sole_lit_at_level(s,clause,d)
```
Check if in a clause, if there is a literal which decision level is d. Only one can be in the clause.

```
analyze_conflict(formula, graph, conflict_node, levels)
```
The conflict node will act as our main star here. We get the clause antecedent of the conflict node. while there is no single literal at decision level d, which the conflict node occurs, in the conflicting clause, then we continue. Otherwise, we return the level and the clause we found.

### Step 4: Backtrack
Once we have set up all the helper functions. Backtrack should be easy.

```
backtrack(formula, graph,dl)
```
Given the decision level where we need to change. We un-assign all literals whose decision level is above the conflicting decision level. We then also delete all the un-assigned nodes in the graph. For the node at the decision level, we negate its value.

### Step 5: Putting it together - Conflict Driven Clause Learning
```
CDCL(formula)
```
While the formula containing unassigned literal, we will increment the decision level and decide on the node. Then, while unit propagation leads to conflict, we will analyze conflict and backtrack accordingly.

Once we are done with the outer most while loop, we return True. If the decision level of the conflict node is less than 0, we return False.

## Summary 
One of the most trickiest things of the algorithm is consistency. When we parse, we will have both ~x and x. Then we have to keep track of them in the graph as well. Hence, sometimes, the logic can seems like spaghetti code trying to updating all the occurence of a newly assigned literal. 

Additionally, analyzing conflict is quite complicated and I believe not all literatures outline how to implement it. However, the three most important pieces for CDCL implementation is:
- Implication Graph
- Analyze Conflict
- Unit Propagation

Once you got the three working and a good consistency in your algorithm, you should be able to put it all together.
