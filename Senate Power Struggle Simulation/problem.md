## Title  
Senate Power Struggle Simulation  

## Slug  
senate-power-struggle-simulation  

## Difficulty  
Medium  

## Description  

A fictional senate is composed of members from two opposing factions: Alpha and Beta.

The senate is voting on a critical policy change using a round-based decision process. Each senator belongs to exactly one faction.

The voting procedure follows these rules:

- The process runs in rounds, and in each round senators act in the original order from left to right.
- A senator who still has voting rights may perform exactly one action when their turn comes.
- A senator may revoke the voting rights of one opposing senator. A revoked senator loses the right to act in the current and all future rounds.
- If, at any point, all remaining senators with voting rights belong to the same faction, any one of them may immediately declare victory and end the process.

You are given a string senate where each character represents the faction of a senator:

- 'A' represents the Alpha faction  
- 'B' represents the Beta faction  

All senators are assumed to act optimally in favor of their own faction.

Your task is to determine which faction will ultimately declare victory.

Return "Alpha" or "Beta" accordingly.

## Examples  

### 1  

#### Input  
AB  

#### Output  
Alpha  

#### Explanation  

The first senator belongs to Alpha and revokes the voting rights of the second senator.  
Only Alpha senators remain, so Alpha declares victory.

### 2  

#### Input  
ABB  

#### Output  
Beta  

#### Explanation  

The first senator from Alpha revokes one Beta senator.  
The remaining Beta senator then revokes the Alpha senator.  
Only Beta senators remain, so Beta declares victory.

## Input Format  

- A single line containing a string senate representing the factions of senators.

## Output Format  

Return a single string — "Alpha" or "Beta" — indicating the winning faction.

## Constraints  

1 ≤ senate.length ≤ 10000  
senate[i] is either 'A' or 'B'  

## Time Limit  

1 second  

## Memory Limit  

512 MB  

## Tags  

queue. 
