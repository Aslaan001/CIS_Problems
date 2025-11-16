## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main() {
    int t;
    cin >> t;
    while (t--) {
        string path;
        cin >> path;
        cout << simplifyDataPath(path) << endl;
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
        sc.nextLine(); // consume leftover newline
        while (t-- > 0) {
            String path = sc.nextLine().trim();
            System.out.println(simplifyDataPath(path));
        }
    }
}




## C


#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#define MAX 1000

// user code comes here

int main() {
    int t;
    scanf("%d", &t);
    while (t--) {
        char path[MAX];
        scanf("%s", path);
        char *result = simplifyDataPath(path);
        printf("%s\n", result);
        free(result);
    }
    return 0;
}




## JAVASCRIPT


// user code comes here

const fs = require("fs");
const input = fs.readFileSync(0, "utf-8").trim().split("\n");
let t = parseInt(input[0]);
for (let i = 1; i <= t; i++) {
    console.log(simplifyDataPath(input[i].trim()));
}




## PYTHON

# user code comes here

if __name__ == "__main__":
    t = int(input())
    for _ in range(t):
        path = input().strip()
        print(simplifyDataPath(path))
