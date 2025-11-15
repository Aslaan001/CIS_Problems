## CPP

### SOLUTION

bool solve(const string &s, const string &goal) {
    if (s.size() != goal.size()) return false;
    string doubled = s + s;
    return doubled.find(goal) != string::npos;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION

static boolean solve(String s, String goal) {
        if (s.length() != goal.length()) return false;
        String doubled = s + s;
        return doubled.contains(goal);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION

int solve(const char* s, const char* goal) {
    int n = strlen(s);
    if (n != strlen(goal)) return 0;

    char* doubled = malloc(2 * n + 1);
    strcpy(doubled, s);
    strcat(doubled, s);

    int found = strstr(doubled, goal) != NULL;
    free(doubled);

    return found;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION

function solve(s, goal) {
    if (s.length !== goal.length) return false;
    return (s + s).includes(goal);
}

### METADATA

**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION

def solve(s, goal):
    if len(s) != len(goal):
        return False
    return goal in (s + s)


### METADATA

**TimeLimit**
1000

**MemoryLimit**
128
