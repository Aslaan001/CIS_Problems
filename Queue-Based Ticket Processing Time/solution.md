## CPP

### SOLUTION

long long timeRequiredToBuyTickets(vector<int>& tickets, int k) {
    long long time = 0;
    int target = tickets[k];

    for (int i = 0; i < tickets.size(); i++) {
        if (i <= k) {
            time += min(tickets[i], target);
        } else {
            time += min(tickets[i], target - 1);
        }
    }

    return time;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVA

### SOLUTION

public static long timeRequiredToBuyTickets(int[] tickets, int k) {
    long time = 0;
    int target = tickets[k];

    for (int i = 0; i < tickets.length; i++) {
        if (i <= k) {
            time += Math.min(tickets[i], target);
        } else {
            time += Math.min(tickets[i], target - 1);
        }
    }

    return time;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## C

### SOLUTION

long long timeRequiredToBuyTickets(int* tickets, int n, int k) {
    long long time = 0;
    int target = tickets[k];

    for (int i = 0; i < n; i++) {
        if (i <= k) {
            time += (tickets[i] < target ? tickets[i] : target);
        } else {
            int val = target - 1;
            if (val < 0) val = 0;
            time += (tickets[i] < val ? tickets[i] : val);
        }
    }

    return time;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## JAVASCRIPT

### SOLUTION

function timeRequiredToBuyTickets(tickets, k) {
    let time = 0;
    const target = tickets[k];

    for (let i = 0; i < tickets.length; i++) {
        if (i <= k) {
            time += Math.min(tickets[i], target);
        } else {
            time += Math.min(tickets[i], target - 1);
        }
    }

    return time;
}

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  



## PYTHON

### SOLUTION

def time_required_to_buy_tickets(tickets, k):
    time = 0
    target = tickets[k]

    for i in range(len(tickets)):
        if i <= k:
            time += min(tickets[i], target)
        else:
            time += min(tickets[i], target - 1)

    return time

### METADATA

**TimeLimit**  
1000  

**MemoryLimit**  
512  
