## Title  
Queue-Based Ticket Processing Time  

## Slug  
queue-based-ticket-processing-time  

## Difficulty  
Medium 

## Description  

A service center operates a single ticket counter where customers stand in a queue to purchase service tickets.

There are n customers in the queue, indexed from 0 to n − 1. Customer 0 is at the front of the queue, and customer n − 1 is at the back.

You are given a 0-indexed integer array tickets of length n, where tickets[i] represents the total number of tickets the ith customer wants to purchase.

The ticket purchasing process follows these rules:

- Each customer takes exactly 1 second to purchase one ticket.
- A customer can buy only one ticket at a time.
- After purchasing a ticket, if the customer still needs more tickets, they immediately move to the end of the queue.
- If a customer has purchased all required tickets, they leave the queue permanently.

You are also given an integer k, representing the initial position of a specific customer in the queue.

Your task is to calculate the total time required for the customer initially at position k to complete purchasing all of their tickets.

## Examples  

### 1  

#### Input  
3  
2 3 2  
2  

#### Output  
6  

#### Explanation  

The initial queue is [2, 3, 2], and the target customer is at index 2.

At each second, the front customer buys one ticket and either moves to the back or leaves the queue.

After 6 seconds, the customer who started at position 2 finishes purchasing all tickets.

### 2  

#### Input  
4  
5 1 1 1  
0  

#### Output  
8  

#### Explanation  

The initial queue is [5, 1, 1, 1], and the target customer is at index 0.

Other customers finish earlier and leave the queue, while the target customer continues buying tickets.

After 8 seconds, the customer at position 0 completes their purchases.

## Input Format  

- The first line contains an integer n — the number of customers in the queue.  
- The second line contains n space-separated integers representing the number of tickets each customer wants to buy.  
- The third line contains an integer k — the index of the target customer.  

## Output Format  

Return a single integer — the total time taken for the target customer to finish buying tickets.

## Constraints  

1 ≤ n ≤ 1000  
1 ≤ tickets[i] ≤ 1000  
0 ≤ k < n  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

queue, array  
