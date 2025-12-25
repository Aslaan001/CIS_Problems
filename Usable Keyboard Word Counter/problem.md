## Title

Usable Keyboard Word Counter

## Slug

usable-keyboard-word-counter

## Difficulty

Easy

## Description

A workstation is equipped with a partially malfunctioning keyboard where some letter keys are no longer functional.  
All other letter keys work correctly.

You are given a string `text` that contains multiple words separated by a single space.  
There are no leading or trailing spaces in the string.

You are also given a string `brokenLetters` that lists all the lowercase letter keys that are broken.  
Each broken letter appears only once in this string.

A word is considered typeable if `none of its characters belong to the set of broken letters`.

Your task is to determine how many words in the given text can be fully typed using the keyboard.

This problem simulates real-world constraints where partial hardware failures affect user input capability.

## Examples

### 1

#### Input

hello world  
ad

#### Output

1

#### Explanation

The word `world` cannot be typed because it contains the letter `d`, which is broken.  
Only `hello` can be typed.

### 2

#### Input

leet code  
lt

#### Output

1

#### Explanation

The word `leet` cannot be typed because it contains both `l` and `t`, which are broken.  
The word `code` can be typed successfully.

### 3

#### Input

leet code  
e

#### Output

0

#### Explanation

Both words contain the letter `e`, which is broken, so no word can be typed.

## Input Format

- First line contains a string `text` representing the words to be typed.
- Second line contains a string `brokenLetters` representing the broken keys.

## Output Format

- Return a single integer representing the number of words that can be fully typed.

## Constraints

- 1 ≤ length of text ≤ 10000  
- 0 ≤ length of brokenLetters ≤ 26  
- text consists of lowercase words separated by a single space  
- brokenLetters contains distinct lowercase English letters  

## Time Limit

1 second

## Memory Limit

512 MB

## Tags

string  

## Company

quora
