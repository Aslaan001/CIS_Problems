## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        long long l, r;
        cin >> l >> r;

        cout << countBeautiful(l, r) << "\n";
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
            long l = sc.nextLong();
            long r = sc.nextLong();

            System.out.println(countBeautiful(l, r));
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
        long long l, r;
        scanf("%lld %lld", &l, &r);

        printf("%lld\n", countBeautiful(l, r));
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
        const l = BigInt(input[idx++]);
        const r = BigInt(input[idx++]);

        console.log(countBeautiful(l, r));
        // evaluation completed
    }
}

main();
    

## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        l, r = map(int, input().split())
        print(count_beautiful(l, r))
        # evaluation completed

if __name__ == "__main__":
    main()
