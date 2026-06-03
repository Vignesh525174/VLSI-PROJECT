# VLSI-PROJECT

# Half Adder — Verilog Implementation

## 📌 Project Overview

A **Half Adder** is a basic combinational logic circuit that adds two single-bit binary numbers and produces two outputs: **Sum** and **Carry**.

This project implements a Half Adder using **Verilog HDL** and simulates it using **EDA Playground (Icarus Verilog)**.

---

## 🔧 Tools Used

| Tool | Purpose |

| EDA Playground | Online HDL simulator |
| Icarus Verilog | Verilog compiler & simulator |
| Verilog (SystemVerilog) | Hardware Description Language |

---

## 📐 Logic Design
<img width="893" height="649" alt="Screenshot 2026-06-03 141823" src="https://github.com/user-attachments/assets/ace5c9fe-5198-46d6-a42b-7d32f1054ce8" />


### Boolean Expressions
- **Sum** = A ⊕ B (XOR operation)
- **Carry** = A · B (AND operation)

### Truth Table

| A | B | Sum | Carry |
|---|---|-----|-------|
| 0 | 0 |  0  |   0   |
| 0 | 1 |  1  |   0   |
| 1 | 0 |  1  |   0   |
| 1 | 1 |  0  |   1   |

---

## 📁 File Structure

```
half-adder/
├── design.sv        # Half Adder module
├── testbench.sv     # Testbench to verify all input combinations
└── README.md        # Project documentation
```

---

## 💻 Source Code

### design.sv
```verilog
module half_adder(
    input A,
    input B,
    output Sum,
    output Carry
);
    assign Sum   = A ^ B;   // XOR operation
    assign Carry = A & B;   // AND operation
endmodule
```

### testbench.sv
```verilog
module testbench;
    reg A, B;
    wire Sum, Carry;

    half_adder HA (
        .A(A),
        .B(B),
        .Sum(Sum),
        .Carry(Carry)
    );

    initial begin
        A = 0; B = 0; #10;
        A = 0; B = 1; #10;
        A = 1; B = 0; #10;
        A = 1; B = 1; #10;
        $finish;
    end

    initial begin
        $monitor("A=%b B=%b Sum=%b Carry=%b", A, B, Sum, Carry);
    end
endmodule
```

---

## ✅ Simulation Output

```
A=0 B=0 Sum=0 Carry=0
A=0 B=1 Sum=1 Carry=0
A=1 B=0 Sum=1 Carry=0
A=1 B=1 Sum=0 Carry=1
```

All outputs match the expected truth table. ✅

---

## 👤 Author

**Vignesh R**
- LinkedIn: [linkedin.com/in/vignesh-r-906157206](https://www.linkedin.com/in/vignesh-r-906157206)
- GitHub: https://github.com/Vignesh525174

---

## 📅 Date

June 3, 2026

---

*This is Project 1 of my VLSI Design Engineer learning journey. 🚀*
