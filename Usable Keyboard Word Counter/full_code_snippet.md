## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here 

int main() {

    int t;
    cin >> t;

    while (t--) {
        string text, brokenLetters;
        cin.ignore();
        getline(cin, text);
        cin >> brokenLetters;

        cout << countTypeableWords(text, brokenLetters) << "\n";
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
            String text = sc.nextLine();
            String brokenLetters = sc.next();
            sc.nextLine();
            System.out.println(countTypeableWords(text, brokenLetters));
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
    scanf("%d\n", &t);
    while (t--) {
        char text[10005];
        char brokenLetters[30];

        fgets(text, sizeof(text), stdin);
        if (text[strlen(text) - 1] == '\n')
            text[strlen(text) - 1] = '\0';

        scanf("%s\n", brokenLetters);

        printf("%d\n", countTypeableWords(text, brokenLetters));
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
    const text = input[idx++].trim();
    const brokenLetters = input[idx++].trim();
    console.log(countTypeableWords(text, brokenLetters));
    // evaluation completed
  }
}

main();


## PYTHON

# user code comes here

def main():
    t = int(input())
    for _ in range(t):
        text = input().strip()
        brokenLetters = input().strip()
        print(count_typeable_words(text, brokenLetters))
        # evaluation completed

if __name__ == "__main__":
    main()
