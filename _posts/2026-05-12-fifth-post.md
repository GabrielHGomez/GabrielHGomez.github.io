---
title: "Update: Wedding and Progress"
date: 2026-05-09 20:30:00 -0500
categories: [Personal, Technical]
tags: [Iris, Aphrodite, leetcode]
---

Post for what I work on this week.

## Leetcode Challenged Completed

This week I was only able to complete 2 leetcode challenged. The recent ones are pretty complicated and I did not have enough time to complete them. I plan on after my wedding I will go back to them, and if I cannot solve them. I will read the answer then attempt to answer the next day. I was able to solve 2 questions. The questions are:
Separate the Digits in an Array (easy): https://leetcode.com/problems/separate-the-digits-in-an-array/description/?envType=daily-question&envId=2026-05-13 

Cyclically Rotating a Grid (medium): https://leetcode.com/problems/cyclically-rotating-a-grid/?envType=daily-question&envId=2026-05-13

## My code "Separate the Digits in an Array"

````cpp
class Solution {
public:
    vector<int> separateDigits(vector<int>& nums) {
        vector<int> result;

        for(int i = 0; i < nums.size();i++){
            string placeholder = to_string(nums[i]);

            for(char ch: placeholder){
                result.push_back(ch-'0');
            }
        }
        return result;
    }
};
````

## My code "Cyclically Rotating a Grid"

````cpp
class Solution {
public:
    vector<vector<int>> rotateGrid(vector<vector<int>>& grid, int k) {
        int top = 0;
        int bottom = grid.size()-1;
        int l = 0;
        int r = grid[0].size()-1;

        while (top < bottom && l < r ){
            int length = bottom - top;
            int width = r - l;

            int perimeter = 2 * length + 2 * width;

            int R = k % perimeter;

            while(R--){
                int tmp = grid[top][l];

                for(int i = l; i < r; i++){
                    grid[top][i] = grid[top][i+1];
                }    

                for(int i = top; i < bottom; i++){
                    grid[i][r] = grid[i+1][r];
                }

                for(int i = r; i > l; i--){
                    grid[bottom][i] = grid[bottom][i-1];
                }

                for(int i = bottom; i > top; i--){
                    grid[i][l] = grid[i-1][l];
                }

                grid[top+1][l]= tmp;
           }
           top++;
           l++;
           bottom--;
           r--;
        }
        return grid;
    }
};
````

## Iris
Weekly Progress:

- Found bugs that I am currently working on by making new examples
- Add .gitignore for those pesky swap files and backups.
- Got rid of stb in the project

A small push to get the .gitignore in my repo, still working to get Iris in a state where I can pull it into new projects

## Aphrodite
Weekly Progress:

- Add shaders
- Working on Texture
- Added .gitignore

Pushed to get the shaders portion into the repo. With textures I will be in a position where I can work on my GLSL

## Hephaestus
Weekly Progress

- Added my dotfiles 
- Add .gitignore to make sure I don't publish sensitive information.

This is just a place to put my dotfiles (tmux,bash, and vim). I will update when I update my own personal files. I also plan on adding a script to install the dotfiles, however, it is a work in progrss since I am not the greatest at bash.

## Progress
I would prefer that I practice my coding more, however, with the wedding coming up I am putting most my time and energy in the wedding. 

I also am learning rust. A small project that I am starting is creating multiple sorting algorithms and running it in rust. Taking a user input to decide which sorting algorithm to use. For fun, the first algorithm I created was BOGO sort. Might possibly make a repo, might not. I have not decided just yet.
