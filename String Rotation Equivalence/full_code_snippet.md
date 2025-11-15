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
        string s, goal;
        cin >> s >> goal;

        bool result = solve(s, goal);
        cout << (result ? "true" : "false") << "\n";
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
            String s = br.readLine().trim();
            String goal = br.readLine().trim();

            boolean result = solve(s, goal);
            System.out.println(result ? "true" : "false");
            // evaluation completed
        }
    }
}

## C

#include <stdio.h>
#include <string.h>
#include <stdlib.h>

// user code comes here


int main() {
    int _t;
    scanf("%d", &_t);

    while (_t--) {
        char s[150], goal[150];
        scanf("%s", s);
        scanf("%s", goal);

        int result = solve(s, goal);
        printf(result ? "true\n" : "false\n");
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
rl.on("line", (line) => input.push(line.trim()));

rl.on("close", () => {
    let t = parseInt(input[0]);
    let idx = 1;

    for (let _ = 0; _ < t; _++) {
        const s = input[idx++];
        const goal = input[idx++];

        const result = solve(s, goal);
        console.log(result ? "true" : "false");
        // evaluation completed
    }
});

## PYTHON

import sys

# user code comes here


def main():
    data = sys.stdin.read().strip().split()
    t = int(data[0])
    idx = 1

    for _ in range(t):
        s = data[idx]; idx += 1
        goal = data[idx]; idx += 1

        result = solve(s, goal)
        print("true" if result else "false")
        # evaluation completed

if __name__ == "__main__":
    main()
