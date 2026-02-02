# Half Adder and Full Adder Circuit Design Using Logisim

## Aim
To design, simulate, and verify the working of Half Adder and Full Adder circuits using Logisim software and validate their operation through truth tables.

## Materials/Resources Needed

### Software
- **Logisim** (digital logic circuit simulator)
- Compatible with Windows, macOS, and Linux operating systems

### Circuit Components (in Logisim)
- XOR gates
- AND gates  
- OR gates
- Input pins
- Output pins
- Wires/connectors
- Text labels (for documentation)

## Theory

### Half Adder
A Half Adder adds two single-bit binary numbers (A and B) and produces two outputs:

- **Sum (S)**: The result of A XOR B
- **Carry-out (C_out)**: The result of A AND B

**Key Equations:**
```
S = A ⊕ B    (XOR)
C_out = A ∧ B  (AND)
```

**Gates Required:** 2 gates (1 XOR + 1 AND)

### Full Adder
A Full Adder adds three single-bit binary numbers: two inputs (A, B) and a carry-in (C_in). It produces:

- **Sum (S)**: XOR of all three inputs
- **Carry-out (C_out)**: Majority function of inputs

**Key Equations:**
```
S = A ⊕ B ⊕ C_in
C_out = (A ∧ B) ∨ (B ∧ C_in) ∨ (A ∧ C_in)
```

**Gates Required:** 5 gates (2 XOR + 3 AND + 1 OR)

**Implementation Note:** A Full Adder can be constructed using two Half Adders and one OR gate.

### Truth Tables

**Half Adder:**
| A | B | Sum (S) | Carry (C) |
|---|---|---------|-----------|
| 0 | 0 | 0       | 0         |
| 0 | 1 | 1       | 0         |
| 1 | 0 | 1       | 0         |
| 1 | 1 | 0       | 1         |

**Full Adder:**
| A | B | C_in | Sum (S) | Carry (C_out) |
|---|---|------|---------|---------------|
| 0 | 0 | 0    | 0       | 0             |
| 0 | 0 | 1    | 1       | 0             |
| 0 | 1 | 0    | 1       | 0             |
| 0 | 1 | 1    | 0       | 1             |
| 1 | 0 | 0    | 1       | 0             |
| 1 | 0 | 1    | 0       | 1             |
| 1 | 1 | 0    | 0       | 1             |
| 1 | 1 | 1    | 1       | 1             |

## Procedure

### Part A: Half Adder Circuit

1. **Launch Logisim** and create a new project
2. **Add Input Pins:**
   - Select input pins from the toolbar
   - Place two input pins and label them as A and B
3. **Add Logic Gates:**
   - Place one XOR gate for Sum output
   - Place one AND gate for Carry output
4. **Add Output Pins:**
   - Place two output pins and label them as S (Sum) and C (Carry)
5. **Connect Wires:**
   - Connect inputs A and B to both the XOR and AND gates
   - Connect XOR output to Sum pin
   - Connect AND output to Carry pin
6. **Add Labels:** Use text tool to label all components for clarity
7. **Test the Circuit:**
   - Use the "Poke" tool to toggle input values
   - Observe output changes (light green = 1, dark green = 0)
   - Verify all four input combinations match the truth table

### Part B: Full Adder Circuit

1. **Create New Circuit** in the same Logisim project
2. **Add Input Pins:** Place three input pins labeled A, B, and C_in
3. **Method 1 - Using Gates Directly:**
   - Add 2 XOR gates, 3 AND gates, and 1 OR gate
   - Connect first two inputs (A, B) to first XOR and first AND gate
   - Connect output of first XOR with C_in to second XOR (produces Sum)
   - Connect outputs appropriately to produce Carry using AND-OR logic

4. **Method 2 - Using Half Adders (Recommended):**
   - Import the Half Adder circuit as a sub-circuit
   - Connect A and B inputs to first Half Adder
   - Connect Sum output of first Half Adder with C_in to second Half Adder
   - Connect both Carry outputs to an OR gate for final Carry output

5. **Add Output Pins:** Label as S (Sum) and C_out (Carry)
6. **Test the Circuit:** Verify all eight input combinations against the truth table

## Results

### Half Adder Verification
The Half Adder circuit successfully performed binary addition of two single bits. When tested with all possible input combinations:
- Inputs (0,0) produced Sum=0, Carry=0
- Inputs (0,1) and (1,0) produced Sum=1, Carry=0  
- Inputs (1,1) produced Sum=0, Carry=1

All outputs matched the theoretical truth table, confirming correct implementation.

### Full Adder Verification  
The Full Adder circuit successfully performed binary addition of three bits including carry input. Testing validated:
- Correct Sum output for all 8 input combinations
- Proper Carry propagation for multi-bit addition scenarios
- Successful implementation using two Half Adders and one OR gate

The circuit outputs matched the theoretical truth table for all test cases, confirming the design's functionality.

## Key Differences

| Feature | Half Adder | Full Adder |
|---------|------------|------------|
| Inputs | 2 (A, B) | 3 (A, B, C_in) |
| Carry Input | No | Yes |
| Applications | Single-bit addition | Multi-bit addition |
| Gates Required | 2 (XOR + AND) | 5 (2 XOR + 3 AND + OR) |

## Applications
These circuits are fundamental building blocks in arithmetic logic units (ALUs), processors, and computer architecture for performing binary arithmetic operations.

## Conclusion
Both Half Adder and Full Adder circuits were successfully designed and verified using Logisim. The simulations confirmed the theoretical behavior of these digital logic circuits, demonstrating their utility in binary arithmetic operations. The Full Adder's ability to handle carry inputs makes it essential for multi-bit addition in computer systems.
