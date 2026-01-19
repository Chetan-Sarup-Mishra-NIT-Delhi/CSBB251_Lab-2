Half Adder and Full Adder Fundamentals
This repository covers the foundational digital logic circuits used for binary addition: Half Adder and Full Adder. These are essential building blocks in arithmetic logic units (ALUs), processors, and computer architecture.

Half Adder Theory
A Half Adder adds two single-bit binary numbers (A and B) and produces two outputs:

Sum (S): The result of A XOR B

Carry-out (C_out): The result of A AND B

Key Equations:

text
S = A ⊕ B    (XOR)
C_out = A ∧ B  (AND)

Full Adder Theory
A Full Adder adds three single-bit binary numbers: two inputs (A, B) and a carry-in (C_in). It produces:

Sum (S): XOR of all three inputs

Carry-out (C_out): Majority function of inputs

Key Equations:

text
S = A ⊕ B ⊕ C_in
C_out = (A ∧ B) ∨ (B ∧ C_in) ∨ (A ∧ C_in)
Block Diagram:

text
A ─────┬─────┬───── XOR ──── XOR ──── S
       │     │                │
       AND   AND              │
       │     │                │
B ─────┼─────┼───── XOR ──────┼───── C_out
       │     │      (C_in)    │
       AND              OR ───┘
       │
C_in ──┘
Full Adder Truth Table
A	B	C_in	Sum (S)	Carry (C_out)
0	0	0	0	0
0	0	1	1	0
0	1	0	1	0
0	1	1	0	1
1	0	0	1	0
1	0	1	0	1
1	1	0	0	1
1	1	1	1	1
Key Differences
Feature	Half Adder	Full Adder
Inputs	2 (A, B)	3 (A, B, C_in)
Carry Input	No	Yes
Applications	Single-bit addition	Multi-bit addition
Gates Required	2 (XOR + AND)	5 (2 XOR + 3 AND + OR)
