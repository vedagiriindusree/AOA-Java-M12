
# EX 2E Pattern Matching using KMP Algorithm.
## DATE:16/11/2025
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1.Start the program. Read the input string s from the user and preprocess it by inserting special characters (#) between each letter and at both ends (^ at start and $ at end) to handle even-length palindromes uniformly.

2.Initialize variables:

cen = 0 → current center of palindrome

r = 0 → right boundary of current palindrome

p[] → array to store palindrome radius for each character

3.Iterate through each character in the preprocessed string:

Find mirror position mir = 2 * cen - i.

If i < r, set p[i] = min(r - i, p[mir]).

Expand palindrome centered at i while matching characters on both sides.

If the palindrome expands beyond r, update cen = i and r = i + p[i].

4.Find the longest palindrome:

Traverse array p[] to find the maximum radius (maxlen) and its center (cur).

Compute the starting index in the original string as (cur - maxlen) / 2.

5.Display the result: Extract the substring from the original string using the computed start and length, print the Longest Palindromic Substring, and stop the program..   

## Program:
```
/*
Program to implement Reverse a String
Developed by:Vedagiri Indu Sree
Register Number: 212223230236  
*/
import java.util.Scanner;

public class Solution {
    public static String preprocess(String s)
    {
        StringBuilder str=new StringBuilder("^");
        int n=s.length();
        for(int i=0;i<n;i++)
        {
            str.append("#").append(s.charAt(i));
        }
        str.append("#$");
        return str.toString();
    }
    public String longestPalindrome(String s) {
        //Type code here...
        String ch=preprocess(s);
        int n=ch.length();
        int cen=0,r=0,i;
        int[] p=new int[n];
        for(i=1;i<n-1;i++)
        {
            int mir=2*cen-i;
            if(i<r)
            {
                p[i]=Math.min(r-i,p[mir]);
            }
            else
            {
                p[i]=0;
            }
            while(ch.charAt(i+1+p[i])==ch.charAt(i-1-p[i]))
            {
                ++p[i];
            }
            if(i+p[i]>r)
            {
                cen=i;
                r=i+p[i];
            }
        }
        int maxlen=0,cur=0;
        for(i=1;i<n-1;i++)
        {
            if(p[i]>maxlen)
            {
                maxlen=p[i];
                cur=i;
            }
        }
        int st=(cur-maxlen)/2;
        return s.substring(st,st+maxlen);
    }

    // Main method for user input
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        //System.out.println("Enter a string:");
        String input = scanner.nextLine();

        Solution sol = new Solution();
        String result = sol.longestPalindrome(input);

        System.out.println("Longest Palindromic Substring: " + result);
        scanner.close();
    }
}


```

## Output:
<img width="810" height="193" alt="image" src="https://github.com/user-attachments/assets/6a17d94d-be93-4784-8cf3-820f8318b389" />

## Result:
The program successfully implemented and the expected output is verified.
