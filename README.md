# Fundamentals of Computing
## Msc. Data Science at Birkbeck, University of London
### 10/2018

Summary:

### Syllabus 
1. Digital logic. slides (Chapter 2 of "Logic and Computer Design Fundamentals")
2. Arithmetic for computers. slides Converting decimal to binary is here and here. A brief and gentle introduction to binary numbers is available here. (Sections 1.2-1.4, 4.1-4.3 and 10.7 of "Logic and Computer Design Fundamentals") 
3. Elements of set theory. Elements of graph theory. slides (Chapters 1 and 10 of "Discrete Mathematics with Applications"; Section 1.4 of "Theory of Computing. A gentle introduction") 
4. Finite state machines (automata). (Section 2.1 of "Theory of Computing. A gentle introduction") 
JFLAP is software for experimenting with finite automata, pushdown automata, Turing machines, regular and context-free languages.
5. Nondeterministic automata. Determinism vs. nondeterminism. (Sections 2.2 and 2.3 of "Theory of Computing. A gentle introduction")
6. Regular languages. (Section 2.4 of "Theory of Computing. A gentle introduction")
7. Context-free languages and pushdown automata. (Sections 3.1 and 3.3 of "Theory of Computing. A gentle introduction") 
8. Turing machines. (Sections 4.1 and 4.2 of "Theory of Computing. A gentle introduction") 
9. The halting problem. Undecidable problems.  
10. Data structures: representations and operations.
11. Lists, trees, forests, binary trees.
12. Tree traversal and other operations; binary search trees.
13. Organisation of disk storage; methods of file organisation; B-trees.
14. Algorithms: design and analysis; algorithmic complexity; space utilisation.
15. Sorting and searching.

## Week 1

* φ <- phi  
* ψ <- psy  
* χ <- chi  

1. Boolean formulas `φ, ψ` are called equivalent if their truth-tables are identical. In this case we write `φ ≡ ψ`.
2. De Morgan laws  
`¬(φ∧ψ) ≡ ¬φ∨¬ψ`  
`¬(φ ∨ ψ) ≡ ¬φ ∧ ¬ψ`
3. Law of double negation
`¬¬φ ≡ φ`  
4. Law of the excluded middle, "to be or not to be"   
`¬φ ∨ φ ≡ 1`  
5. Law of contradiction
`¬φ ∧ φ ≡ 0`  
6. Distributivity of `∧` over `∨`  
`φ∧(ψ∨χ) ≡ (φ∧ψ)∨(φ∧χ)`  
7. Distributivity of `∨` over `∧`  
`φ∨(ψ∧χ) ≡ (φ∨ψ)∧(φ∨χ)`  
8. A implies B === not A or B  
`φ→ψ ≡ ¬φ∨ψ`
9. `↔` = if and only if
10. `⊕` = XOR gate 
11. `|` or `NAND` 

## Week 2
1. Converting decimal numbers to binaries: divide by 2  
   * Rule: 
     1. `Divide repeatedly by 2, keeping track of the remainders as you go`
     2. `The result is read from the last remainder upwards`  
2. Binary addition and subtraction (for unsigned numbers)  
   * Rule:   
   0 + 0= 0  
   0 + 1= 1  
   1 + 0= 1  
   1 + 1 = 10  
3. Positive and negative numbers  
  * The positive numbers are also represented as before:  
    `0a30 ...a0 means 0×231 +a30 ×230 +···+a1 ×2+a0`
  * To represent a negative number, take its complement to 231:  
    `1a30 ...a0 means −1×231 +a30 ×230 +···+a1 ×2+a0`
