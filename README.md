# Efficient-Quantum-Modular-Arithmetics-Paper-to-Qiskit

# Quantum Modular Arithmetic Operators in Qiskit
### *Based on the methods presented in* **“Modular Quantum Operators for Cryptographic Applications in the ISQ Era”**  
📄 Reference: https://arxiv.org/abs/2311.08555

---

## 📌 Overview

This repository provides a **Qiskit implementation** of quantum modular arithmetic operators described in the research paper  
**“Modular Quantum Operators for Cryptographic Applications in the ISQ Era.”**

As quantum hardware progresses through the **Intermediate-Scale Quantum (ISQ)** era, efficient modular arithmetic becomes essential for developing advanced quantum algorithms—particularly in **quantum cryptography** and **number-theoretic computations**.

---

## 🔬 Implemented Operators

### **Auxiliary Foundations**
- **Quantum Fourier Transform (QFT)**  
- **Quantum Fourier Adder (Sum(k))**

---

## ➕ Modular Adders

### **1. Inplace Modular Quantum–Classical Adder**

Implements:

$$
\text{Add}_{\text{in}}(k,N)\|a\rangle \\rightarrow\ |a + k \bmod N\rangle
$$

Includes modular wrap-around detection via auxiliary qubits.

---

### **2. Outplace Modular Quantum–Classical Adder**

$$
\text{Add}_{\text{out}}(k,N)\|a\rangle|0\rangle \\rightarrow\ |a\rangle\|a + k \bmod N\rangle
$$

---

### **3. Inplace Modular Quantum–Quantum Adder**

$$
\text{Add}_{\text{in}}(N)\|a\rangle\|b\rangle \\rightarrow\ |a\rangle\|a + b \bmod N\rangle
$$

Uses QFT-based controlled additions.

---

### **4. Outplace Modular Quantum–Quantum Adder**

$$
\text{Add}_{\text{out}}(N)\|a\rangle\|b\rangle\|0\rangle \\rightarrow\ |a\rangle\|b\rangle\|a + b \bmod N\rangle
$$

---

## ✖ Modular Multipliers

### **5. Outplace Modular Quantum–Classical Multiplier**

$$
\text{Mult}_{\text{out}}(k,N)\|a\rangle\|b\rangle \\rightarrow\ |a\rangle\|b + ka \bmod N\rangle
$$

---

### **6. Inplace Modular Quantum–Classical Multiplier**

$$
\text{Mult}_{\text{in}}(k,N)\|a\rangle \\rightarrow\ |ka \bmod N\rangle
$$

---

### **7. Outplace Modular Quantum–Quantum Multiplier**

$$
\text{Mult}_{\text{out}}(N)\|a\rangle\|b\rangle\|0\rangle \\rightarrow\ |a\rangle\|b\rangle\|ab \bmod N\rangle
$$

---

### **8. Inplace Modular Quantum–Quantum Multiplier**

$$
\text{Mult}_{\text{in}}(N)\|a\rangle\|b\rangle \\rightarrow\ |a\rangle\|ab \bmod N\rangle
$$

*Due to the nature of this multiplier, This was not converted or computed at this time

---

## 🚀 Modular Exponential Operator

### **9. Modular Exponential (Outplace)**  
Fundamental to Shor’s algorithm:

$$
\text{Exp}(a,N)\|x\rangle\|1\rangle\|0\rangle \\rightarrow\ |x\rangle\|a^{x} \bmod N\rangle\|0\rangle
$$

Constructed using controlled modular multipliers and precomputed values:

$$
a^{2^i} \bmod N
$$

