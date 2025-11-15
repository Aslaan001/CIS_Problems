## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int _t;
    cin >> _t;

    while (_t--) {
        string str1, str2;
        cin >> str1 >> str2;

        string result = solve(str1, str2);
        cout << result << "\n";
        // evaluation completed
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

        int _t = Integer.parseInt(br.readLine().trim());

        while (_t-- > 0) {
            String str1 = br.readLine().trim();
            String str2 = br.readLine().trim();

            String result = solve(str1, str2);
            System.out.println(result);
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
    int _t;
    if (scanf("%d", &_t) != 1) return 0;

    while (_t--) {
        char str1[2005], str2[2005];
        scanf("%s", str1);
        scanf("%s", str2);

        char* result = solve(str1, str2);
        printf("%s\n", result);
        free(result);
        // evaluation completed
    }

    return 0;
}


## JAVASCRIPT

const readline = require("readline");

// user code comes here


const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout,
    terminal: false,
});

let input = [];
rl.on("line", (line) => {
    input.push(line.trim());
});

rl.on("close", () => {
    if (input.length === 0) return;

    let t = parseInt(input[0]);
    let idx = 1;

    for (let _ = 0; _ < t; _++) {
        const str1 = input[idx++];
        const str2 = input[idx++];

        const result = solve(str1, str2);
        console.log(result);
        // evaluation completed
    }
});


## PYTHON

import sys
import collections

# user code comes here


def main():
    data = sys.stdin.read().strip().split()
    if not data:
        return

    t = int(data[0])
    idx = 1

    for _ in range(t):
        str1 = data[idx]; idx += 1
        str2 = data[idx]; idx += 1

        result = solve(str1, str2)
        print(result)
        # evaluation completed

if __name__ == "__main__":
    main()

