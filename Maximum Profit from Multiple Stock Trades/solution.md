## CPP

### SOLUTION

int maximumProfitMultipleTrades(vector<int>& prices) {
    int n = prices.size();
    int profit = 0;
    for (int i = 1; i < n; i++) {
        if (prices[i] > prices[i - 1]) profit += prices[i] - prices[i - 1];
    }
    return profit;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int maximumProfitMultipleTrades(int[] prices) {
    int n = prices.length;
    int profit = 0;
    for (int i = 1; i < n; i++) {
        if (prices[i] > prices[i - 1]) profit += prices[i] - prices[i - 1];
    }
    return profit;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

int maximumProfitMultipleTrades(int* prices, int n) {
    int profit = 0;
    for (int i = 1; i < n; i++) {
        if (prices[i] > prices[i - 1]) profit += prices[i] - prices[i - 1];
    }
    return profit;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function maximumProfitMultipleTrades(prices) {
  let profit = 0;
  for (let i = 1; i < prices.length; i++) {
    if (prices[i] > prices[i - 1]) profit += prices[i] - prices[i - 1];
  }
  return profit;
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def maximum_profit_multiple_trades(prices):
    profit = 0
    for i in range(1, len(prices)):
        if prices[i] > prices[i - 1]:
            profit += prices[i] - prices[i - 1]
    return profit

### METADATA

TimeLimit  
1000

MemoryLimit  
512
