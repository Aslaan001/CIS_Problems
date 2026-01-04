## Title  
Confidential Information Spread Simulation  

## Slug  
confidential-information-spread-simulation  

## Difficulty  
Medium  

## Description  

An organization is monitoring how confidential information spreads among its members over time.

On day 1, exactly one person becomes aware of a confidential piece of information.

Each person who knows the information follows these rules:

- A person starts sharing the information with exactly one new person per day, beginning delay days after the day they first learned it.
- A person forgets the information forget days after the day they first learned it.
- A person cannot share the information on the day they forget it or on any day after that.

You are given three integers n, delay, and forget.

Your task is to determine how many people still know the confidential information at the end of day n.

Since the number of people can grow very large, return the result modulo 10^9 + 7.

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
Day 2: No new sharing occurs.  
Day 3: The first person shares the information with one new person.  
Day 4: The first person shares the information again.  
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
