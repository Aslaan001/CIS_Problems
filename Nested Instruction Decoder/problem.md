## Title

Nested Instruction Decoder

## Slug

nested-instruction-decoder

## Difficulty

Medium

## Description

A backend processing system stores compressed execution instructions as a single encoded string to reduce transmission size between services.

Each instruction follows a specific encoding rule:

k[segment]

Where:
- `segment` is a sequence of lowercase alphabetic instructions.
- `k` is a positive integer indicating how many times the segment should be expanded.
- Encoded segments may be nested within each other.

The decoding process works as follows:
- When a number is encountered, it applies only to the immediately following bracketed segment.
- The content inside brackets must be fully decoded before repetition.
- All brackets are guaranteed to be well-formed.
- Digits appear only as repeat counts and never as part of instruction text.

You are given a single encoded string `s` representing the compressed instruction sequence.

Your task is to return the fully decoded instruction string after expanding all encoded segments according to the rules.

It is guaranteed that the final decoded string will not exceed a length of 100000 characters.

## Examples

### 1

#### Input

3[a]2[bc]

#### Output

aaabcbc

#### Explanation

- `3[a]` expands to `aaa`
- `2[bc]` expands to `bcbc`
- Final result is `aaabcbc`

### 2

#### Input

3[a2[c]]

#### Output

accaccacc

#### Explanation

- Inner segment `2[c]` becomes `cc`
- Outer segment `3[a2[c]]` becomes `accaccacc`

### 3

#### Input

2[abc]3[cd]ef

#### Output

abcabccdcdcdef

#### Explanation

- `2[abc]` expands to `abcabc`
- `3[cd]` expands to `cdcdcd`
- Remaining `ef` is appended as-is

## Input Format

- A single string `s` representing the encoded instruction sequence

## Output Format

- Return a single string representing the fully decoded instruction sequence

## Constraints

- 1 ≤ length of `s` ≤ 30
- `s` consists only of lowercase English letters, digits, and square brackets
- All repeat counts are in the range 1 to 300
- The decoded output length will not exceed 100000

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

string

## Company

snapchat