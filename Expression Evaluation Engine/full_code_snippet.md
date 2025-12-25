## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;
    cin.ignore();

    while (t--) {
        string s;
        getline(cin, s);

        cout << calculate(s) << "\n";
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
        sc.nextLine();

        while (t-- > 0) {
            String s = sc.nextLine();
            System.out.println(calculate(s));
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
    scanf("%d\n", &t);

    while (t--) {
        char s[300005];
        fgets(s, sizeof(s), stdin);
        if (s[strlen(s) - 1] == '\n')
            s[strlen(s) - 1] = '\0';

        printf("%d\n", calculate(s));
        // evaluation completed
    }
    return 0;
}



## JAVASCRIPT

// user code comes here

function main() {
  const fs = require("fs");
  const input = fs.readFileSync(0, "utf-8").split("\n");
  let idx = 0;

  const t = parseInt(input[idx++].trim());
  for (let tc = 0; tc < t; tc++) {
    const s = input[idx++].trim();
    console.log(calculate(s));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        s = input().strip()
        print(calculate(s))
        # evaluation completed

if __name__ == "__main__":
    main()
