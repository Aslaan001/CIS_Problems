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
        int n; 
        cin >> n;
        vector<int> nums(n);
        for(int i=0;i<n;i++) cin >> nums[i];
        cout << solve(nums) << "\n";
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
        int _t=Integer.parseInt(br.readLine().trim());
        while(_t-->0){
            int n=Integer.parseInt(br.readLine().trim());
            String[] arr=br.readLine().trim().split(" ");
            int[] nums=new int[n];
            for(int i=0;i<n;i++) nums[i]=Integer.parseInt(arr[i]);
            System.out.println(solve(nums));
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
        int* nums=malloc(n*sizeof(int));
        for(int i=0;i<n;i++) scanf("%d",&nums[i]);
        printf("%d\n", solve(nums,n));
        free(nums);
        // evaluation completed
    }
    return 0;
}

## JAVASCRIPT

const readline=require("readline");

// user code comes here


const rl=readline.createInterface({
    input:process.stdin,
    output:process.stdout
});

let input=[];
rl.on("line",line=>input.push(...line.trim().split(/\s+/).map(Number)));
rl.on("close",()=>{
    let t=input[0], idx=1;
    for(let _=0;_<t;_++){
        let n=input[idx++];
        let nums=input.slice(idx,idx+n); idx+=n;
        console.log(solve(nums));
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
        nums=data[idx:idx+n]; idx+=n
        print(solve(nums))
        # evaluation completed

if __name__=="__main__":
    main()
