## Title  
Confidential Information Spread Simulation  

## Slug  
confidential-information-spread-simulation  

## Difficulty  
Medium  

## Description  

An organization wants to simulate how confidential information spreads among its members over a period of time.

On day 1, exactly one person knows the confidential information.

When a person learns the information on some day X, they follow a fixed set of rules:

- The person does not share the information immediately.  
- They start sharing the information after delay days, which means they can first share on day X + delay.  
- Once sharing starts, the person shares the information with exactly one new person per day.  
- The person forgets the information after forget days, which means they forget it on day X + forget.  
- On the day they forget the information, and on all days after that, they cannot share the information.  

So, a person is allowed to share the information only during the time period:

From day X + delay to day X + forget - 1

Every new person who learns the information follows the same rules independently, causing the information to spread over multiple days.

You are given three integers n, delay, and forget.

Your task is to calculate how many people still remember the confidential information at the end of day n.

Since the number of people can become very large, return the answer modulo 10^9 + 7.

## Examples  

### 1  

#### Input  
6  
2  
4  

#### Output  
5  

#### Explanation  

Day 1: One person knows the information.  
Day 2: No sharing happens because the waiting period is not complete.  
Day 3: The first person shares the information with one new person.  
Day 4: The first person shares again with another new person.  
Day 5: The first person forgets the information, while another person shares it.  
Day 6: Two people share the information, resulting in five people knowing it.  

### 2  

#### Input  
4  
1  
3  

#### Output  
6  

#### Explanation  

Day 1: One person knows the information.  
Day 2: The information is shared with one new person.  
Day 3: Two people share the information with two new people.  
Day 4: One person forgets the information, while others continue sharing.  

## Input Format  

- The first line contains an integer n — the total number of days.  
- The second line contains an integer delay — the number of days before a person starts sharing.  
- The third line contains an integer forget — the number of days after which a person forgets the information.  

## Output Format  

Return a single integer — the number of people who know the information at the end of day n, modulo 10^9 + 7.

## Constraints  

2 ≤ n ≤ 1000  
1 ≤ delay < forget ≤ n  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

dynamic-programming, queue
