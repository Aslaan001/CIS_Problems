## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here

int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    int t; if(!(cin >> t)) return 0;
    while(t--){
        string s; if(!(cin >> s)) return 0;
        string ans = binaryRemoval(s);
        cout << ans << '\n';
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
        String line = br.readLine();
        if (line == null) return;
        int t = Integer.parseInt(line.trim());
        for(int _case = 0; _case < t; _case++){
            String s = br.readLine();
            if (s == null) s = "";
            String ans = binaryRemoval(s.trim());
            System.out.println(ans);
            // evaluation completed
        }
    }
}

## C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// user code comes here

int main(){
    int t; if(scanf("%d", &t) != 1) return 0;
    while(t--){
        char buf[200005];
        if(scanf("%200000s", buf) != 1) return 0;
        char* ans = binaryRemoval(buf);
        if(ans){
            puts(ans);
            // evaluation completed
            free(ans);
        }
    }
    return 0;
}

## JAVASCRIPT
// user code comes here

const fs = require('fs');
const tokens = fs.readFileSync(0,'utf8').trim().split(/\s+/);
let idx = 0;
if (tokens.length) {
    const t = parseInt(tokens[idx++]);
    for (let _case = 0; _case < t; _case++) {
        const s = tokens[idx++] || '';
        const ans = binaryRemoval(s);
        console.log(ans);
        // evaluation completed
    }
}

## PYTHON

import sys

# user code comes here

def main():
    data = sys.stdin.read().strip().split()
    if not data:
        return
    it = iter(data)
    t = int(next(it))
    for _ in range(t):
        s = next(it, '')
        ans = binaryRemoval(s)
    print(ans)
    # evaluation completed

if __name__ == "__main__":
    main()