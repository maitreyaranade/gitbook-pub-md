

# HDL Theory questions

- [HDL Theory questions](#hdl-theory-questions)
- [Verilog](#verilog)
- [SystemVerilog](#systemverilog)

--- 

# Verilog

1. Why do we need an HDL?
2. Difference between Programming Language & Hardware Description Language
3. What are the different types of HDLs present in the industry?
4. Explain VHDL vs Verilog HDL
5. Different levels of Abstraction in Verilog
6. Explain the data types in Verilog
7. Difference between reg and wire & default values of reg and wire
8. Declare a 2-dimensional unpacked array
9. Difference between $display, $strobe, $write and $monitor
10. Difference between $finish, $stop and $reset
11. Write a Verilog code for NAND Gate using switch-level modelling
12. What are the different gate primitives in Verilog? Explain user-defined primitives
13. Explain the delays in Gate Level Modelling
14. What are the different types of operators in Verilog?
15. Difference between == and ===
16. Explain logical and arithmetic shifts with examples
17. Write a Verilog code for the decoder using conditional & shift operator
18. Explain the delays in Data Flow Modelling
19. What are procedural blocks in Verilog and explain them
20. Difference between the initial block and the final block
21. Explain the difference between ‘begin-end’ and ‘fork-join’
22. Blocking vs Non-blocking assignments
23. Explain inter and intra-assignment delays with an example
27. What is a parameter?
28. Explain compiler directives
29. Explain `timescale in Verilog
30. Explain Case-x and Case-z statements
31. Explain the full case and parallel case statements
32. Difference between task and function
33. Explain the delays in Behavioural Modelling
44. Explain simulation & synthesis
45. What are the synthesizable constructs in Verilog?
46. What is linting?  
47. Explain Event regions in Verilog
48. What is structural modelling?
49. What is meant by a generic style of coding?
50. Explain port mapping in Verilog.

---

# SystemVerilog

1. What is the difference between an initial and final block of the systemverilog?
2. Explain the simulation phases of SystemVerilog verification?
3. What is the Difference between SystemVerilog packed and unpacked array?
4. What is “This ” keyword in the systemverilog?
5. What is alias in SystemVerilog?
6. randomized in the systemverilog test bench?
7. in SystemVerilog which array type is preferred for memory declaration and why?
8. How to avoid race round condition between DUT and test bench in SystemVerilog verification?
9. What are the advantages of the systemverilog program block?
10. What is the difference between logic and bit in SystemVerilog?
11. What is the difference between datatype logic and wire?
12. What is a virtual interface?
13. What is an abstract class?
14. What is the difference between $random and $urandom?
15. What is the expect statements in assertions?
16. What is DPI?
17. What is the difference between == and === ?
18. What are the system tasks?
19. What is SystemVerilog assertion binding and advantages of it?
20. What are parameterized classes?
21. How to generate array without randomization?
22. What is the difference between always_comb() and always@(*)?
23. What is the difference between overriding and overloading?
24. Explain the difference between deep copy and shallow copy?
25. What is interface and advantages over the normal way?
26. What is modport and explain the usage of it?
27. What is a clocking block?
28. What is the difference between the clocking block and modport?
29. System Verilog Interview Questions, Below are the most frequently asked questions.
30. What are the different types of verification approaches?
31. What are the basic testbench components?
32. What are the different layers of layered architecture?
33. What is the difference between a $rose and @ (posedge)?
34. What is the use of extern?
35. What is scope randomization?
36. What is the difference between blocking and non-blocking assignments?
37. What are automatic variables?
38. What is the scope of local and private variables?
39. How to check if any bit of the expression is X or Z?
40. What is the Difference between param and typedef?
41. What is `timescale?
42. Explain the difference between new( ) and new[ ] ?
43. What is the difference between task and function in class and Module?
44. Why always blocks are not allowed in the program block?
45. Why forever is used instead of always in program block?
46. What is SVA?
47. Explain the difference between fork-join, fork-join_none, and fork- join_any?
48. What is the difference between mailboxes and queues?
49. What is casting?
50. What is inheritance and polymorphism?
51. What is callback?
52. What is constraint solve-before?
53. What is coverage and what are different types?
54. What is the importance of coverage in SystemVerilog verification?
55. When you will say that verification is completed?
56. What are illegal bins? Is it good to use it and why?
57. What is the advantage of seed in randomization?
58. What is circular dependency?
59. What is “super “?
60. What is the input skew and output skew in the clocking block?
61. What is a static variable?
62. What is a package?
63. What is the difference between bit [7:0] and byte?
64. What is randomization and what can be
65. What are the constraints? Is all constraints are bidirectional?
66. What are in line constraints?
67. What is the difference between rand and randc?
68. Explain pass by value and pass by ref?
69. What are the advantages of cross-coverage?
70. What is the difference between associative and dynamic array?
71. What is the type of SystemVerilog assertions?
72. What is the difference between $display,$strobe,$ monitor?
73. Can we write SystemVerilog assertions in class?
74. What is an argument pass by value and pass by reference?
75. what is the difference between a bit and logic data type in system verilog?
76. what is the difference between $display, $write, $monitor, and $strobe in systemverilog?
77. what is the difference between a packed array and an unpacked array in system verilog with example?
78. suppose a dynamic array of integers is initialized to values as shown below. write a code to find all elements greater than 5 in the array using array locator method “ find ”?
79. how can we use system verilog constraints to generate a dynamic array with random but unique values with and without unique constraint?
80. explain the concept of a “ref” and “const ref” argument in systemverilog function or task with example?
81. difference between “forever loop” and “for loop” in systemverilog?
82. what is the difference between “case”, “casex” and “casez” in systemverilog?
83. how regions inside a system verilog simulation semantics works? explain with examples
84. what is a modport in an system verilog interface?
85. which of the logical equality operators “==” or “===” are used in case expression conditions for case, casex, and casez?
86. what is the difference between byte and logic[7:0] variable in system verilog?
87. what is the difference between input #1 step sig_1; and input #1ns sig_1; ways of specifying skews in a clocking block?
88. given a dynamic array of size 50, how can the array be re-sized to hold 100 elements while the lower 50 elements are preserved as original in system verilog?
89. what are pre_randomize() and post_randomize() in system verilog with example?
90. what is the difference between a union and struct in systemverilog with example?
91. explain unique constraint in system verilog with example?
92. which of the array types are good to model really large arrays or a huge memory of 16/32/64kb?
93. difference between private, public, and protected data members of a systemverilog class.
94. what is the difference between new() and new[] in systemverilog?
95. what is difference between bounded and unbounded mailboxes in system verilog? explain with examples
96. explain interfaces in system verilog with example
97. what is the difference between a logic, reg and wire in system verilog?
98. explain system tasks and functions in system verilog? give some example of system tasks and functions
99. explain the concept of forward declaration of a class in system verilog with example.
100. what metrics would you use to track the progress of verification project?
101. in system verilog how can we merge two events? explain with example
102. explain clocking block with example and what are the advantages of using clocking blocks inside system verilog interface?
103. identify how many parallel threads does this given code executes?
104. how can we disable or enable constraints selectively in a system verilog class?
105. given a class with following constraints, how can you generate a packet object with address value greater than 500?
106. write a system verilog constraint to generate a random value such that it always has 15 bits as 1 and no two bits next to each other should be 1
107. what is gate level simulation and why is it important in signing off any design?
108. write system verilog constraints to generate elements of a dynamic array such that each element of the array is less than 50 and the array size is less than 50.
109. write system verilog constraints to create a random array such that array size is between 50 and 100 and the values of the array are in descending order?
110. hard constraints vs soft constraints with examples
111. is the given systemverilog constraint correct? if yes what will be the output and if no what's wrong with it. please explain
112. how to override a constraint defined in the base/parent class in the derived/child class?
113. when can you say that verification is complete?