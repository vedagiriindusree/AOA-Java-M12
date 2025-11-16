
# EX 2B Jump Game using Greedy Algorithm.
## DATE:16/11/2025
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1.Start the program. Read the size of the array n and input the array elements nums[], where each element represents the maximum jump length from that position.

2.Handle base cases:

If n <= 1, return 0 (already at the end).

If nums[0] == 0, return -1 (cannot move forward).

3.Initialize variables:

jumps = 0 → counts total jumps

currentReach = 0 → current range reachable with current jump

maxReach = 0 → farthest position reachable at any time

4.Iterate through the array (from index 0 to n-2):

Update maxReach = max(maxReach, i + nums[i]).

If i == currentReach, increment jumps and set currentReach = maxReach.

If currentReach >= n - 1, stop and return jumps.

If currentReach == i, return -1 (stuck, can’t progress).

5.Display the result: Print the minimum number of jumps to reach the last index (or -1 if unreachable) and stop the program.  

## Program:
```
/*
Program to implement Reverse a String
Developed by:Vedagiri Indu Sree
Register Number: 212223230236
*/
import java.util.Scanner;

public class MinJumpToEnd {

    // Function to return minimum jumps to reach end
    public static int minimumJumps(int[] nums) {
        // Type Your Code Here.
        int n=nums.length;
        if(n<=1) return 0;
        if(nums[0]==0)return -1;
        int jumps=0;
        int currentReach=0;
        int maxReach=0;
        for(int i=0;i<n-1;i++){
            maxReach=Math.max(maxReach,i+nums[i]);
            if(i==currentReach){
                jumps++;
                currentReach=maxReach;
                if(currentReach>=n-1)
                return jumps;
                if(currentReach==i)
                return -1;
            }
        }
        return -1;
    }

    // Main method to handle input and output
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Number of elements
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}


```

## Output:
<img width="844" height="267" alt="image" src="https://github.com/user-attachments/assets/5427d836-6e13-4d6b-9bb9-5afb5d7ef158" />

## Result:
The program successfully implemented and the expected output is verified.
