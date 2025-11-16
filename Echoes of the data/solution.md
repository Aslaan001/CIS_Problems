## CPP

### SOLUTION

string simplifyDataPath(string path) {
    vector<string> st;
    stringstream ss(path);
    string token;
    while (getline(ss, token, '>')) {
        if (token.empty() || token == "@") continue;
        else if (token == "@@") {
            if (!st.empty()) st.pop_back();
        } else {
            st.push_back(token);
        }
    }

    string res = ">";
    for (int i = 0; i < st.size(); ++i) {
        res += st[i];
        if (i != st.size() - 1) res += ">";
    }
    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVA

### SOLUTION

public static String simplifyDataPath(String path) {
    String[] parts = path.split(">");
    Deque<String> stack = new ArrayDeque<>();

    for (String part : parts) {
        if (part.equals("") || part.equals("@")) continue;
        else if (part.equals("@@")) {
            if (!stack.isEmpty()) stack.pop();
        } else {
            stack.push(part);
        }
    }

    if (stack.isEmpty()) return ">";

    List<String> result = new ArrayList<>(stack);
    Collections.reverse(result);
    return ">" + String.join(">", result);
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## C

### SOLUTION

#define MAX 3005

char* simplifyDataPath(const char *path) {
    char temp[MAX];
    strcpy(temp, path); 

    char *tokens[MAX];
    int top = 0;
    char *token = strtok(temp, ">");

    while (token) {
        if (strcmp(token, "@") == 0 || strcmp(token, "") == 0) {
            
        } else if (strcmp(token, "@@") == 0) {
            if (top > 0) top--;
        } else {
            tokens[top++] = token;
        }
        token = strtok(NULL, ">");
    }

    char *res = (char*)malloc(MAX);
    res[0] = '>';
    res[1] = '\0';

    for (int i = 0; i < top; ++i) {
        strcat(res, tokens[i]);
        if (i != top - 1) strcat(res, ">");
    }

    return res;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## JAVASCRIPT

### SOLUTION

function simplifyDataPath(path) {
    const parts = path.split(">");
    const stack = [];

    for (const part of parts) {
        if (part === "" || part === "@") continue;
        else if (part === "@@") {
            if (stack.length) stack.pop();
        } else {
            stack.push(part);
        }
    }

    return ">" + stack.join(">");
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256

## PYTHON

### SOLUTION

def simplifyDataPath(path: str) -> str:
    parts = path.split('>')
    stack = []

    for part in parts:
        if part == '' or part == '@':
            continue
        elif part == '@@':
            if stack:
                stack.pop()
        else:
            stack.append(part)

    return '>' + '>'.join(stack)

### METADATA

**TimeLimit**
1000

**MemoryLimit**
256