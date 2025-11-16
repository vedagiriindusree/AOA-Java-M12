# EX 2C Job Sequencing using Greedy Approach
## DATE:16/11/2025
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm
1. Input: Read the number of jobs n. For each job, read: id → unique job identifier deadline → latest time by which the job should be completed profit → profit gained if the job is completed before or on its deadline
2. Sort Jobs by Profit: Sort all jobs in descending order of profit (highest profit first). This ensures we pick the most profitable jobs before less profitable ones.
3. Find the Maximum Deadline: Determine the largest deadline among all jobs (maxDeadline). This helps define the number of available time slots.
4. Initialize Scheduling Slots: Create a boolean array slot[maxDeadline + 1], where each index represents a time slot. Initially, all slots are false (unoccupied). Initialize counters: jobsDone = 0 → total number of jobs scheduled totalProfit = 0 → total profit earned
5. Schedule the Jobs: For each job in sorted order: Check from its deadline slot backward (to schedule it as late as possible). If an empty slot (slot[j] == false) is found: Mark it as occupied (slot[j] = true). Increment jobsDone. Add the job’s profit to totalProfit. Break (move to next job). 6.Output: Return {jobsDone, totalProfit}. Print the number of jobs scheduled and total profit obtained.   

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vedagiri Indu Sree
Register Number:212223230236
import java.util.*;

public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {
        // Type Your Code Here.
        Arrays.sort(jobs,(a,b)->b.profit-a.profit);
        int maxDeadline=0;
        for (Job job:jobs){
            maxDeadline =Math.max(maxDeadline,job.deadline);
        }
        boolean[] slot=new boolean[maxDeadline+1];
        int jobsDone=0,totalProfit=0;
        for(Job job:jobs){
            for(int j=job.deadline;j>0;j--){
                if(!slot[j]){
                    slot[j]=true;
                    jobsDone++;
                    totalProfit+=job.profit;
                    break;
                }
            }
        }
        return new int[]{jobsDone,totalProfit};
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}

*/
```

## Output:
<img width="368" height="421" alt="image" src="https://github.com/user-attachments/assets/69e1ec87-ed73-4f93-b5b7-e81c219e3f54" />

## Result:
The program successfully implemented and the expected output is verified.
