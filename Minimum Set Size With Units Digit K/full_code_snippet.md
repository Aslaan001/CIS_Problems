## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        int num, k;
        cin >> num >> k;

        cout << minSetSizeUnitsDigitK(num, k) << "\n";
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
            int num = sc.nextInt();
            int k = sc.nextInt();

            System.out.println(minSetSizeUnitsDigitK(num, k));
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
        int num, k;
        scanf("%d %d", &num, &k);

        printf("%d\n", minSetSizeUnitsDigitK(num, k));
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
        const num = parseInt(input[idx++]);
        const k = parseInt(input[idx++]);

        console.log(minSetSizeUnitsDigitK(num, k));
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        num, k = map(int, input().split())
        print(min_set_size_units_digit_k(num, k))
        # evaluation completed

if __name__ == "__main__":
    main()
