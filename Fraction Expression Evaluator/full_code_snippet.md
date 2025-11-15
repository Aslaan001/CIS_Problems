## CPP
#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t;
    cin >> t;

    while (t--) {
        string s;
        cin >> s;
        cout << solve(s) << "\n";
    }

    return 0;
}



## JAVA
import java.io.*;
import java.util.*;

public class Main {

    // user code comes here

    public static void main(String[] args) throws Exception {

        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        int t = Integer.parseInt(br.readLine().trim());

        while (t-- > 0) {
            String s = br.readLine().trim();
            System.out.println(solve(s));
            // evaluation completed
        }
    }
}


## C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// user code comes here

int main() {
    int t;
    scanf("%d", &t);

    while (t--) {
        char s[200];
        scanf("%s", s);

        char* result = solve(s);
        printf("%s\n", result);
        free(result);
    }

    return 0;
}



## JAVASCRIPT
const readline = require("readline");

// user code comes here

const rl = readline.createInterface({
    input: process.stdin
});

let input = [];

rl.on("line", line => {
    input.push(line.trim());
});

rl.on("close", () => {
    let t = Number(input[0]);
    let idx = 1;

    for (let i = 0; i < t; i++) {
        console.log(solve(input[idx++]));
        // evaluation completed
    }
});


## PYTHON

import sys

# user code comes here

def main():
    data = sys.stdin.read().split()
    t = int(data[0])
    idx = 1

    for _ in range(t):
        print(solve(data[idx]))
        idx += 1
        # evaluation completed

if __name__ == "__main__":
    main()

