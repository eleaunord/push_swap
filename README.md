# push\_swap

> Sorting numbers with stacks and constraints. Because `swap_push` would’ve been too easy.

## 📌 Project Overview

The **push\_swap** project is one of the most challenging and algorithmically rich projects at 42. The goal is to sort a stack of integers using two stacks (`a` and `b`) and a very limited set of operations. The tricky part? You have to sort the data using the fewest moves possible.

To solve this, I had to combine algorithmic thinking with efficient C programming, data structure management, and plenty of trial and error.

## 🧠 What I Learned

### Sorting Algorithms & Complexity

This project gave me a much deeper understanding of sorting complexity (O(n), O(n²), etc.) and why some sorting strategies are better than others depending on the input.

I learned how to:

* Analyze and compare time/space complexity.
* Choose between algorithms like radix sort, insertion sort, or quicksort depending on the input size.
* Optimize for specific cases (e.g. sorting 3, 5, or 100 numbers differently).

### 📚 Data Structures

I became very comfortable managing linked lists and stacks in C, as I needed full control over memory and behavior to implement the push\_swap rules.

### Algorithm Design & Optimization

Figuring out the optimal number of operations was the most challenging part. I developed my own scoring system to evaluate the efficiency of each potential move and reduce the total number of operations.

### Debugging & Testing

I wrote extensive custom tests to verify my output with `checker` and compare instruction counts. I also learned how important it is to avoid memory leaks and segmentation faults in a tightly constrained C program.

## 🔧 Project Rules Recap

You're given:

* Stack `a`: a list of unsorted integers.
* Stack `b`: initially empty.
* A limited set of operations (e.g. `sa`, `pb`, `ra`, `rrr`, etc.)

Your program:

* Must output the smallest number of instructions needed to sort stack `a`.
* Must handle input errors (non-integers, duplicates, out-of-bounds values).
* Will be benchmarked for efficiency based on input size (100 and 500 elements).

## ⚠️ Challenges I Faced

### Radix Sort Logic

Radix sort is efficient for large datasets, but implementing it with push\_swap’s limited instructions took some effort. Shifting binary digits while juggling two stacks got messy quickly.

### Special Cases (3 or 5 Numbers)

While sorting 100+ numbers was mostly handled by radix sort, sorting 3 or 5 numbers with the fewest instructions required a totally different approach—like solving a puzzle.

### Memory Management

Dealing with dynamically allocated stacks and avoiding leaks took a lot of debugging. I had to write cleanup functions for every possible failure point in the program.

### Edge Cases

Inputs like already-sorted stacks, reversed stacks, or stacks with just one number needed special handling to avoid unnecessary instructions or errors.

## 🧪 Example

```sh
$ ./push_swap 2 1 3 6 5 8
sa
pb
pb
pb
sa
pa
pa
pa
```

```sh
$ ARG="4 67 3 87 23"; ./push_swap $ARG | ./checker $ARG
OK
```

## 🚀 How to Run

```bash
make
ARG="3 2 1 6 5 4"; ./push_swap $ARG
```

To check the output:

```bash
./push_swap $ARG | ./checker $ARG
```

## 🏁 Final Thoughts

`push_swap` was a serious test of logic, patience, and C skills. It made me understand sorting not just as a concept, but as a challenge that can be approached in many creative ways. Getting a low number of instructions for large inputs was tough, but really rewarding when it finally worked.
