# LeetCode 7: Reverse Integer (C++ Solution)

Hey there! This is my solution to the *Reverse Integer* problem on LeetCode. 

## 🧠 The Challenge

The goal is pretty straightforward: take a 32-bit signed integer and reverse its digits (e.g., 123 becomes 321, -456 becomes -654). 

The real catch here is the *32-bit limit constraint*. We are explicitly told that we cannot use 64-bit data types like long or long long to easily bypass overflow. The code has to actively watch out for the boundary lines (2,147,483,647 and -2,147,483,648) before doing the math.

## 🚀 How I Solved It

Instead of turning the number into a string (which is slow and memory-heavy), I handled it purely with math:
1. Used % 10 to peel off the last digit of the number.
2. Used / 10 to shrink the original number down.
3. Multiplied my running total by 10 and added the new digit.

*The Crucial Part (Handling Overflow):*
Right before multiplying the running total by 10, the code checks if the next step will push it past INT_MAX or INT_MIN. If it looks like it's going to overflow, it safely stops and returns 0.
