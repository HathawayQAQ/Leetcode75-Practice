# Two Pointers: 283. Move Zeroes

## Problem ##
https://leetcode.com/problems/move-zeroes/description/?envType=study-plan-v2&envId=leetcode-75

## Problem Description ##
> Given two strings s and t, return true if s is a subsequence of t, or false otherwise.
>
> A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., "ace" is a subsequence of "abcde" while "aec" is not).

> Example 1:
> 
> Input: s = "abc", t = "ahbgdc"
> Output: true
> Example 2:
> 
> Input: s = "axc", t = "ahbgdc"
> Output: false

## First Solution - Python3 ##
``` class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        if len(s) == 0:
            return True
        n = 0
        for i in range(len(t)):
            if t[i] == s[n]:
                n += 1
            if n == len(s):
                return True
        
```

## Improved Solution ##

``` class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        if len(s) > len(t):
            return False

        if len(s) == 0 or len(t) == 0:
            return True

        i = 0
        j = 0

        while i < len(s) and j < len(t):
            if s[i] == t[j]:
                i += 1
                j += 1
                if i == len(s):
                    return True
            else:
                j += 1

        return False
```
