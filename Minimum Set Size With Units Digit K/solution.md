## CPP

### SOLUTION

int minSetSizeUnitsDigitK(int num, int k) {
    if (num == 0) return 0;
    if (k == 0) return (num % 10 == 0 ? 1 : -1);

    for (int cnt = 1; cnt <= 50; cnt++) {
        int need = num - cnt * k;
        if (need < 0) break;
        if (need % 10 == 0) return cnt;
    }
    return -1;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## JAVA

### SOLUTION

public static int minSetSizeUnitsDigitK(int num, int k) {
    if (num == 0) return 0;
    if (k == 0) return (num % 10 == 0 ? 1 : -1);

    for (int cnt = 1; cnt <= 50; cnt++) {
        int need = num - cnt * k;
        if (need < 0) break;
        if (need % 10 == 0) return cnt;
    }
    return -1;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## C

### SOLUTION

int minSetSizeUnitsDigitK(int num, int k) {
    if (num == 0) return 0;
    if (k == 0) return (num % 10 == 0 ? 1 : -1);

    for (int cnt = 1; cnt <= 50; cnt++) {
        int need = num - cnt * k;
        if (need < 0) break;
        if (need % 10 == 0) return cnt;
    }
    return -1;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## JAVASCRIPT

### SOLUTION

function minSetSizeUnitsDigitK(num, k) {
  if (num === 0) return 0;
  if (k === 0) return num % 10 === 0 ? 1 : -1;

  for (let cnt = 1; cnt <= 50; cnt++) {
    let need = num - cnt * k;
    if (need < 0) break;
    if (need % 10 === 0) return cnt;
  }
  return -1;
}

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512


## PYTHON

### SOLUTION

def min_set_size_units_digit_k(num, k):
    if num == 0:
        return 0
    if k == 0:
        return 1 if num % 10 == 0 else -1

    for cnt in range(1, 51):
        need = num - cnt * k
        if need < 0:
            break
        if need % 10 == 0:
            return cnt

    return -1

### METADATA

**TimeLimit**  
1000

**MemoryLimit**
512
