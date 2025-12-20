## Title

Word-wise Anagram Enumeration

## Slug

word-wise-anagram-enumeration

## Difficulty

Hard

## Description

A document processing system stores text as a sequence of words separated by single spaces. To support advanced linguistic analysis and indexing, the system needs to determine how many distinct rearrangements of the text are possible under specific constraints.

You are given a string `s` consisting of one or more words. Each pair of consecutive words is separated by exactly one space character.

A string `t` is considered a valid anagram of `s` if and only if:
- `t` has the same number of words as `s`
- For every word position `i`, the `i`-th word in `t` is a permutation of the `i`-th word in `s`

The order of words must remain unchanged. Only the characters within each word may be rearranged independently.

For example:
- `"acb dfe"` is a valid anagram of `"abc def"`
- `"def cab"` is not valid because the word order is changed
- `"adc bef"` is not valid because individual words are not permutations of the originals

Your task is to compute the total number of **distinct** valid anagrams of the given string `s`.

Since the result can be very large, return the answer modulo `1000000007`.

## Examples

### 1

#### Input
too hot

#### Output
18

#### Explanation

The word `"too"` has 3 characters with one repeated character, resulting in 3 distinct permutations.
The word `"hot"` has 3 unique characters, resulting in 6 distinct permutations.

Total anagrams = 3 × 6 = 18

### 2

#### Input
aa

#### Output
1

#### Explanation

The word `"aa"` has only one distinct permutation.

## Input Format

- A single line containing the string `s`

## Output Format

- Return a single integer representing the number of distinct valid anagrams of `s`, modulo `1000000007`

## Constraints

- 1 ≤ length of `s` ≤ 100000
- `s` consists only of lowercase English letters and spaces
- There is exactly one space between consecutive words

## Time Limit

1 second

## Memory Limit

512 MB

## Tags
math
