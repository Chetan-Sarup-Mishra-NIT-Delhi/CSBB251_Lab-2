# Binary Adders: Theory and Logic

This repository contains the fundamental logic and design principles for **Half Adders** and **Full Adders**, the building blocks of digital arithmetic.

---

## 1. Half Adder

### Theory
A **Half Adder** is a combinational logic circuit that performs the addition of two single-bit binary numbers. It is the simplest form of an adder but has a significant limitation: it does not have an input for a "Carry" from a previous stage.

It produces two outputs:
1.  **Sum (S):** Represents the least significant bit of the addition.
2.  **Carry (C):** Represents the overflow bit.



[Image of half adder circuit diagram and logic gates]


### Truth Table
| Input A | Input B | Sum (S) | Carry (C) |
| :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

### Boolean Expressions
- **Sum:** $S = A \oplus B$ (XOR Gate)
- **Carry:** $C = A \cdot B$ (AND Gate)

---

## 2. Full Adder

### Theory
A **Full Adder** is a digital circuit that adds three bits: two significant bits ($A$ and $B$) and a **Carry-in ($C_{in}$)** from a previous addition. This capability allows Full Adders to be cascaded (connected in series) to add multi-bit binary numbers (e.g., 4-bit or 8-bit ripple carry adders).

A Full Adder is typically constructed using two Half Adders and an OR gate.



### Truth Table
| Input A | Input B | Carry-In ($C_{in}$) | Sum (S) | Carry-Out ($C_{out}$) |
| :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

### Boolean Expressions
- **Sum:** $S = A \oplus B \oplus C_{in}$
- **Carry-Out:** $C_{out} = (A \cdot B) + (C_{in} \cdot (A \oplus B))$

---

## Key Differences

| Feature | Half Adder | Full Adder |
| :--- | :--- | :--- |
| **Inputs** | 2 bits | 3 bits (includes $C_{in}$) |
| **Usage** | Addition of LSB only | Addition of all other bits |
| **Components** | 1 XOR, 1 AND | 2 XOR, 2 AND, 1 OR |
