# Compilers, Interpreters & Language Working



🔹 1. Compiler vs Interpreter :-

Compiler: Translates entire program into machine code (faster execution).

Ex: C, C++ (compiled → binary → run).


Interpreter: Executes code line-by-line (slower, flexible).

Ex: Python, JavaScript.



---

🔹 2. How Python Works :-

1. Python source code (.py) → Interpreter


2. Code is first compiled into bytecode (.pyc)


3. Bytecode is executed by the Python Virtual Machine (PVM)


4. Optional: JIT (Just-In-Time) compilers like PyPy speed up execution.



---

🔹 3. How Other Languages Work :-

C / C++

Source code → Compiler → Machine code (direct execution).


Java

Source code → Compiler → Bytecode (.class) → JVM (interprets / JIT compiles).


JavaScript

Code → JS Engine (e.g., V8) → Parser + Interpreter + JIT → Machine code.


Go / Rust

Source code → Compiler → Binary → Run (like C).



---

🔹 4. Six Phases of Compilation (Universal) :- 

1. Lexical Analysis (Scanner) :-

Breaks code into tokens.

Ex: int x = 5; → int, x, =, 5, ;



2. Syntax Analysis (Parser) :-

Checks grammar via parse tree/AST.

Ex: Verifies assignment statement.



3. Semantic Analysis :-

Checks meaning (type checking, scope rules).

Ex: Can’t add string to int.



4. Intermediate Code Generation (IR) :-

Converts AST → Intermediate Representation (portable).



5. Optimization :-

Improves IR (remove redundancies, loop optimizations).



6. Code Generation :-

IR → Target Machine Code (assembly/binary).




(Additional Phase: Symbol Table Management + Error Handling throughout)


---

🔹 5. Mapping Phases in Languages :-

C / C++ → All 6 phases → Machine Code.

Java → All 6 phases → Bytecode → JVM interprets/JIT compiles.

Python → Mini-compiler (phases 1–4) → Bytecode → PVM interprets.

JavaScript → Parser + Interpreter + JIT → Optimized machine code.



---

🔹 6. Key Takeaways :-

Compiled langs = Faster, optimized binaries.

Interpreted langs = Flexible, slower, but portable.

Modern trend: Hybrid (Bytecode + VM + JIT) → Best of both worlds.



---




From High-Level Language to Executable + Platform Dependence
