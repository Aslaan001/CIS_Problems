## Title

Strategic Resource Allocation Duel

## Slug

strategic-resource-allocation-duel

## Difficulty

Medium

## Description

Two senior analysts are competing in a strategic resource allocation simulation used by enterprises to evaluate decision-making under constraints.

The system provides a list of non-negative integers, where each integer represents the value of a resource unit arranged linearly in a secured pipeline.

The analysts take turns allocating resources, with Analyst A starting first. Initially, both analysts have a total allocation value of 0.

At each turn, the active analyst must choose exactly one resource unit from either end of the pipeline (the first or the last available unit). Once selected, that unit is permanently removed from the pipeline, and its value is added to the analyst’s total allocation score.

The simulation continues until all resource units have been allocated.

Both analysts are assumed to make optimal decisions at every step, aiming to maximize their own total allocation value.

Your task is to determine whether Analyst A can secure a win.

A win is defined as:
- Analyst A having a strictly higher total allocation value than Analyst B, or
- Both analysts ending with equal total allocation values (in this case, Analyst A is still considered the winner due to first-move priority).

This problem models real-world competitive optimization scenarios such as budget allocation strategies, supply chain prioritization, and adversarial decision systems.

## Examples

### 1

#### Input

3
1 5 2

#### Output

NO

#### Explanation

Analyst A can start by choosing either 1 or 2.  
Regardless of this choice, Analyst B can then select 5, gaining a decisive advantage.

At the end of the simulation, Analyst B’s total allocation exceeds Analyst A’s, so Analyst A cannot win under optimal play.

### 2

#### Input

4
1 5 233 7

#### Output

YES

#### Explanation

Analyst A begins by selecting 1.  
No matter whether Analyst B chooses 5 or 7, Analyst A will then be able to select 233.

This guarantees Analyst A a higher total allocation value by the end of the simulation, resulting in a win.

## Input Format

- A single integer array nums representing resource unit values arranged linearly

## Output Format

- Return true if Analyst A can win the simulation  
- Return false otherwise

## Constraints

- 1 ≤ nums.length ≤ 20  
- 0 ≤ nums[i] ≤ 10^7  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

dynamic-programming

## Company

snapchat
