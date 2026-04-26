# Digital Systems and Binary Numbers

---

- [Digital Systems and Binary Numbers](#digital-systems-and-binary-numbers)
- [Introduction](#introduction)
- [Number representation](#number-representation)
  - [Binary Addition](#binary-addition)
  - [Binary Subtraction](#binary-subtraction)
  - [Binary Multiplication](#binary-multiplication)
  - [Binary Division](#binary-division)
- [Number base conversion](#number-base-conversion)
  - [Case 1: Higher Base to Lower Base](#case-1-higher-base-to-lower-base)
    - [Process](#process)
    - [Integral Part Conversion](#integral-part-conversion)
    - [Fractional Part Conversion](#fractional-part-conversion)
    - [Final Combined Result](#final-combined-result)
  - [Case 2: Lower Base to Higher Base](#case-2-lower-base-to-higher-base)
    - [Process](#process-1)
    - [Integral Part Conversion](#integral-part-conversion-1)
    - [Fractional Part Conversion](#fractional-part-conversion-1)
    - [Final Combined Result](#final-combined-result-1)
  - [Alternative methods for number base conversion](#alternative-methods-for-number-base-conversion)
    - [Decimal Binary Conversion](#decimal-binary-conversion)
    - [Decimal Octal \& Hexadecimal Conversion](#decimal-octal--hexadecimal-conversion)
    - [Binary Octal Conversion](#binary-octal-conversion)
    - [Binary Hexadecimal Conversion](#binary-hexadecimal-conversion)
- [Complements of numbers](#complements-of-numbers)
  - [Subtraction using complements](#subtraction-using-complements)
- [Signed Binary Numbers](#signed-binary-numbers)
  - [Ordinary Arithmatic](#ordinary-arithmatic)
  - [Signed Complement System](#signed-complement-system)
  - [Addition of signed numbers](#addition-of-signed-numbers)
  - [Subtraction of signed numbers](#subtraction-of-signed-numbers)
- [Binary codes](#binary-codes)
  - [Binary coded Decimal code (BCD)](#binary-coded-decimal-code-bcd)
    - [BCD addition](#bcd-addition)
  - [Gray code](#gray-code)
  - [ASCII character code](#ascii-character-code)
  - [Error detecting code](#error-detecting-code)
- [Binary storage and registers](#binary-storage-and-registers)
  - [Registers](#registers)
  - [Register transfer](#register-transfer)
- [Binary logic](#binary-logic)
  - [Logic gates](#logic-gates)

---

# Introduction

- The binary information in a digital computer must have a physical existence in some medium for storing individual bits. 
- A binary cell is a device that possesses two stable states and is capable of storing one bit (0 or 1) of information. 
- Bit is a binary digit with only 2 discrete values 0 & 1. 
- Bit is the smallest unit of data.
  - 1 nibble = 4 bits
  - 1 byte = 8 bits
  - 1 word = 16 bits = 2 bytes
  - 1 double word = 32 bits = 4 bytes
- Digital system is an interconnection of digital modules. These manipulate discrete quantities of information that are represented in binary form.

---

# Number representation

Any number can be expressed in a specific number system. A general representation in a base-r system is:
$$a_n*r^n + a_{n-1}*r^{n-1} + .... + a_1*r + a_0 $$
$$+ a_{-1}*r^{-1} + a_{-2}*r^{-2} + ....$$
where, 
- r = base of the number system,
- $a_{i}$ = coefficients of bases with values varying from 0 to r-1

## Binary Addition
- The sum of 2 binary numbers is calculated by the same rules as in decimal.
- Any carry obtained in a given significant position is used by the pair of digits one significant position higher.
- Binary addition for a single bit is:
  - 0+0 = sum: 0 & carry:0
  - 1+0 or 0+1 = sum: 1 & carry:0
  - 1+1 = sum: 0 & carry:1

## Binary Subtraction
The subtraction of 2 binary numbers is calculated by the same rules as in decimal except that the borrow in a given significant position adds 2 to a minuend digit.

## Binary Multiplication
In binary multiplication, the result is onn only when both the input bits are 1. It looks like this:
  - 0x0 = 0
  - 1x0 or 0x1 = 0
  - 1x1 = 1

## Binary Division
The division of 2 binary numbers is calculated by the same rules as in decimal.

---

# Number base conversion

If a number includes a radix point, the number is split into an integer and a fraction part. Then conversion of decimal integer to a number in base-r is done by dividing the number and all successive quotients by r and accumulating the reminders. In case of fractions, multiplication is used instead of division.

## Case 1: Higher Base to Lower Base
*(e.g., Decimal to Binary, Hex to Binary)*

### Process
- Convert the given number from Base 1 to **decimal (base 10)** first (if needed).  
- Then convert decimal to Base 2 using:
  - **Integral part**: repeated division by Base 2 
  - **Fractional part**: repeated multiplication by Base 2 

### Integral Part Conversion
- Divide the number repeatedly by Base 2.  
- Record remainders.  
- Final result = **remainders read in reverse order**.

**Example (Decimal to Binary):**  
$$
 25_{10} = 11001_2 
$$  
- 25 ÷ 2 -> remainder 1  
- 12 ÷ 2 -> remainder 0  
- 6 ÷ 2 -> remainder 0  
- 3 ÷ 2 -> remainder 1  
- 1 ÷ 2 -> remainder 1  

### Fractional Part Conversion
- Multiply fractional part repeatedly by Base 2.  
- Record integer part at each step.  
- Final result = **digits read in order**.

**Example:**  
$$
 0.625_{10} = 0.101_2 
$$  
0.625 × 2 = 1.25 -> carry 1  
0.25 × 2 = 0.5 -> carry 0  
0.5 × 2 = 1.0 -> carry 1 


### Final Combined Result
$$
 25.625_{10} = 11001.101_2 
$$

---

## Case 2: Lower Base to Higher Base
*(e.g., Binary to Decimal, Binary to HEX)*

### Process
- Expand number using positional weights of Base 2.  
- Separate **integral and fractional parts**.  
- Use powers of 2 for conversion.

### Integral Part Conversion
- Multiply each digit by corresponding power of 2.  
- Sum all terms.

**Example:**  
$$
 11001_2 = (1×2^4) + (1×2^3) + (0×2^2) + (0×2^1) + (1×2^0) 
$$  
$$
 = 16 + 8 + 0 + 0 + 1 = 25_{10} 
$$

### Fractional Part Conversion
- Multiply each digit by negative powers of 2.

**Example:**  
$$
 0.101_2 = (1×2^{-1}) + (0×2^{-2}) + (1×2^{-3}) 
$$  
$$
 = 0.5 + 0 + 0.125 = 0.625_{10} 
$$

### Final Combined Result
$$
 11001.101_2 = 25.625_{10} 
$$

---

## Alternative methods for number base conversion

### Decimal Binary Conversion

- Decimal to Binary Conversion: There are 2 methods for this:
  - By division:
    - Divide by 2
    - Mark the remainder
    - Divide the quotient by 2
    - Append to the remainder
    - Repeat this until quotient < 2
    - For fractional part, multiply by 2
  - By subtraction:
    - Take highest power of 2 which is lesser than or equal to the decimal number
    - Subtract it from the number 
    - Repeat this until the remainder becomes zero
    - Collect all the powers of 2 subtracted from the number to compute the bits
    - For fractional part, add by powers of 2
- Binary to Decimal Conversion: Add weighted powers of 2 just like the number representation
  
### Decimal Octal & Hexadecimal Conversion

- Exactly similar to binary just, use the base as 8, 16 respectively.

### Binary Octal Conversion

- Binary to Octal Conversion: Clubbing 3 bits to obtain a single Octal digit.
- Octal to Binary Conversion: Replace octal digit into corresponding 3 binary digits.

### Binary Hexadecimal Conversion

- Binary to HEX Conversion: Clubbing 4 bits to obtain a single Hex digit.
- HEX to Binary Conversion: Replace Hex digit into corresponding 4 binary digits.

---

# Complements of numbers

Complements are used in digital systems to simplify the subtraction operation and logical manipulation. There are 2 types of complements:

1. **Diminished radix complement ((r-1)'s complement):** (r-1)'s complement of an n-digit number N in base-r is defined as:
    > $(r^{n} -1 ) - N$ where, r is base number.
      - 9's complement = subtracting every digit from 9     
      - 1's complement = subtracting every digit from 1
        - which is same as toggling bits

2.  **Radix complement (r's complement):** r's complement of an n digit number 'N' in base-r is defined as:
    > $(r^n-N)$ for N != 0

    > '0' for N = 0 

  > **r's complement = (r-1)'s complement + 1**
  > **Complement of the complement restores the number to its original value.**

- For eg. 9's complement of 546 is 453
- For eg. 10's complement of 546 is 454 = 453+1
- For eg. 1's complement of 1100 is 0011
- For eg. 2's complement of 1100 is 0100 = 0011+1

## Subtraction using complements

Consider M & N are 2 n-digit unsigned numbers in base-r.
> M - N = M + (r's complement of N)

if M $\geqslant$ N :
> M - N = M + (r's complement of N) + $r^{n}$;
Carry can be ignored.

if M < N : 
> M - N = $r^{n}$ - (N- M) 
> 
> = r's complement of (N-M) (answer) result is negative.
> 
> = - (r's complement of answer) (familiar representation)
>
> Final carry bit acts as a sign bit for the answer.
>   - If carry bit = 1, then the result is positive.
>   - If carry bit = 0, then the result is negative.

- For eg. 
  - Decimal number: 
    - 530 - 240 
      - = 530 + (10's complement of 240) 
      - = 530 + (759+1) 
      - = (1)290 = 290 (neglecting carry)
    - 240 - 530
      - = - (10's complement of ( 240 + (10's complement of 530)))
      - = - (10's complement of ( 240 + (469+1)))
      - = - (10's complement of 710)
      - = - (289+1) = -290
  - Binary number:
    - 1100 - 1010 
      - = 1100 + (2's complement of 1010) 
      - = 1100 + (0101+1) 
      - = 1100 + 0110
      - = (1)0010 = 0010
    - 1010 - 1100
      - = - (2's complement of ( 1010 + (2's complement of 1100)))
      - = - (2's complement of ( 1010 + (0011+1)))
      - = - (2's complement of 1110)
      - = - (0001+1) = - (0010)
  
---

# Signed Binary Numbers

## Ordinary Arithmatic

In ordinary arithmatic, negative numbers are represented with a minus sign. But due to hardware limitations, Computers must represent everything with binary digits. Signed Binary Numbers representation:
- sign bit = 0 for a positive number
- sign bit = 1 for a negative number

> | sign bit | Number (magnitude) |

- Unsigned number: Left most bit is the MSB
- Signed number: Left most bit is the sign bit. 
- Eg. 01001 = 9 (unsigned) & + 9 (signed)
- Eg. 11001 = 25 (unsigned) & -9 (signed)

This representation is known as the signed magnitude convention, or ordinary arithmatic.

## Signed Complement System
In this system, a negative number is indicated by it's complement. Representation of a number in Signed Complement System :

> | sign bit | Complement |

There are 2 representations of the Signed Complement System:
  - Signed 1's complement
  - Signed 2's complement
  
> Complement could be (1's or 2's) but usually 2's complement.
- For eg. '-9' has three different representations:
  - Signed magnitude: 1-0001001 (Changing the leftmost bit)
  - Signed 1's compliment: 1-1110110 (Complement of all the bits including sign bit)
  - **Preferred method** : Signed 2's compliment: 1-1110111 (Complement of all the bits & add 1) 
- Range of the number representations:
  - Signed magnitude: $-2^{n-1}+1$ to $2^{n-1}-1$ for ex. -7 to 7 for 4 bit numbers
  - Signed 1's compliment: $-2^{n-1}+1$ to $2^{n-1}-1$ for ex. -7 to 7 for 4 bit numbers
  - Signed 2's compliment:  $-2^{n-1}$ to $2^{n-1} -1$ for ex. -8 to 7 for 4 bit numbers 

> *An extra number $-2^{n-1}$ is accommodated in 2's compliment representation.*

> In signed magnitude's compliment, zero is represented as:
>   - Positive zero: 0  for ex. 0000
>   - Negative zero: $-0$ for ex. 1000

> In signed 1's compliment, zero is represented as:
>   - Positive zero: 0  for ex. 0000
>   - Negative zero: $-0$ for ex. 1111

> In signed 2's compliment, zero is represented as:
>   - Positive zero: 0  for ex. 0000
>   - Negative zero: Doesn't exist
>   - Extra negative number: $-2^{n-1}$ for ex. -8 looks like 1000

> Positive numbers are same in all the representations.

## Addition of signed numbers

- Signed Magnitude:
  - if signs are same:
    - Subtract magnitude.
    - Keep the sign.
  - if signs are different:
    - Compare the numbers.
    - Subtract smaller one from the larger one.
    - Append sign of the larger number.
- Signed 2's complement: simply add the numbers including sign bit and discard the carry.

## Subtraction of signed numbers

- 2's complement of subtrahend (including sign bit) is added to the minuend (including sign bit) and discard the carry.
- As subtraction & addition basically use the same method in a signed 2's complement representation. 
- Computers need only one common hardware circuit to handle both types of arithmatic.

---

# Binary codes
Code is nothing but group of symbols.

## Binary coded Decimal code (BCD)

Decimal number representation in binary (4 bits are used to represent a decimal digit). Binary combination 0000 to 1001 represent 0-9 whereas, 1010 to 1111 are not used and have no meaning in BCD.

### BCD addition

1. Sum $\leqslant$ 1001 (without carry)\
Sum = A + B 
2. Sum $\geqslant$ 1010\
Sum = add 6 (16-10) to the binary sum and also generates a carry\
Representation of signed BCD is similar to the signed numbers in binary.

## Gray code

Advantage over straight binary numbers only one bit change in the next an increment. This is useful in continuous data such as ADCs

| **Binary Number** | **Gray Code** |
|-------------------|---------------|
| 0                 | 00            |
| 1                 | 01            |
| 2                 | 11            |
| 3                 | 10            |

## ASCII character code

- ASCII stands for American Standard code for Information Interchange.
- An alphanumeric character set representation with binary digits. 
- This set includes 10 decimal digits, 26 letters of the alphabet (uppercase & lowercase) and multiple special characters. 
- This is a 7 bit code but used as a byte for storing in computers.

## Error detecting code

Eighth bit of the ASCII code is used to detect errors. The bit is called as parity bit. Parity bit represents total of 1's in the number. The parity could be odd or even.

| **Number** | **Even Parity** | **Odd Parity** |
|------------|-----------------|----------------|
| 101        | 0101            | 1011           |
| 111        | 1111            | 0111           |

---

# Binary storage and registers

- The binary information in a digital computer must have a physical existence in some medium for storing bits. 
- A binary cell is a device that possesses 2 stable states and is capable of storing one bit of information (0 or 1).

## Registers

A register is a contiguous group of binary cells. An n-bit register can store n bit information, and can have $2^{n}$ possible states.

## Register transfer

A digital system is characterized by its registers and the components that perform data processing. 
>**The device most commonly used for holding data is a register, and Binary variables are manipulated by means of digital logic circuits.**
- In digital systems, a register transfer operation is a basic operation that consists of a transfer of binary information from one set of registers into another set of registers. 
- The transfer may be direct, from one register to another, or may pass through data‐processing circuits to perform an operation. 

![Transfer of information among registers](images/RTL.png)

---

# Binary logic

- Binary logic deals with variables that take on 2 discrete values and with operations that assume logical meaning.
- Binary logic consists of binary variables and a set of logical operation. 
- Each variables has only 2 distinct values 1 & 0. 
- Basic logical operations include only 3 functions: AND, OR & NOT.

## Logic gates

- Logic gates are the electronic circuits that operate on one or more physical input signals to produce an output signal.
- Binary information is stored into voltage levels. 
- Voltage ranges are assigned to logic 0 & Logic 1 for interpretation.
- Basic gates: NOT, AND, & OR (with these gates we can create all the other gates)
- Universal gates: NAND, & NOR 
- Arithmatic gates: XOR, & XNOR 

![Logic Gates & their Truth tables](images/LogicGates.png)

---