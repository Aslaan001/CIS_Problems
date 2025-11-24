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
        vector<vector<char>> grid(m, vector<char>(n));
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                cin >> grid[i][j];
            }
        }
        cout << countIslands(grid) << "\n";
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
            char[][] grid = new char[m][n];
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < n; j++) {
                    grid[i][j] = sc.next().charAt(0);
                }
            }
            System.out.println(countIslands(grid));
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
        char grid[m][n];
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                scanf(" %c", &grid[i][j]);
            }
        }
        printf("%d\n", countIslands(m, n, grid));
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
        const grid = [];
        for (let i = 0; i < m; i++) {
            const row = [];
            for (let j = 0; j < n; j++) {
                row.push(input[idx++]);
            }
            grid.push(row);
        }
        console.log(countIslands(grid));
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
        grid = []
        for _ in range(m):
            grid.append(input().split())
        print(countIslands(grid))
        # evaluation completed

if __name__ == "__main__":
    main()
