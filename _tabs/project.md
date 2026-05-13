---
title: Projects
icon: fas fa-code
order: 4
---

## Iris

**Language**: C++17, Boost.Interprocess Shared Memory Platforms:Linux & Windows
[Github repo]: (https://github.com/GabrielHGomez/Iris)

A single header C++ library for sharing structs between process via shared memory. The hope is to put this project in bigger projects in which I need shared memory by using git fetch in cmake. I am also making this project work with multiple languages (C++, Python, and Rust).

**Writer Example**
````cpp
SharedMemory<Random> random_shm("Random_info", true);

std::random_device rd;
std::mt19937 gen(rd());
std::uniform_int_distribution<int> dist(0,100);

random_shm->random_val = dist(gen);
````

**Reader Example**
````cpp
SharedMemory<Random> random_shm("Random_info", false);

std::cout << "random_val = " << random_shm->random_val << std::endl;
````

**What I am learning** Building project in modules is the main thing I want to learn. I want to make projects where I can "drag and drop" into other project with reusable and generic code.
