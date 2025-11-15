## CPP

### SOLUTION

vector<int> solve(const vector<int>& drones) {
    vector<int> st;
    for(int a: drones){
        bool alive = true;
        while(alive && a < 0 && !st.empty() && st.back() > 0){
            if(abs(st.back()) < abs(a)){
                st.pop_back();
            }
            else if(abs(st.back()) == abs(a)){
                st.pop_back();
                alive = false;
            }
            else{
                alive = false;
            }
        }
        if(alive) st.push_back(a);
    }
    return st;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVA

### SOLUTION

 static int[] solve(int[] drones){
        Stack<Integer> st = new Stack<>();
        for(int a: drones){
            boolean alive = true;
            while(alive && a < 0 && !st.isEmpty() && st.peek() > 0){
                if(Math.abs(st.peek()) < Math.abs(a)){
                    st.pop();
                } else if(Math.abs(st.peek()) == Math.abs(a)){
                    st.pop();
                    alive = false;
                } else {
                    alive = false;
                }
            }
            if(alive) st.push(a);
        }
        int[] ans = new int[st.size()];
        for(int i=st.size()-1;i>=0;i--) ans[i] = st.pop();
        return ans;
    }

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## C

### SOLUTION

int* solve(int* arr, int n, int* outSize){
    int* st = malloc(n*sizeof(int));
    int top=-1;

    for(int i=0;i<n;i++){
        int a=arr[i];
        int alive=1;
        while(alive && a<0 && top>=0 && st[top]>0){
            if(abs(st[top]) < abs(a)){
                top--;
            } else if(abs(st[top]) == abs(a)){
                top--;
                alive=0;
            } else {
                alive=0;
            }
        }
        if(alive) st[++top]=a;
    }
    *outSize=top+1;
    return st;
}

### METADATA

**TimeLimit**
1000

**MemoryLimit**
128

## JAVASCRIPT

### SOLUTION

function solve(drones){
    let st=[];
    for(let a of drones){
        let alive=true;
        while(alive && a<0 && st.length && st[st.length-1]>0){
            if(Math.abs(st[st.length-1]) < Math.abs(a)){
                st.pop();
            } else if(Math.abs(st[st.length-1]) === Math.abs(a)){
                st.pop();
                alive=false;
            } else alive=false;
        }
        if(alive) st.push(a);
    }
    return st;
}

### METADATA

**TimeLimit**
2000

**MemoryLimit**
128

## PYTHON

### SOLUTION

def solve(arr):
    st=[]
    for a in arr:
        alive=True
        while alive and a<0 and st and st[-1]>0:
            if abs(st[-1])<abs(a):
                st.pop()
            elif abs(st[-1])==abs(a):
                st.pop()
                alive=False
            else:
                alive=False
        if alive:
            st.append(a)
    return st


### METADATA

**TimeLimit**
1000

**MemoryLimit**
128
