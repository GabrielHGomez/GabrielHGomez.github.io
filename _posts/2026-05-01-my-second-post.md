---
title: "Daily Log: Leetcode and Iris Progress"
date: 2026-05-01 20:30:00 -0500
categories: [Technical]
tags: [leetcode, iris]
---

Post for what I worked on today.

## Leetcode Daily Challenge

Today daily challenge was extremly difficult to understand.
Here is 5/1/2026 challenge: https://leetcode.com/problems/rotated-digits/?envType=daily-question&envId=2026-05-02

## My code

````cpp
class Solution {
public:
    int rotatedDigits(int n) {
        int count = 0;

        for (int x = 1; x <= n; x++) {
            if (isGoodNumber(x)) {
                count++;
            }
        }
        return count;
    }

    bool isGoodNumber(int x) {
        bool digitChanged = false;

        while (x > 0) {
            int digit = x % 10;
            if (digit == 3 || digit == 4 || digit == 7) {
                return false;
            }

            if (digit == 2 || digit == 5 || digit == 6 || digit == 9) {
                digitChanged = true;
            }
            x /= 10;
        }
        return digitChanged;
    }
};
````
{: file="solution.cpp" }

## Iris

Today progress:

- Started working on mutex in the shared memory.
- Adding GTest

No push yet, however, hopefully I get to push during the weekend to Iris and Aphrodite.

## Tommorow 

Complete tomorrow LeetCode, implement more on the mutex functionality, maybe work on aphrodite.
