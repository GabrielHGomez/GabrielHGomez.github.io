---
title: "Daily Log: Leetcode and Aphrodite Progress"
date: 2026-05-02 20:30:00 -0500
categories: [Technical]
tags: [leetcode, Aphrodite]
---

Post for what I worked on today.

## Leetcode Daily Challenge

Today daily challenge was simple and a freshener on string manipulation. Sadly this was not the most effective way to approach this problem. After solving it, I viewed the most effective answer, and it was really interesting to understand the logic. Essentailly, every possible rotation of a string appears in a substring that is resulted from s + s. I went with a solution that I feel is more intuitive, by rotating s and see if it matches.
Here is 5/2/2026 challenge: https://leetcode.com/problems/rotate-string/description/?envType=daily-question&envId=2026-05-03

## My code

````cpp
class Solution {
public:
    bool rotateString(string s, string goal) {
        if(s.size() != goal.size())
        {
            return false;
        }
        for( int i = 0; i < s.length(); i++){
            s = s.substr(1) + s[0];
            if(s == goal){
                return true;
            }
        }
        return false;  
    }
};
````
{: file="solution.cpp" }

## Aphrodite

Today progress:

- Completed creating a window

I did a push to have a point where I can return to.

## Tommorow

Complete tomorrow leetcode, then possibly work on Iris. Possibly work on Aphrodite since it is more enjoyable.
