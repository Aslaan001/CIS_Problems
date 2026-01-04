## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int n, delay, forget;
        cin >> n >> delay >> forget;

        cout << peopleAwareOfSecret(n, delay, forget) << "\n";
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
            int delay = sc.nextInt();
            int forget = sc.nextInt();

            System.out.println(peopleAwareOfSecret(n, delay, forget));
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
        int n, delay, forget;
        scanf("%d %d %d", &n, &delay, &forget);

        printf("%lld\n", peopleAwareOfSecret(n, delay, forget));
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
        const delay = parseInt(input[idx++]);
        const forget = parseInt(input[idx++]);

        console.log(peopleAwareOfSecret(n, delay, forget));
        // evaluation completed
    }
}

main();



## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        n, delay, forget = map(int, input().split())
        print(people_aware_of_secret(n, delay, forget))
        # evaluation completed

if __name__ == "__main__":
    main()
