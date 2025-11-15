## CPP

#include <bits/stdc++.h>
using namespace std;

// user code comes here


int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int t; cin >> t;
    while(t--){
        int n; cin >> n;
        vector<int> arr(n);
        for(int i=0;i<n;i++) cin >> arr[i];
        int k; cin >> k;
        cout << solve(arr,k) << "\n";
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
        int t=Integer.parseInt(br.readLine().trim());
        while(t-->0){
            int n=Integer.parseInt(br.readLine().trim());
            String[] s=br.readLine().trim().split(" ");
            int[] nums=new int[n];
            for(int i=0;i<n;i++) nums[i]=Integer.parseInt(s[i]);
            int k=Integer.parseInt(br.readLine().trim());
            System.out.println(solve(nums,k));
            // evaluation completed
        }
    }
}

## C

#include <stdio.h>
#include <stdlib.h>

// user code comes here

int main(){
    int t; scanf("%d",&t);
    while(t--){
        int n; scanf("%d",&n);
        int* arr=malloc(n*sizeof(int));
        for(int i=0;i<n;i++) scanf("%d",&arr[i]);
        int k; scanf("%d",&k);
        printf("%d\n", solve(arr,n,k));
        free(arr);
        // evaluation completed
    }
    return 0;
}

## JAVASCRIPT

const readline=require("readline");

// user code comes here

const rl=readline.createInterface({input:process.stdin});
let input=[];
rl.on("line",l=> input.push(...l.trim().split(/\s+/)));
rl.on("close",()=>{
    let t=Number(input[0]), idx=1;
    for(let _=0;_<t;_++){
        let n=Number(input[idx++]);
        let arr=input.slice(idx,idx+n).map(Number);
        idx+=n;
        let k=Number(input[idx++]);
        console.log(solve(arr,k));
        // evaluation completed
    }
});

## PYTHON

import sys

# user code comes here

def main():
    data=list(map(int,sys.stdin.read().split()))
    t=data[0]; idx=1
    for _ in range(t):
        n=data[idx]; idx+=1
        arr=data[idx:idx+n]; idx+=n
        k=data[idx]; idx+=1
        print(solve(arr,k))
        # evaluation completed

if __name__=="__main__":
    main()
