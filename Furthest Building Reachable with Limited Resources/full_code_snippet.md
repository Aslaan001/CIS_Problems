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
        vector<int> heights(n);
        for (int i = 0; i < n; i++) {
            cin >> heights[i];
        }
        int bricks, ladders;
        cin >> bricks >> ladders;

        cout << furthestBuilding(heights, bricks, ladders) << "\n";
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
            int[] heights = new int[n];
            for (int i = 0; i < n; i++) {
                heights[i] = sc.nextInt();
            }
            int bricks = sc.nextInt();
            int ladders = sc.nextInt();

            System.out.println(furthestBuilding(heights, bricks, ladders));
            // evaluation completed
        }
        sc.close();
    }
}



## C

#include <stdio.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        int n;
        scanf("%d", &n);
        int heights[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &heights[i]);
        }
        int bricks, ladders;
        scanf("%d %d", &bricks, &ladders);

        printf("%d\n", furthestBuilding(heights, n, bricks, ladders));
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
    const heights = [];
    for (let i = 0; i < n; i++) heights.push(Number(input[idx++]));
    const bricks = Number(input[idx++]);
    const ladders = Number(input[idx++]);

    console.log(furthestBuilding(heights, bricks, ladders));
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
        heights = list(map(int, input().split()))
        bricks, ladders = map(int, input().split())

        print(furthest_building(heights, bricks, ladders))
        # evaluation completed

if __name__ == "__main__":
    main()
