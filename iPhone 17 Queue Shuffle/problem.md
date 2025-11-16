## Title

iPhone 17 Queue Shuffle

## Slug

iphone-17-queue-shuffle

## Difficulty

Easy

## Description

The highly anticipated iPhone 17 lineup has just launched, and a long line of eager customers has formed outside the Apple Store. Everyone expects to be served in the order they arrived — the first person in line should buy first.

Suddenly, the store opens a new counter, but it is placed exactly at the position where the last person in line is standing. If the process starts directly from there, the last customer would unfairly get served first.

To maintain fairness, the store decides to reverse the last k people in the queue before sending them to the new counter. This way, their original arrival order is preserved, and no one who arrived later gets served before someone who came earlier.

Your task is to update the queue by reversing the last k elements, while keeping the first n - k elements unchanged.

If the number of people (n) is smaller than k, the queue remains unchanged.

## Examples

### 1
#### Input

q = [1, 2, 3, 4, 5], k = 3

#### Output

[1, 2, 5, 4, 3]

#### Explanation

The last 3 people [3, 4, 5] would be served unfairly if left as is (since 5 would go first). Reversing them to [5, 4, 3] restores fairness. Final queue: [1, 2, 5, 4, 3].

### 2
#### Input

q = [10, 20, 30, 40], k = 2

#### Output

[10, 20, 40, 30]

#### Explanation

The last 2 people [30, 40] are reversed into [40, 30], so 30 still gets served before 40 at the new counter.

## Input Format

- First line contains an integer n — the number of people in the queue.

- Second line contains n space-separated integers representing the queue elements (q[0] is the front, q[n-1] is the rear).

- Third line contains a single integer k, the number of people at the end of the queue to reverse.

## Output Format

Return the queue after reversing the last k elements, keeping the first n - k unchanged.

## Constraints

- 1 ≤ q[i] ≤ 10^5

- 1 ≤ n ≤ 10^5

- 1 ≤ k ≤ 10^5

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

queue
