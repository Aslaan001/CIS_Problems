## Title

Circular Dial Command Execution

## Slug

circular-dial-command-execution

## Difficulty

Hard

## Description

A control room uses a circular mechanical dial to execute secure command sequences for activating restricted systems.  
The dial is engraved with lowercase English letters arranged in a circular order, represented by a string called `ring`.

To execute a command, an operator must input a command sequence represented by another string called `key`.

Initially, the dial is positioned so that the `first character of the ring is aligned at the reference marker (12:00 position)`.

The operator must execute the command sequence character by character using the following operations:

- The dial can be rotated clockwise or anticlockwise by one position, and each such rotation costs one step.
- To execute a character `key[i]`, the dial must be rotated until a matching character from the ring is aligned at the reference marker.
- Once aligned, the operator presses the execution button, which also costs one step.
- After pressing the button, the dial remains in its current orientation for executing the next character.

Your task is to determine the `minimum number of steps` required to execute the entire command sequence.

It is guaranteed that the given command sequence can always be executed using the provided dial.

## Examples

### 1

#### Input

godding  
gd

#### Output

4

#### Explanation

The first command character `g` is already aligned, so only one step is needed to press the button.  
For the next character `d`, the dial is rotated anticlockwise by two positions and then the button is pressed.

Total steps required are 4.

### 2

#### Input

godding  
godding

#### Output

13

## Input Format

- First line: string `ring` representing the circular dial  
- Second line: string `key` representing the command sequence  

## Output Format

- Return a single integer representing the minimum number of steps required to execute the full command sequence

## Constraints

- 1 ≤ length of `ring`, `key` ≤ 100  
- Both strings contain only lowercase English letters  
- The command sequence can always be executed using the dial

## Time Limit

1 second

## Memory Limit

512 MB

## Company

deshaw

## Tags

dynamic-programming, string  
