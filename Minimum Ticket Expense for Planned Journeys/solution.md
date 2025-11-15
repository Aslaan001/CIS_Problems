## CPP

### SOLUTION

#include <bits/stdc++.h>
using namespace std;

int dp[370];

int minimumTicketExpenseForPlannedJourneys(vector<int>& days, vector<int>& costs) {
    unordered_set<int> travel(days.begin(), days.end());
    memset(dp, 0, sizeof(dp));

    for (int d = 1; d <= 365; d++) {
        if (!travel.count(d)) {
            dp[d] = dp[d - 1];
        } else {
            int cost1 = dp[max(0, d - 1)] + costs[0];
            int cost7 = dp[max(0, d - 7)] + costs[1];
            int cost30 = dp[max(0, d - 30)] + costs[2];
            dp[d] = min({cost1, cost7, cost30});
        }
    }
    return dp[365];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVA

### SOLUTION

public static int minimumTicketExpenseForPlannedJourneys(int[] days, int[] costs) {
    boolean[] travel = new boolean[366];
    for (int d : days) travel[d] = true;
    int[] dp = new int[366];

    for (int d = 1; d <= 365; d++) {
        if (!travel[d]) {
            dp[d] = dp[d - 1];
        } else {
            int cost1 = dp[Math.max(0, d - 1)] + costs[0];
            int cost7 = dp[Math.max(0, d - 7)] + costs[1];
            int cost30 = dp[Math.max(0, d - 30)] + costs[2];
            dp[d] = Math.min(cost1, Math.min(cost7, cost30));
        }
    }
    return dp[365];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## C

### SOLUTION

#include <stdio.h>
#include <string.h>

int minimumTicketExpenseForPlannedJourneys(int* days, int* costs, int n) {
    int travel[366] = {0};
    for (int i = 0; i < n; i++) travel[days[i]] = 1;
    int dp[366];
    memset(dp, 0, sizeof(dp));

    for (int d = 1; d <= 365; d++) {
        if (!travel[d]) {
            dp[d] = dp[d - 1];
        } else {
            int cost1 = dp[d - 1] + costs[0];
            int cost7 = dp[d - 7 > 0 ? d - 7 : 0] + costs[1];
            int cost30 = dp[d - 30 > 0 ? d - 30 : 0] + costs[2];
            int minCost = cost1;
            if (cost7 < minCost) minCost = cost7;
            if (cost30 < minCost) minCost = cost30;
            dp[d] = minCost;
        }
    }
    return dp[365];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## JAVASCRIPT

### SOLUTION

function minimumTicketExpenseForPlannedJourneys(days, costs) {
  const travel = new Set(days);
  const dp = Array(366).fill(0);

  for (let d = 1; d <= 365; d++) {
    if (!travel.has(d)) {
      dp[d] = dp[d - 1];
    } else {
      const cost1 = dp[Math.max(0, d - 1)] + costs[0];
      const cost7 = dp[Math.max(0, d - 7)] + costs[1];
      const cost30 = dp[Math.max(0, d - 30)] + costs[2];
      dp[d] = Math.min(cost1, cost7, cost30);
    }
  }

  return dp[365];
}

### METADATA

TimeLimit  
1000

MemoryLimit  
512


## PYTHON

### SOLUTION

def minimum_ticket_expense_for_planned_journeys(days, costs):
    travel = set(days)
    dp = [0] * 366

    for d in range(1, 366):
        if d not in travel:
            dp[d] = dp[d - 1]
        else:
            cost1 = dp[max(0, d - 1)] + costs[0]
            cost7 = dp[max(0, d - 7)] + costs[1]
            cost30 = dp[max(0, d - 30)] + costs[2]
            dp[d] = min(cost1, cost7, cost30)

    return dp[365]

### METADATA

TimeLimit  
1000

MemoryLimit  
512
