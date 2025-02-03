# Performance Issues with std::vector<bool> in C++

This repository demonstrates a common performance pitfall in C++ when using `std::vector<bool>`.  `std::vector<bool>` is a specialized container that uses bit packing to save memory, which is usually the reason one would use it. However, this optimization comes at the cost of performance overhead, as each boolean requires bit manipulation to be accessed, leading to a performance slowdown compared to the normal `std::vector<int>` or `std::vector<char>`. The performance impact might be negligible when the boolean vector is small, but as the size increases, the overhead becomes significant.   This can lead to unexpected slowdowns or even incorrect results in algorithms not designed for this specific implementation.

The example code shows how to reproduce the performance issue and provides a solution using `std::vector<char>` instead to showcase a better performing alternative.

## Reproduction

To reproduce the performance issue, compile and run the `bug.cpp` file.