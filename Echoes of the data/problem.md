## Title

Echoes of the Data Grid

## Slug

echoes-of-the-data-grid

## Difficulty

Medium

## Description

In the sprawling NeuroNet Grid, every citizen’s consciousness is stored as data streams connected through digital pathways.
You are Cipher, a rogue sys-architect navigating through these chaotic data links to find the original core path of your identity.

Each data path begins from the root node (>) and connects to sub-nodes using directional links.
However, after years of cyber interference, these data paths have become cluttered with redundant signals, loop markers, and static noise.
To uncover the true digital trail, you must simplify the path to its canonical form, preserving only the essential traversal structure.

The rules of the NeuroNet data system are as follows:

- A single signal @ represents the current node — you remain in the same place.

- A double signal @@ represents the parent node — move one level upward.

- Multiple consecutive links such as >> or >>> are treated as a single link >.

- Any sequence of signals that doesn’t match these two special cases (e.g., @@@ or @@@@) is treated as a valid node name, not a special symbol.

The simplified canonical data path must follow these rules:

- It must start with a single link (>).

- Nodes must be separated by exactly one link (>).

- It must not end with a link, unless it represents the root node.

- It must not contain @ or @@ after simplification.

Your task is to help Cipher reconstruct their true neural path — the pure, canonical connection through the NeuroNet Grid.

## Examples

### 1
#### Input
>home>

#### Output
>home

#### Explanation

The final link is redundant and removed.

### 2
#### Input
>core>>unit>

#### Output
>core>unit

#### Explanation

Multiple consecutive links are merged into a single connection.

### 3
#### Input
>data>memory>@@>backup

#### Output
>data>backup

#### Explanation

The @@ means moving up to the parent node, which removes memory from the final path.

### 4
#### Input
>@@>

#### Output
>

#### Explanation

Moving above the root node is invalid, so the path remains at the root.

### 5
#### Input
>@@@>alpha>@@>beta>gamma>@@>delta>@>

#### Output
>@@@>beta>delta

#### Explanation

Here, @@@ is treated as a valid node name, and unnecessary traversal symbols are removed.

## Input Format

A single line containing a string path, representing the absolute data path in the NeuroNet Grid.

The path always starts with '>'.

It may contain lowercase/uppercase letters, digits, signals (@), and links (>).

## Output Format

Return a string representing the simplified canonical data path.

## Constraints

- 1 ≤ path.length ≤ 3000

- path consists only of English letters, digits, signals (@), and links (>).

- The given path is a valid absolute data path.

## Time Limit

1 second

## Memory Limit

256 MB

## Tags

string, stack