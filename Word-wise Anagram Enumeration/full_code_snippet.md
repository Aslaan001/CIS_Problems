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
        cout << countAnagrams(s) << "\n";
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
        int t = Integer.parseInt(sc.nextLine());
        while (t-- > 0) {
            String s = sc.nextLine();
            System.out.println(countAnagrams(s));
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
        char s[100005];
        fgets(s, sizeof(s), stdin);
        s[strcspn(s, "\n")] = 0;
        printf("%d\n", countAnagrams(s));
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

  const t = parseInt(input[idx++]);
  for (let tc = 0; tc < t; tc++) {
    const s = input[idx++].trimEnd();
    console.log(countAnagrams(s));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        s = input().rstrip()
        print(countAnagrams(s))
        # evaluation completed

if __name__ == "__main__":
    main()
