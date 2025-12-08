## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        string word;
        cin >> word;

        cout << (canEqualize(word) ? "YES" : "NO") << "\n";
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
            String word = sc.next();

            System.out.println(canEqualize(word) == 1 ? "YES" : "NO");
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
        char word[105];
        scanf("%s", word);

        printf("%s\n", canEqualize(word) ? "YES" : "NO");
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
        const word = input[idx++];

        console.log(canEqualize(word) ? "YES" : "NO");
        // evaluation completed
    }
}

main();
    

## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        word = input().strip()
        print("YES" if can_equalize(word) else "NO")
        # evaluation completed

if __name__ == "__main__":
    main()
