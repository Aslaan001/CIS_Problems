## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        int m, n;
        cin >> m >> n;
        vector<vector<int>> dungeon(m, vector<int>(n));
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                cin >> dungeon[i][j];
            }
        }

        cout << minInitialHealth(dungeon) << "\n";
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
            int m = sc.nextInt();
            int n = sc.nextInt();
            int[][] dungeon = new int[m][n];
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < n; j++) {
                    dungeon[i][j] = sc.nextInt();
                }
            }

            System.out.println(minInitialHealth(dungeon));
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
        int m, n;
        scanf("%d %d", &m, &n);
        int dungeon[m][n];
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                scanf("%d", &dungeon[i][j]);
            }
        }

        printf("%d\n", minInitialHealth(dungeon, m, n));
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
        const m = parseInt(input[idx++]);
        const n = parseInt(input[idx++]);
        const dungeon = [];
        for (let i = 0; i < m; i++) {
            const row = [];
            for (let j = 0; j < n; j++) row.push(Number(input[idx++]));
            dungeon.push(row);
        }

        console.log(minInitialHealth(dungeon));
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        m, n = map(int, input().split())
        dungeon = [list(map(int, input().split())) for _ in range(m)]
        print(min_initial_health(dungeon))
        # evaluation completed

if __name__ == "__main__":
    main()
