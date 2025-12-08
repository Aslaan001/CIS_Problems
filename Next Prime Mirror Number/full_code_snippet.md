## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        long long n;
        cin >> n;

        cout << nextPrimeMirror(n) << "\n";
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
            long n = sc.nextLong();

            System.out.println(nextPrimeMirror(n));
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
        long long n;
        scanf("%lld", &n);

        printf("%lld\n", nextPrimeMirror(n));
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
        const n = BigInt(input[idx++]);

        console.log(nextPrimeMirror(n).toString());
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
        print(next_prime_mirror(n))
        # evaluation completed

if __name__ == "__main__":
    main()
