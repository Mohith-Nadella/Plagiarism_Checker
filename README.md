# Plagiarism Checker in C++

## Overview

This project is a **two-phase plagiarism detection system** written in C++ using object-oriented principles, STL containers, and multithreading. It can detect **global**, **paraphrased**, and **patchwork** plagiarism in both pairwise and large-scale submission scenarios.

---

##  Features

- **Two-phase Detection Strategy**:
  -  **Phase 1**: Compares two code submissions using:
    - Rolling Hash (Rabin-Karp)
    - Dynamic Programming (to detect longest common subsequences/blocks)
    - 2D Segment Trees (to locate common code fragments efficiently)
  -  **Phase 2**: Handles large-scale batches of submissions using:
    - `std::thread` for parallelism
    - `std::mutex` and `std::condition_variable` for thread safety
    - Efficient plagiarism detection using rolling hash

- **Plagiarism Types Handled**:
  -  Global plagiarism (entire code copied)
  -  Paraphrased plagiarism (renamed variables, reordered blocks)
  -  Patchwork plagiarism (copied from multiple sources)

- **Efficient Data Structures**:
  - Utilizes `unordered_map`, `unordered_set`, `queue`, and other STL containers to manage tokens, matches, and thread tasks efficiently.

---

##  Technologies Used

- **Language**: C++17
- **Libraries**:
  - STL (`vector`, `unordered_map`, `unordered_set`, `queue`)
  - Multithreading (`<thread>`, `<mutex>`, `<condition_variable>`)
- **Algorithms**:
  - Rolling Hashing
  - Dynamic Programming
  - Segment Trees (2D)

---


