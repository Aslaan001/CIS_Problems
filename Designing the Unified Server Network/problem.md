## Title
Designing the Unified Server Network

## Slug
designing-the-unified-server-network

## Difficulty
Hard

## Description
A technology company is planning to deploy a large-scale cluster computing system made up of multiple servers arranged in a line.  
Each server operates using a specific database protocol, represented by a positive integer.

At the beginning, all servers are isolated and cannot communicate with each other.  
The company’s objective is to establish connections between servers so that, in the final configuration, every server can communicate with every other server, either directly or through intermediate servers.

To build the network, you may add connections between pairs of servers.  
When you choose to connect server u and server v (with u < v), the cost of creating this connection is determined as follows:

- Consider the protocol values of all servers from index u to index v (inclusive).
- Compute the greatest common divisor (gcd) of these protocol values.
- The cost of the connection is exactly this gcd value.

Your task is to carefully choose which connections to establish so that:
- All servers become part of a single connected network.
- The total cost of all connections is minimized.

Return the minimum possible total cost required to fully connect the server cluster.

## Examples

### 1
#### Input
3  
4 2 6  

#### Output
4  

#### Explanation
One optimal strategy is to connect the servers in a way that ensures full connectivity while minimizing the sum of gcd-based connection costs.

### 2
#### Input
6  
2 4 6 7 14 21  

#### Output
5  

#### Explanation
It is possible to connect all servers using connections whose costs are small (for example, cost 1), achieving full connectivity with a total cost of 5.

## Input Format
- The first line contains a single integer n — the number of servers.
- The second line contains n positive integers p1, p2, …, pn, where pi denotes the protocol type of the i-th server.

## Output Format
Return a single integer — the minimum total cost required to connect all servers so that every server can reach every other server.

## Constraints
- 2 ≤ n ≤ 2 × 10^5  
- 1 ≤ pi ≤ 10^9  

## Time Limit
1 second

## Memory Limit
256 megabytes

## Tags
maths, hackwithinfy

## Company
infosys
