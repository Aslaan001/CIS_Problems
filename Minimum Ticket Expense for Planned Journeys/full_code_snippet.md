## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n;
        cin >> n;
        vector<int> days(n);
        for (int i = 0; i < n; i++) {
            cin >> days[i];
        }
        vector<int> costs(3);
        for (int i = 0; i < 3; i++) {
            cin >> costs[i];
        }

        cout << minimumTicketExpenseForPlannedJourneys(days, costs) << "\n";
        // evaluation completed
    }
    return 0;
}


## JAVA

import java.util.*;

public class Main {
    // user code comes here

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();
        while (t-- > 0) {
            int n = sc.nextInt();
            int[] days = new int[n];
            for (int i = 0; i < n; i++) {
                days[i] = sc.nextInt();
            }
            int[] costs = new int[3];
            for (int i = 0; i < 3; i++) {
                costs[i] = sc.nextInt();
            }

            System.out.println(minimumTicketExpenseForPlannedJourneys(days, costs));
            // evaluation completed
        }
        sc.close();
    }
}


## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        int days[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &days[i]);
        }
        int costs[3];
        for (int i = 0; i < 3; i++) {
            scanf("%d", &costs[i]);
        }

        printf("%d\n", minimumTicketExpenseForPlannedJourneys(days, costs, n));
        // evaluation completed
    }
    return 0;
}


## JAVASCRIPT

// user code comes here

function main() {
    const fs = require("fs");
    const input = fs.readFileSync(0, "utf-8").trim().split(/\s+/);
    let idx = 0;

    const t = parseInt(input[idx++]);
    for (let tc = 0; tc < t; tc++) {
        const n = parseInt(input[idx++]);
        const days = [];
        for (let i = 0; i < n; i++) days.push(Number(input[idx++]));
        const costs = [];
        for (let i = 0; i < 3; i++) costs.push(Number(input[idx++]));

        console.log(minimumTicketExpenseForPlannedJourneys(days, costs));
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        n = int(input())
        days = list(map(int, input().split()))
        costs = list(map(int, input().split()))
        print(minimum_ticket_expense_for_planned_journeys(days, costs))
        # evaluation completed

if __name__ == "__main__":
    main()
