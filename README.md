# Ford-Johnson Merge-Insert Sort

## Overview

PmergeME is a C++98 implementation of the Ford-Johnson merge-insert sort algorithm, also known as the merge-insertion sort. This project demonstrates the algorithm's efficiency by sorting sequences of positive integers using two different STL containers (`std::vector` and `std::deque`) and comparing their performance.

## Algorithm Description

The Ford-Johnson algorithm is a comparison-based sorting algorithm that aims to minimize the number of comparisons needed to sort a sequence. It works by:

1. **Pairing elements** and sorting them within pairs
2. **Recursively sorting** the larger elements of each pair
3. **Inserting remaining elements** using binary search with a specific insertion order based on Jacobsthal numbers

The algorithm is notable for being comparison-optimal for small sequences and historically important in the study of sorting algorithms.

## Features

- **Dual Container Implementation**: Sorts using both `std::vector` and `std::deque` containers
- **Performance Comparison**: Measures and displays timing and operation counts for both containers
- **Input Validation**: Comprehensive validation of command-line arguments
- **Template-Based Design**: Efficient template implementation in `PmergeME.tpp`
- **C++98 Compliance**: Full compatibility with the C++98 standard

## Project Structure

```
├── main.cpp          # Main program entry point
├── PmergeME.cpp      # Class implementation
├── PmergeME.hpp      # Class declaration and interface
├── PmergeME.tpp      # Template method implementations
├── Makefile          # Build configuration
└── README.md         # This file
```

## Implementation Details

### Key Components

- **Input Validation**: Checks for positive integers, duplicates, and valid format
- **Jacobsthal Sequence**: Uses Jacobsthal numbers to determine optimal insertion order
- **Binary Search**: Employs binary search for efficient element insertion
- **Performance Tracking**: Measures execution time and operation counts
- **Template Design**: Generic implementation works with different container types

### Algorithm Complexity

- **Time Complexity**: O(n log n) average case, with fewer comparisons than traditional merge sort for small inputs
- **Space Complexity**: O(n) auxiliary space
- **Comparison Count**: Approaches the theoretical minimum for small sequences

## Error Handling

The program handles various error conditions:

- **Invalid Arguments**: Non-numeric inputs, negative numbers, or zero
- **Duplicate Numbers**: Prevents sorting sequences with repeated values
- **Integer Overflow**: Validates that numbers fit within integer range
- **Empty Input**: Requires at least one number to sort

## Technical Requirements

This project adheres to 42 School's C++ module requirements:

- **C++98 Standard**: No modern C++ features used
- **Orthodox Canonical Form**: Proper constructor, destructor, copy constructor, and assignment operator
- **No STL Algorithms**: Custom implementation without using STL sorting functions
- **Memory Management**: No memory leaks or undefined behavior
- **Compilation**: Compiles with `-Wall -Wextra -Werror` flags

## Make Targets

```bash
make        # Build the project
make clean  # Remove object files
make fclean # Remove object files and executable
make re     # Rebuild everything
```

## References

- Ford, L.R., & Johnson, S.M. (1959). A Tournament Problem. The American Mathematical Monthly, 66(5), 387-389.
- Knuth, D.E. (1998). The Art of Computer Programming, Volume 3: Sorting and Searching.

---
## Building and Running

### Build

```bash
make
```

### Usage

```bash
./PmergeME <Not duplicate Integers>
```

#### Examples

```bash
# Sort a sequence of numbers
./PmergeME 3 5 9 7 4

# Sort larger sequences
./PmergeME 1 4 2 8 5 3 6 7

# The program accepts any number of positive integers
./PmergeME 42 17 3 28 91 55 12 73
```

### Expected Output

The program displays:
1. **Before**: The original unsorted sequence
2. **After**: The sorted sequence
3. **Timing Information**: Processing time for both vector and deque implementations
4. **Operation Counts**: Number of operations performed by each container

Example output:
```
Before: 3 5 9 7 4
After:  3 4 5 7 9
Time to process a range of 5 elements with std::vector : 0.000123 us
Time to process a range of 5 elements with std::deque  : 0.000098 us
Vector operations: 42
Deque operations: 38
```
