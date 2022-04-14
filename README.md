# core-code-from-scratch-readme

## Index

1. [ Week 1: Introduction to programming & Javascript](#1-Week-1-Introduction-to-programing-&-Javascript)
2. .

# 1. Week 1: Intoduction to programming & Javascript

    
   ## Week Challenges (Tuesday)

### 1. Interpreted And Compiled Programming Languages

| Interpreted Programming Languages | Compliled Programming Languages |
| --- | --- |
| The source code is not directly translated by the target machine. Instead, a different program, aka the interpreter, reads and executes the code. | Compiled languages are converted directly into machine code that the processor can execute. |
| Interpreted languages were once significantly slower than compiled languages. But, with the development of just-in-time compilation, that gap is shrinking. | They tend to be faster and more efficient to execute than interpreted languages. |
| Interpreted languages tend to be more flexible, and often offer features like dynamic typing and smaller program size. | They give the developer more control over hardware aspects, like memory management and CPU usage. |
| Interpreters run through a program line by line and execute each command. | You need to “rebuild” the program every time you need to make a change. |
| Examples of common interpreted languages are PHP, Ruby, Python, and JavaScript. | Examples of pure compiled languages are C, C++, Erlang, Haskell, Rust, and Go. |
| Because interpreters execute the source program code themselves, the code itself is platform independent. | Platform dependence of the generated binary code. |
| Source code is public. | Source code is private. |
| Interpreted languages requires an interpreter. | Compiled languages need a “build” step – they need to be manually compiled first. |

Most programming languages can have both compiled and interpreted implementations – the language itself is not necessarily compiled or interpreted. However, for simplicity’s sake, they’re typically referred to as such.

Python, for example, can be executed as either a compiled program or as an interpreted language in interactive mode. On the other hand, most command line tools, CLIs, and shells can theoretically be classified as interpreted languages.

### 2. Is Java compiled or interpreted, or both?

Java is both compiled and interpreted language. Java implementations typically use a two-step compilation process. Java source code is compiled down to bytecode by the Java compiler. The bytecode is executed by a Java Virtual Machine (JVM). Modern JVMs use a technique called Just-in-Time (JIT) compilation to compile the bytecode to native instructions understood by hardware CPU on the fly at runtime.
Some implementations of JVM may choose to interpret the bytecode instead of JIT compiling it to machine code, and running it directly. While this is still considered an "interpreter," It's quite different from interpreters that read and execute the high level source code (i.e. in this case, Java source code is not interpreted directly, the bytecode, output of Java compiler, is.)
It is technically possible to compile Java down to native code ahead-of-time and run the resulting binary. It is also possible to interpret the Java code directly.

### 3. Pseudocode Currency Converter exercise

1. START
2. PRINT "Enter USD to be converted into BTC"
3. USD <-- GET
4. BTC <-- 0.000025
5. converter <-- USD * BTC
6. PRINT converter
7. END


 ## Week challenges (Wednesday)
 
 ### 1. Your date of birth in the matrix? exercise
 
 **Date of Birth:12/02/1992**
 
| Power of two  | Result |
| ------------- | ------ |
| 2^0  | 1  |
| 2^1  | 2  |
| 2^2  | 4  |
| 2^3  | 8  |
| 2^4  | 16  |
| 2^5  | 32  |
| 2^6  | 64  |
| 2^7  | 128  |
| 2^8  | 256  |
| 2^9  | 512  |
| 2^10  | 1024  |

**Decimal:** 1992
**Binary:** 11111001000

| 1024    | 512   | 256   | 128   |64   | 32   | 16   | 8   | 4   | 2   | 1   |
| ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1    | 1   | 1   | 1   | 1   | 0   | 0   | 1   | 0   | 0   | 0   |

**Decimal:** 2
**Binary:** 10

| 2    | 1   | 
| ---- | --- |
| 1    | 0   | 

**Decimal:** 12
**Binary:** 1100

| 8    | 4   | 2   | 1   |
| ---- | --- | --- | --- | 
| 1    | 1   | 0   | 0   | 

### 2. MIPS exercise

**Create a program that adds any two given numbers provided by the user**

   
   
    .data
        message: .asciiz "\nLet's add two numbers\n"
        result: .asciiz "\nThe result is: "
        number1: .asciiz "\nEnter the first number: "
        number2: .asciiz "\nEnter the second number: "
  
    .text
        main:
              # add two numbers message
              li $v0, 4
              la $a0, message
              syscall
              
              # user input
              li $v0, 4
              la $a0, number1
              syscall

              li $v0, 5
              syscall

              # saving user input
              move $t0, $v0

              # user input
              li $v0, 4
              la $a0, number2
              syscall

              li $v0, 5
              syscall

              # saving user input
              move $t1, $v0

              # adding the user numbers
              add $t2, $t0, $t1

              # showing result number
              li $v0, 4
              la $a0, result
              syscall

              # printing number
              li $v0, 1
              move $a0, $t2
              syscall
