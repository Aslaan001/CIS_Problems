## Title
Synchronized Nicknames for the Twin Scribes

## Slug
synchronized-nicknames-for-the-twin-scribes

## Difficulty
Hard

## Description
Two young scribes, who happen to be twins, have names written entirely in uppercase letters.  
The elder scribe is named A, containing N characters.  
The younger scribe is named B, containing M characters, with the guarantee that N ≤ M.

You want to give each scribe a special nickname:

- The elder scribe’s nickname A′ may be any permutation of the characters in A.  
- The younger scribe’s nickname B′ must be obtained by taking any permutation of B, then removing exactly M − N characters, keeping the relative order of the remaining characters.

Thus, B′ will have exactly N characters.

However, the nicknames must obey a special synchronization rule.  
For every position i (1 ≤ i ≤ N):

B′ᵢ must be equal to either A′ᵢ  
or the alphabetical successor of A′ᵢ (if such a next letter exists).

Your task is to determine:  
How many distinct pairs of nicknames (A′, B′) can satisfy this rule?  
Two pairs are considered different if at least one nickname differs.  
Since the number can be large, output it modulo 998244353.

## Examples

### 1
#### Input
3 4  
AMA  
ANAB

#### Output
9

### 2
#### Input
5 8  
BINUS  
BINANUSA

#### Output
120

## Input Format
- First line: integers N and M  
- Second line: string A of length N  
- Third line: string B of length M  
All characters are uppercase English letters.

## Output Format
Return a single integer — the number of valid nickname pairs (A′, B′) modulo 998244353.

## Constraints
1 ≤ N ≤ M ≤ 200000  
All strings contain only uppercase letters.

## Time Limit
1 second

## Memory Limit
1024 megabytes

## Tags
dynamic-programming, hackwithinfy

## Company
infosys
