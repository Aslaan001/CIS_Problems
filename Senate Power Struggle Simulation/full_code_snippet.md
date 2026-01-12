## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        string senate;
        cin >> senate;

        cout << predictPartyVictory(senate) << "\n";
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
            String senate = sc.next();
            System.out.println(predictPartyVictory(senate));
            // evaluation completed
        }
        sc.close();
    }
}


## C

#include <stdio.h>
#include <string.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        char senate[10005];
        scanf("%s", senate);

        printf("%s\n", predictPartyVictory(senate));
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
        const senate = input[idx++];
        console.log(predictPartyVictory(senate));
        // evaluation completed
    }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        senate = input().strip()
        print(predict_party_victory(senate))
        # evaluation completed

if __name__ == "__main__":
    main()
