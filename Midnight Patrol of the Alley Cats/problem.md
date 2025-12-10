## Title
Midnight Patrol of the Alley Cats

## Slug
midnight-patrol-alley-cats

## Difficulty
Hard

## Description
Every night, a caretaker walks along a long alley consisting of n numbered checkpoints.

There are m stray cats living in the alley.  
Each cat roams only during a specific part of the night:  
cat i can be found from checkpoint li to checkpoint ri, inclusive.

Whenever the caretaker reaches a checkpoint, they may choose to place food there.  
All cats currently present at that checkpoint immediately eat the food.  
However, each cat must be fed at most once — giving food to a cat twice will upset it and end the patrol immediately.

The caretaker wants to feed as many different cats as possible during the night.  
To do this, they must decide on a set of distinct checkpoints where food will be placed, ensuring that:

• No cat's roaming interval contains more than one chosen checkpoint, and  
• The total number of cats that receive exactly one meal is maximized.

Your task is to compute the highest number of cats that can be fed safely.

## Examples

### 1
#### Input
15 6  
2 10  
3 5  
2 4  
7 7  
8 12  
11 11

#### Output
5

### 2
#### Input
1000 1  
1 1000

#### Output
1

## Input Format
A line with integers n and m  
m lines follow, each with two integers li and ri describing the roaming interval of a cat.

## Output Format
Return the maximum number of cats that can be fed exactly once without violating the constraints.

## Constraints 
1 ≤ n ≤ 10⁶  
1 ≤ m ≤ 2⋅10⁵  
1 ≤ li ≤ ri ≤ n  
Sum of all n across test cases ≤ 10⁶  
Sum of all m across test cases ≤ 2⋅10⁵

## Time Limit
3 seconds

## Memory Limit
512 megabytes

## Tags
Dp, hackwithinfy

## Company
infosys.
