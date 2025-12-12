# PLC Motor Control Project
### Motor Start/Stop with Latching, Overload Protection, and Level High Interlock  
**Designed and simulated using PLC Ladder Simulator 2**

---

## 🔥 Project Overview
This project implements a **PLC-based motor starter** using standard industrial ladder logic principles.  
The circuit includes:

- Start/Stop pushbutton control  
- Seal-in **latching mechanism** using internal bit `B0:0/0`
- Motor output control using `O0:0/0`
- Safety interlocks:
  - Stop (NC)
  - Overload relay (NC)
  - Level High sensor (NC)
- Full testing for all fault and safety conditions

This logic replicates a real **DOL (Direct-On-Line) motor starter** widely used in industries.

---

## 📌 Objectives
- Understand PLC ladder logic fundamentals  
- Implement Start/Stop motor control  
- Design a self-latching (seal-in) circuit  
- Integrate overload and level interlocks for safety  
- Test the circuit under normal and abnormal conditions  

---

## 🧠 Ladder Diagram Overview

### **Rung 1 — Latching Logic**
- Start (`I0:0/0`) energizes internal relay `B0:0/0`
- `B0:0/0` is used in parallel for sealing (latching)

### **Rung 2 — Motor Output with Interlocks**
Motor runs only if:
- Latch bit `B0:0/0` is active  
- Stop (`I0:0/1`) is closed  
- Overload (`I0:0/2`) not tripped  
- LevelHigh (`I0:0/3`) is normal  
- Then output `(O0:0/0)` energizes  

---

## 🛠 I/O Configuration

| Function        | Address   | Type             |
|-----------------|-----------|------------------|
| Start Button    | I0:0/0    | Normally Open    |
| Stop Button     | I0:0/1    | Normally Closed  |
| Overload Relay  | I0:0/2    | Normally Closed  |
| Level High      | I0:0/3    | Normally Closed  |
| Latch Bit       | B0:0/0    | Internal Memory  |
| Motor Output    | O0:0/0    | Output Coil      |

---

## 🧪 Testing & Validation

### ✔ Normal Run
- Start pressed → motor turns ON  
- Start released → motor remains ON (latched)

### ✔ Stop Operation
- Stop pressed → motor turns OFF immediately  

### ✔ Overload Trip
- I0:0/2 opened → motor shuts down for safety  

### ✔ Level High Interlock
- I0:0/3 opened → motor cannot start  

---

## 📸 Screenshots

- circuit
  ![circuit](https://github.com/user-attachments/assets/c097cd02-ace2-4a2e-8d93-ec7566ee4d02)

- Motor ON state
  ![start](https://github.com/user-attachments/assets/6f9f6a06-ddd2-45ea-ac58-1e3b0c947923)

- Overload test
  ![Overload](https://github.com/user-attachments/assets/54943dc7-d787-4eb9-b8e3-1cba00b47900)

- LevelHigh block test
  ![LevelHigh](https://github.com/user-attachments/assets/1779c40e-494d-40b2-a9ed-83bf6337f44b)


---

## 📄 Project Summary
This project demonstrates a complete **industrial motor-start control** system using PLC ladder logic.  
It includes latching logic, emergency shutdown paths, and safety interlocks — making it suitable for real-world automation applications.

---

## 👨‍💻 Author
**Lokesh Goud**  
Electrical Engineering  
(Add your email or LinkedIn if you want)

---

## 📂 Repository Structure
