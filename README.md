# ARM_Prep
# Day 1: RISC vs CISC + Basic idea + History of ARM

## Part 1: What is CISC?

**CISC = Complex Instruction Set Computer**  
A CPU design that uses **many complex instructions**, some of which may take **multiple cycles**.

### Key Features of CISC:

- Large instruction set (e.g., 200+ instructions)
- One instruction can do **multiple things** (e.g., load + add + store)
- Fewer registers
- Hardware is **complex and power-hungry**

### Example Instructions (CISC – x86):

```asm
MOV AX, [BX]    ; Move from memory to AX directly  
ADD AX, 10      ; Add 10 to AX
```
### Disadvantages of CISC:

- More complex CPU design  
- Slower execution for some instructions  
- Harder to pipeline

## Part 2: What is RISC?

**RISC = Reduced Instruction Set Computer**  
A CPU design that uses a **small set of simple instructions** that execute very fast.

### Key Features of RISC:
- Each instruction takes **1 clock cycle** to execute 
- Focuses on **simplicity and speed**
- Uses **many general-purpose registers**
- Fewer instruction formats → **easier decoding**
- **Load/Store architecture** → only `LOAD` and `STORE` access memory

### Example Instructions (RISC):
```asm
MOV R0, #5      ; Load 5 into R0  
ADD R1, R0, #2  ; Add 2 to R0 and store in R1  
STR R1, [R2]    ; Store R1 value into memory pointed by R2
```
### Advantages of RISC:
```
Q) What is the main advantage of RISC architecture?

- Faster execution (due to simple instructions)
- Easier pipelining
- Low power consumption
- Simple hardware → cheaper
```

### Part 3: RISC vs CISC – Comparison Table
```
Q)What is the difference between RISC and CISC?

| Feature                  | RISC (ARM)             | CISC (x86)              |
|--------------------------|------------------------|--------------------------|
| Instruction Set          | Small and simple       | Large and complex        |
| Clock Cycles per Instr.  | Mostly 1               | Multiple                 |
| Memory Access            | Only by load/store     | Can access during ALU ops|
| Register Usage           | More general registers | Fewer registers          |
| Power Consumption        | Low                    | High                     |
| Code Size                | Larger (more lines)    | Smaller                  |
| Execution Speed          | High                   | Moderate                 |
| Used In                  | Mobiles, Embedded      | PCs, Laptops             |
```
## Part 4: 1.What is a ARM?
```
- **ARM** stands for **Advanced RISC Machine**  
- It is a **RISC-based processor architecture**  
- Created by a UK company named **ARM Holdings**  
- **ARM Holdings licenses** the design, doesn't manufacture chips. 

**Examples of users**: Apple, Samsung, Qualcomm all use ARM cores.
```
### 2.Where is ARM Used?
```
| Device           | Example                      | ARM Chip             |
|------------------|------------------------------|----------------------|
| Smartphones      | iPhone, Samsung Galaxy       | Cortex-A             |
| Embedded Systems | Smartwatch, Fitness bands    | Cortex-M             |
| Automotive       | Car ECU                      | Cortex-R             |
| IoT Devices      | Smart bulb, WiFi switches    | Cortex-M0/M4         |
 
```
### 3.Why is ARM so Popular?
```
- Low power usage  
- High performance 
- Small size → fits in embedded devices  
```

### 4.History of ARM

| Year        | Event                                                  |
|-------------|--------------------------------------------------------|
| 1983        | ARM project started by Acorn Computers for BBC Micro   |
| 1985        | First ARM processor: ARM1                              |
| 1990        | ARM Holdings Ltd. formed                               |
| 1993–2000   | ARM7/ARM9 dominate embedded devices                    |
| 2004        | Cortex series launched (M, A, R)                       |
| 2010        | ARM becomes dominate in smartphones                    |
| 2020        | Apple shifts Macs to ARM-based M1 chip                 |
| 2021+       | ARM enters AI, ML, automotive                          |

# Day 2: ARM Family Overview (ARM7, ARM9, Cortex-A / M / R)

## ARM Architecture Family Tree

ARM's processor families have evolved in three major stages:

1. **Classic ARM** (ARM7, ARM9, ARM11)
2. **Cortex Series** (Cortex-M, Cortex-R, Cortex-A)
3. **Neoverse** (For cloud/server/datacenter)


## 1. ARM7 Family

- One of the most successful early cores
- Based on ARMv4T architecture
- 32-bit RISC architecture
- No cache or MMU (Memory Management Unit)
- Used in early mobile phones, low-end microcontrollers

**Used In**:
- Nokia feature phones
- LPC2148 (NXP microcontroller)
- Low-end embedded systems

## 2. ARM9 Family

- Improvement over ARM7
- Based on ARMv5TE architecture
- Supports cache, MMU → used for embedded Linux
- Faster and more capable

**Used In**:
- GPS devices
- Routers
- Set-top boxes
- Entry-level smartphones (2005–2010)

## 3. Cortex Series (ARMv7, ARMv8, ARMv9)

ARM divided this into 3 sub-families for targeted applications:

### Cortex-M Family – For Microcontrollers

- Optimized for real-time and embedded systems
- Low power, simple design
- ARMv7-M and ARMv8-M architecture
- NVIC, SysTick, and easy interrupt handling

#### Common Cores:
| Core       | Use Case                        |
|------------|---------------------------------|
| Cortex-M0  | Ultra-low power                 |
| Cortex-M3  | General purpose MCU             |
| Cortex-M4  | DSP + MCU (with FPU)            |
| Cortex-M7  | High-performance MCU            |
| Cortex-M33 | Secure IoT (TrustZone support)  |

**Used In**:
- STM32, NXP LPC, TI Tiva
- Smart home devices, wearables, sensors

### Cortex-R Family – For Real-Time Applications

- High performance + real-time responsiveness
- ARMv7-R architecture
- Includes Tightly Coupled Memory (TCM)
- Deterministic behavior and fault tolerance

**Used In**:
- Automotive (ABS, engine control)
- Industrial control systems
- HDD/SSD controllers

### Cortex-A Family – For Application Processors

- Supports virtual memory, MMU, OS (Linux, Android)
- Used in smartphones, tablets, smart TVs
- ARMv7-A, ARMv8-A, ARMv9-A architectures
- Multicore + SIMD + NEON support

#### Common Cores:
| Core        | Feature Set                    |
|-------------|---------------------------------|
| Cortex-A7   | Power-efficient mobile cores    |
| Cortex-A9   | Dual/quad-core, smartphones     |
| Cortex-A53  | 64-bit, mid-range processors    |
| Cortex-A72  | High-performance                |
| Cortex-A78  | Used in latest Android SoCs     |

 **Used In**:
- Snapdragon, MediaTek, Exynos SoCs
- Android Phones, Raspberry Pi, Chromebooks

## Summary Table: ARM Families and Their Uses

| Family      | Used In                          | Key Feature                  |
|-------------|----------------------------------|------------------------------|
| ARM7        | Early phones, simple MCUs        | Basic 32-bit core            |
| ARM9        | Routers, early smart devices     | MMU, cache support           |
| Cortex-M    | MCUs, IoT, smart devices         | Low power, interrupt support |
| Cortex-R    | Real-time/automotive systems     | Deterministic, fault-tolerant|
| Cortex-A    | Phones, tablets, high-end apps   | Full OS, high performance    |


## Conclusion:

- **ARM7/9**: Older, used in simpler embedded systems
- **Cortex-M**: Ideal for low-power embedded and IoT devices
- **Cortex-R**: Perfect for safety-critical real-time apps
- **Cortex-A**: Runs Android/Linux — high-end performance

