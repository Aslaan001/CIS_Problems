## Title

Luna’s Cookie Heist


## Slug

luna-cookie-heist

## Difficulty

Medium

## Description

In the magical kingdom of `Sweetopia`, Luna is tasked with collecting all the enchanted cookies from `n jars` before sunrise.  
Each jar contains a certain number of magical cookies, and Luna can only collect a limited number of cookies per hour due to the jars’ magical restrictions.  

Luna can decide her `collection speed 's'`, which is the number of cookies she can take from a single jar in `one hour`. Her routine works like this:

- Each hour, she picks `any jar` she likes.  
- She collects up to `s` cookies from that jar.  
- If the jar contains fewer than `s` cookies, she takes all remaining cookies in that jar and stops collecting for that hour.  

Luna wants to `collect all cookies` within `h` hours. Your task is to determine the `minimum collection speed 's'` that allows her to finish the job in time.  


## Examples

### 1

#### Input

4
3 6 7 11
8

#### Output

4

#### Explanation

At speed `s = 4`:

- Jar 1: 3 cookies → 1 hour  
- Jar 2: 6 cookies → 2 hours  
- Jar 3: 7 cookies → 2 hours  
- Jar 4: 11 cookies → 3 hours  

Total hours = 1 + 2 + 2 + 3 = 8 hours, which fits exactly in the limit.  
Any speed lower than 4 would exceed 8 hours.

### 2

#### Input

5
30 11 23 4 20
5

#### Output

30

#### Explanation

There are 5 jars and 5 hours.  
To finish each jar in 1 hour, Luna must take all cookies from each jar in that hour.  
Thus, the minimum collection speed must be equal to the largest jar, which is 30.


## Input Format  

- First line: integer `n` — the number of cookie jars.  
- Second line: `n` space-separated integers `cookies[i]` — the number of cookies in each jar.  
- Third line: integer `h` — the total number of hours before sunrise.  

## Output Format  

Return a single integer — the `minimum collection speed 's'` that allows Luna to collect all cookies in `h` hours.  



## Constraints  

- 1 ≤ n ≤ 1e4  
- n ≤ h ≤ 1e9   
- 1 ≤ cookies[i] ≤ 1e9  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

binary-search, arrays. 
