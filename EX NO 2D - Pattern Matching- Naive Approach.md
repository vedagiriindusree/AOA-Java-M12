# EX 2D Pattern Matching using Naive Approach.
## DATE:16/11/2025
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12

## Algorithm
1.Start the program. Read the input string text and the substring pattern from the user.

2.Initialize variables: Let n = length of text and m = length of pattern.

3.Slide the pattern over the text: For each position i from 0 to n - m:

Compare the substring of text starting at index i with the pattern.

4.Check for match:

For each character j in the pattern, check if text[i + j] == pattern[j].

If all characters match (j == m), print "Pattern found at index i".

5.End the program. Stop after scanning the entire text.
## Program:
```
/*
Program to implement Reverse a String
Developed by: Vedagiri Indu sree
Register Number: 212223230236
*/

import java.util.Scanner;

public class NaivePatternSearch {
    //Type code here....
    static void search(String text,String pattern){
        int n=text.length();
        int m=pattern.length();
        for(int i=0;i<=n-m;i++){
            int j;
            for(j=0;j<m;j++){
                if(text.charAt(i+j)!=pattern.charAt(j))
                break;
            }
            if(j==m)
                System.out.println("Pattern found at index "+i);
        
    }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input from the user
        //.out.print("Enter the text: ");
        String text = scanner.nextLine();

        //System.out.print("Enter the pattern: ");
        String pattern = scanner.nextLine();

        // Search for pattern in the text
        search(text, pattern);

        scanner.close();
    }
}


```

## Output:
<img width="750" height="253" alt="image" src="https://github.com/user-attachments/assets/bf4724c5-36b3-4295-93be-2b7d2687a5cf" />

## Result:
The program successfully implemented and the expected output is verified.
