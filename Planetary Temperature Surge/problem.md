## Title

Planetary Temperature Surge

## Slug

planetary-temperature-surge

## Difficulty

Medium

## Description

On the planet Mars, scientists are monitoring a sequence of temperature readings recorded around the planet’s equator. Since Mars rotates continuously, the readings form a circular pattern, meaning the last reading is followed again by the first.

For each temperature reading, scientists want to determine when the next higher temperature will occur as they move clockwise around the planet. If no higher temperature appears even after a full rotation, the scientists record -1 for that reading.

Your task is to assist the research team by identifying, for every temperature reading, the value of the next greater temperature in the circular sequence.

## Examples

### 1
#### Input

temperatures = [1, 2, 1]

#### Output

[2, -1, 2]

#### Explanation

The first reading (1) finds its next higher temperature as 2.

The second reading (2) has no greater value ahead, so it gets -1.

The last reading (1) wraps around and finds the next greater temperature as 2 again.

### 2
#### Input

temperatures = [1, 2, 3, 4, 3]

#### Output

[2, 3, 4, -1, 4]

#### Explanation

Each temperature finds the next greater one ahead, except 4, which has none.

The final reading (3) wraps around and encounters 4 again, making it the next greater temperature.

## Input Format

A single line containing an integer array nums, where each element represents a temperature reading.

The sequence is circular, i.e., after the last reading, the sequence continues again from the start.

## Output Format

Return an array of integers, where the ith value represents the next greater temperature for nums[i].

If no greater temperature exists, return -1 for that position.

## Constraints

- 1 ≤ temperatures.length ≤ 10⁴

- -10⁹ ≤ temperatures[i] ≤ 10⁹

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

array, stack, monotonic-stack