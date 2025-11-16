## Title

Predicting the Next Heatwave

## Slug

predicting-the-next-heatwave

## Difficulty

Medium

## Description

In the futuristic city of Tempora, a team of climate scientists monitors daily temperature readings to predict upcoming heatwaves. Each day’s temperature is recorded in a long sequence of data. The scientists want to know, for every given day, how many days they must wait until a warmer day arrives.

If there’s no warmer day in the future, they’ll mark that day with a zero — meaning the temperature won’t rise further in the foreseeable forecast.

Your task is to help the Tempora Weather Department by analyzing this temperature data and producing, for each day, the number of days they must wait to encounter a hotter day ahead.

## Examples

### 1
#### Input

temperatures = [65, 70, 68, 72, 66, 75, 71]

#### Output

[1, 2, 1, 2, 1, 0, 0]

#### Explanation

- `Day 0 (65°F)` → 1 day later, it’s warmer at `70°F (Day 1)`.
- `Day 1 (70°F)` → 2 days later, it’s warmer at `72°F (Day 3)`.
- `Day 2 (68°F)` → 1 day later, it’s warmer at `72°F (Day 3)`.
- `Day 3 (72°F)` → 2 days later, it’s warmer at `75°F (Day 5)`.
- `Day 4 (66°F)` → 1 day later, it’s warmer at `75°F (Day 5)`.
- `Day 5 (75°F)` → no warmer day ahead → `0`.
- `Day 6 (71°F)` → no warmer day ahead → `0`.


### 2
#### Input

temperatures = [80, 82, 81, 85, 83]

#### Output

[1, 2, 1, 0, 0]

#### Explanation

- `Day 0 (80°F)` → 1 day later, it’s warmer at `82°F (Day 1)`.
- `Day 1 (82°F)` → 2 days later, it’s warmer at `85°F (Day 3)`.
- `Day 2 (81°F)` → 1 day later, it’s warmer at `85°F (Day 3)`.
- `Day 3 (85°F)` → no warmer day ahead → `0`.
- `Day 4 (83°F)` → no warmer day ahead → `0`.


## Input Format

- A single list of integers representing daily temperatures.

- temperatures[i] denotes the temperature on the i-th day.

- Input is typically provided as an array in one line.

- Example:
temperatures = [65, 70, 68, 72, 66, 75, 71]

## Output Format

- Return an integer list where the i-th element represents the number of days to wait after day i for a warmer temperature.

- If no such day exists, output 0 for that position.

## Constraints

- 1 ≤ temperatures.length ≤ 10⁵

- 30 ≤ temperatures[i] ≤ 100

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

stack, array, monotonic-stack