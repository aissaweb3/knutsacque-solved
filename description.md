# Quaternion Challenge Write-Up

## Overview
This challenge is based on **quaternions**, which are essentially points in 4D space. It takes a text message, turns it into quaternions, performs some math operations with randomly generated quaternions, and outputs a result. The goal is to reverse this process to recover the original message.

The code is in the sageMath programming language which is build on python and is very helpful in math

---

## What Are Quaternions?
Quaternions are mathematical objects with four components:
- **Real part (1)**
- **Imaginary parts (i, j, k)**

They can be written like this:
```
q = a + b*i + c*j + d*k
```
Where:
- `a, b, c, d` are numbers.
- `i, j, k` are perpendicular directions in 4D space.

---

## How the Challenge Works

### 1. Converting the Message
The input is a text message of size `4n` bytes (e.g., `irisctf{...}`).

The text is divided into chunks of 4 bytes, and each chunk is mapped to a quaternion:
```
q = x*1 + y*i + z*j + w*k
```
Here:
- `x, y, z, w` are the byte values from the text.

Now, we have an array of quaternions, let’s call it `msg`.

### 2. Generating Random Quaternions
A second array of quaternions, `A`, is generated. Each quaternion in `A` has random coefficients for `1, i, j, k`.

### 3. Multiplication and Summation
Each quaternion in `msg` is multiplied by the corresponding quaternion in `A`. All these results are then summed together to get a final quaternion `sm`.

Mathematically:
```
sm = (msg[0] * A[0]) + (msg[1] * A[1]) + ... + (msg[n] * A[n])
```

At the end, you’re given:
- The array `A` (random quaternions)
- The result `sm` (sum of all the multiplications)

But the original message (`msg`) is missing, and that’s what you’re supposed to find.

---

### My Only Idea: Brute Force
The only thing I could think of was trying every possible combination of `msg`, but that’s not feasible given the size of the numbers involved. You’d need absurd computing power.
This idea was dirived even more the hint: the number of possible bytes used in the flag is only 29, which could be much of a help.

---

## Conclusion
This was a super interesting challenge, and I learned a lot about quaternions and their properties. But yeah, I couldn’t solve it. If you’ve got any smart ideas or approaches, hit me up – I’m curious to see how someone else would tackle it!

