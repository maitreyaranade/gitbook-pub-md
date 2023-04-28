# Digital Systems and Binary Numbers

---

- [Digital Systems and Binary Numbers](#digital-systems-and-binary-numbers)
- [Introduction](#introduction)
- [Number representation](#number-representation)
- [Number base conversion](#number-base-conversion)
  - [Binary  Octal Conversion](#binary--octal-conversion)
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
- Digital system is an interconnection of digital modules.
These manipulate discrete quantities of information that are represented in binary form.


---
# Number representation

Any number can be expressed in a specific number system. A general representation in a base-r system is:
$$a_n*r^n + a_{n-1}*r^{n-1} + .... + a_1*r + a_0 $$
$$+ a_{-1}*r^{-1} + a_{-2}*r^{-2} + ....$$
where, 
- r = base of the number system,
- $a_{i}$ = coefficients of bases with values varying from 0 to r-1


---
# Number base conversion

If a number includes a radix point, the number is split into an integer and a fraction part. Then conversion of decimal integer to a number in base-r is done by dividing the number and all successive quotients by r and accumulating the reminders. In case of fractions, multiplication is used instead of division.

## Binary  Octal Conversion

- Binary to Octal Conversion: Clubbing 3 bits to obtain a single Octal digit.
- Octal to Binary Conversion: Replace octal digit into corresponding 3 binary digits.

## Binary Hexadecimal Conversion

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

     - r's complement = (r-1)'s complement + 1
       - For eg. 9's complement of 546 is 453
       - For eg. 10's complement of 546 is 454 = 453+1
       - For eg. 1's complement of 1100 is 0011
       - For eg. 2's complement of 1100 is 0100 = 0011+1

> Complement of the complement restores the number to its original value.
 
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

- For eg. 
  - Decimal number: 
    - 530 - 240 
      - = 530 + (10's complement of 240) 
      - = 530 + (759+1) 
      - = (1)290 = 290 (neglecting carry)
    - 240 - 530
      - = - (10's complement of ( 240 + (10's complement of 530))
      - = - (10's complement of ( 240 + (469+1))
      - = - (10's complement of 710)
      - = - (289+1) = -290
  - Binary number:
    - 1100 - 1010 
      - = 1100 + (2's complement of 1010) 
      - = 1100 + (0101+1) 
      - = 1100 + 0110
      - = (1)0010 = 0010
    - 1010 - 1100
      - = - (2's complement of ( 1010 + (2's complement of 1100))
      - = - (2's complement of ( 1010 + (0011+1))
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
  
> Complement could be (l's or 2's) but usually 2's complement.
- For eg. '-9' has three different representations:
  - Signed magnitude: 1-0001001 (Changing the leftmost bit)
  - Signed 1's compliment: 1-1110110 (Complement of all the bits including sign bit)
  - **Preferred method** : Signed 2's compliment: 1-1110111 (Complement of all the bits & add 1) 

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

- The binary information in a digital computer must a physical existence in some medium for storing bits. 
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
- Binary information into voltage levels. 
- Voltage ranges are assigned to logic 0 & Logic 1 for interpretation.

![Logic Gates & their Truth tables](images/LogicGates.png)

