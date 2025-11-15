## Title  
Minimum Ticket Expense for Planned Journeys  

## Slug  
minimum-ticket-expense-for-planned-journeys  

## Difficulty  
Medium  

## Description  

You are organizing a set of train journeys within a year. The specific days you plan to travel are given as an array days, where each element represents a calendar day number between 1 and 365.  

There are three types of tickets available, each valid for consecutive travel days:  
- A 1-day ticket costs costs[0] units,  
- A 7-day ticket costs costs[1] units,  
- A 30-day ticket costs costs[2] units.  

When you buy a ticket, it remains valid for its duration starting from that day.  
For instance, purchasing a 7-day pass on day 10 will allow travel from day 10 through day 16.  

Your goal is to determine the minimum total amount of money needed to cover all the planned travel days.  

## Examples  

### 1  

#### Input  
6  
1 4 6 7 8 20  
2 7 15  

#### Output  
11  

#### Explanation  
- Buy a 1-day ticket on day 1 for 2 units (covers day 1).  
- Buy a 7-day ticket on day 3 for 7 units (covers days 3 to 9, including 4, 6, 7, and 8).  
- Buy another 1-day ticket on day 20 for 2 units.  
Total expense = 2 + 7 + 2 = 11.  

### 2  

#### Input  
12  
1 2 3 4 5 6 7 8 9 10 30 31  
2 7 15  

#### Output  
17  

#### Explanation  
- Buy a 30-day ticket on day 1 for 15 units (covers days 1 through 30).  
- Buy a 1-day ticket on day 31 for 2 units.  
Total expense = 17.  

## Input Format  

- The first line contains an integer n — the number of days you plan to travel.  
- The second line contains n space-separated integers representing the travel days.  
- The third line contains three integers representing the cost of each ticket type: 1-day, 7-day, and 30-day.  

## Output Format  

Return a single integer — the minimum possible total cost to cover all travel days.  

## Constraints  

- 1 ≤ n ≤ 365  
- 1 ≤ days[i] ≤ 365  
- days is strictly increasing  
- costs.length = 3  
- 1 ≤ costs[i] ≤ 1000  

## Time Limit  
1 second  

## Memory Limit  
256 MB  

## Tags  
dynamic-programming, cost-optimization, planning, scheduling  
