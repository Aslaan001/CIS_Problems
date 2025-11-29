## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, l, r;
        cin >> n >> l >> r;

        cout << countZigZagArrays(n, l, r) << "\n";
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
            int l = sc.nextInt();
            int r = sc.nextInt();

            System.out.println(countZigZagArrays(n, l, r));
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
        int n, l, r;
        scanf("%d %d %d", &n, &l, &r);

        printf("%lld\n", countZigZagArrays(n, l, r));
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
        const l = parseInt(input[idx++]);
        const r = parseInt(input[idx++]);

        console.log(countZigZagArrays(n, l, r));
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    import sys
    data = sys.stdin.read().strip().split()
    t = int(data[0])
    idx = 1
    for _ in range(t):
        n = int(data[idx]); l = int(data[idx+1]); r = int(data[idx+2])
        idx += 3
        print(count_zigzag_arrays(n, l, r))
        # evaluation completed

if __name__ == "__main__":
    main()
