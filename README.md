# Go Race Condition Example

This repository demonstrates a classic race condition in Go.  Incrementing a shared variable from multiple goroutines without using synchronization primitives (like mutexes) can result in unexpected and inconsistent values. The `bug.go` file shows the problematic code, while `bugSolution.go` offers a corrected version using a mutex.

## Bug Description
The program starts 10 goroutines concurrently incrementing a shared variable. Without proper synchronization this will lead to a lower value than 10. 

## Solution
The solution uses a mutex to protect the shared variable `count`, ensuring that only one goroutine can access and modify it at any given time.