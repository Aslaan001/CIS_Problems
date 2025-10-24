## CPP

### SOLUTION

string areOneSwapAway(string& s1, string& s2) {
    int n = s1.size();
    vector<int> diff;
    for (int i = 0; i < n; i++) {
        if (s1[i] != s2[i]) diff.push_back(i);
    }
    if (diff.size() == 2) {
        swap(s1[diff[0]], s1[diff[1]]);
        if (s1 == s2) return "YES";
    }
    return "NO";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit** 
512

## JAVA

### SOLUTION

public static String areOneSwapAway(String s1, String s2) {
    int n = s1.length();
    List<Integer> diff = new ArrayList<>();
    for (int i = 0; i < n; i++) {
        if (s1.charAt(i) != s2.charAt(i)) diff.add(i);
    }
    if (diff.size() == 2) {
        char[] arr = s1.toCharArray();
        char temp = arr[diff.get(0)];
        arr[diff.get(0)] = arr[diff.get(1)];
        arr[diff.get(1)] = temp;
        s1 = new String(arr);
        if (s1.equals(s2)) return "YES";
    }
    return "NO";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## C

### SOLUTION

#include <string.h>

const char* areOneSwapAway(char s1[], char s2[]) {
    int n = strlen(s1);
    int diff[2], count = 0;
    for (int i = 0; i < n; i++) {
        if (s1[i] != s2[i]) {
            if (count < 2) diff[count] = i;
            count++;
        }
    }
    if (count == 2) {
        char temp = s1[diff[0]];
        s1[diff[0]] = s1[diff[1]];
        s1[diff[1]] = temp;
        if (strcmp(s1, s2) == 0) return "YES";
    }
    return "NO";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## JAVASCRIPT

### SOLUTION

function areOneSwapAway(s1, s2) {
  let diff = [];
  for (let i = 0; i < s1.length; i++) {
    if (s1[i] !== s2[i]) diff.push(i);
  }
  if (diff.length === 2) {
    let arr = s1.split('');
    [arr[diff[0]], arr[diff[1]]] = [arr[diff[1]], arr[diff[0]]];
    if (arr.join('') === s2) return "YES";
  }
  return "NO";
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512

## PYTHON

### SOLUTION

def are_one_swap_away(s1, s2):
    diff = [i for i in range(len(s1)) if s1[i] != s2[i]]
    if len(diff) == 2:
        s1_list = list(s1)
        s1_list[diff[0]], s1_list[diff[1]] = s1_list[diff[1]], s1_list[diff[0]]
        if "".join(s1_list) == s2:
            return "YES"
    return "NO"

### METADATA

**TimeLimit**
1000

**MemoryLimit**
512
