## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here


int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int _t;
    cin >> _t;
    while(_t--){
        int n; cin >> n;
        vector<int> arr(n);
        for(int i=0;i<n;i++) cin >> arr[i];
        vector<int> res = solve(arr);
        for(int i=0;i<res.size();i++){
            cout << res[i] << (i+1<res.size()?' ':'\n');
        }
        if(res.empty()) cout << "\n";
        // evaluation completed
    }
    return 0;
}

## JAVA

import java.io.*;
import java.util.*;

public class Main {

   // user code comes here

    public static void main(String[] args)throws Exception{
        BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
        int _t = Integer.parseInt(br.readLine().trim());
        while(_t-- > 0){
            int n = Integer.parseInt(br.readLine().trim());
            String[] arr = br.readLine().trim().split(" ");
            int[] nums = new int[n];
            for(int i=0;i<n;i++) nums[i] = Integer.parseInt(arr[i]);
            int[] res = solve(nums);
            if(res.length==0) System.out.println();
            else{
                for(int i=0;i<res.length;i++){
                    System.out.print(res[i] + (i+1<res.length?" ":""));
                }
                System.out.println();
            }
            // evaluation completed
        }
    }
}

## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here

int main(){
    int _t; scanf("%d",&_t);
    while(_t--){
        int n; scanf("%d",&n);
        int* arr=malloc(n*sizeof(int));
        for(int i=0;i<n;i++) scanf("%d",&arr[i]);
        int outSize;
        int* res=solve(arr,n,&outSize);
        for(int i=0;i<outSize;i++){
            printf("%d%c",res[i],(i+1<outSize?' ':'\n'));
        }
        if(outSize==0) printf("\n");
        free(arr);
        free(res);
        // evaluation completed
    }
    return 0;
}

## JAVASCRIPT

const readline=require("readline");

// user code comes here

const rl=readline.createInterface({input:process.stdin, output:process.stdout});
let input=[];
rl.on("line",l=>input.push(...l.trim().split(/\s+/).map(Number)));
rl.on("close",()=>{
    let t=input[0], idx=1;
    for(let _=0;_<t;_++){
        let n=input[idx++], arr=input.slice(idx,idx+n); idx+=n;
        let res=solve(arr);
        console.log(res.join(" "));
        // evaluation completed
    }
});

## PYTHON

import sys
import collections

# user code comes here

def main():
    data=list(map(int,sys.stdin.read().split()))
    t=data[0]; idx=1
    for _ in range(t):
        n=data[idx]; idx+=1
        arr=data[idx:idx+n]; idx+=n
        res=solve(arr)
        print(*res)
        # evaluation completed

if __name__=="__main__":
    main()
