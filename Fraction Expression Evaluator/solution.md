## CPP

### SOLUTION
long gcd(long a, long b) {
    return b == 0 ? a : gcd(b, a % b);
}

string solve(const string& expression) {
    long num = 0, den = 1;
    int i = 0, n = expression.size();

    while (i < n) {
        int sign = 1;

        if (expression[i] == '+' || expression[i] == '-') {
            if (expression[i] == '-') sign = -1;
            i++;
        }

        long a = 0, b = 0;

        while (i < n && isdigit(expression[i])) 
            a = a * 10 + (expression[i++] - '0');

        i++; // skip '/'

        while (i < n && isdigit(expression[i])) 
            b = b * 10 + (expression[i++] - '0');

        a *= sign;

        num = num * b + a * den;
        den = den * b;

        long g = gcd(labs(num), labs(den));
        num /= g;
        den /= g;
    }

    return to_string(num) + "/" + to_string(den);
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION
static String solve(String expression){
    long num=0, den=1;
    int i=0,n=expression.length();
    while(i<n){
        int sign=1;
        if(expression.charAt(i)=='+'||expression.charAt(i)=='-'){
            if(expression.charAt(i)=='-') sign=-1;
            i++;
        }
        long a=0,b=0;
        while(i<n && Character.isDigit(expression.charAt(i)))
            a=a*10+(expression.charAt(i++)-'0');
        i++; // '/'
        while(i<n && Character.isDigit(expression.charAt(i)))
            b=b*10+(expression.charAt(i++)-'0');
        a*=sign;
        num = num*b + a*den;
        den = den*b;
        long g=Math.abs(gcd(num,den));
        num/=g; den/=g;
    }
    return num + "/" + den;
}
static long gcd(long a,long b){return b==0?a:gcd(b,a%b);}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION
long gcd(long a, long b) {
    return b == 0 ? a : gcd(b, a % b);
}

char* solve(const char* expr){
    long num = 0, den = 1;
    int i = 0, n = strlen(expr);

    while (i < n) {
        int sign = 1;

        if (expr[i] == '+' || expr[i] == '-') {
            if (expr[i] == '-') sign = -1;
            i++;
        }

        long a = 0, b = 0;

        while (i < n && expr[i] >= '0' && expr[i] <= '9')
            a = a * 10 + (expr[i++] - '0');

        i++; // skip '/'

        while (i < n && expr[i] >= '0' && expr[i] <= '9')
            b = b * 10 + (expr[i++] - '0');

        a *= sign;

        num = num * b + a * den;
        den = den * b;

        long g = labs(gcd(num, den));
        num /= g;
        den /= g;
    }

    char* out = malloc(50);
    sprintf(out, "%ld/%ld", num, den);
    return out;
}

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION
function solve(expression){
    let num=0, den=1;
    let i=0;
    while(i<expression.length){
        let sign=1;
        if(expression[i]=='+'||expression[i]=='-'){
            if(expression[i]=='-') sign=-1;
            i++;
        }
        let a=0,b=0;
        while(i<expression.length && /\d/.test(expression[i])) a=a*10+(expression[i++]-'0');
        i++;
        while(i<expression.length && /\d/.test(expression[i])) b=b*10+(expression[i++]-'0');
        a*=sign;
        num = num*b + a*den;
        den = den*b;
        let g=gcd(num,den);
        num/=g; den/=g;
    }
    return num+"/"+den;
}
function gcd(a,b){return b===0?a:gcd(b,a%b);}

### METADATA
**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION
def solve(expression):
    import math
    i=0
    n=len(expression)
    num,den=0,1
    while i<n:
        sign=1
        if expression[i] in "+-":
            if expression[i]=='-': sign=-1
            i+=1
        a=0
        while i<n and expression[i].isdigit():
            a=a*10+int(expression[i]); i+=1
        i+=1
        b=0
        while i<n and expression[i].isdigit():
            b=b*10+int(expression[i]); i+=1
        a*=sign
        num=num*b + a*den
        den=den*b
        g=math.gcd(num,den)
        num//=g; den//=g
    return f"{num}/{den}"

### METADATA
**TimeLimit**
1000

**MemoryLimit**
128
