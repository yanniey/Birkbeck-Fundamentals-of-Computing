# Fundamentals of Computing
## Msc. Data Science at Birkbeck, University of London, 10/2018

### Course Format:
* On campus: 1.5 hours of lecture and 1.5 hours of lab per week
* 2 courseworks
* Written exam in May
* Final mark = Coursework (20%) + exam (80%)

This course is like playing mind gymnastics. 

### Two things I learned from this course:

1. `A->B` is equal to `(¬A)∨B` (not A or B). Example:

    `If you study data science, then you can find a job.` is equivalent to:  
    `If you don't study data science, then `

2. From contradiction you can derive any truth. Example:

    `If pigs can fly, then I am a superstar.` is a true statement. 


### Syllabus 
1. Digital logic. (Chapter 2 of "Logic and Computer Design Fundamentals")

2. Arithmetic for computers. Converting decimal to binary. (Sections 1.2-1.4, 4.1-4.3 and 10.7 of "Logic and Computer Design Fundamentals")  

3. Elements of set theory. Elements of graph theory. (Chapters 1 and 10 of "Discrete Mathematics with Applications"; Section 1.4 of "Theory of Computing. A gentle introduction")   

4. Finite state machines (automata). (Section 2.1 of "Theory of Computing. A gentle introduction")   

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

## Week 1 Digital logic  

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


## Week 2 Arithmetic for computers  

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

3. Negative numbers: Sign-magnitude representation (not recommended)

    Treat the most significant (left-most) bit in the word as a sign :
    * If it is 0, the number is positive; 
    * If the left-most bit is 1, the number is negative; the right-most 31 bits contain the magnitude of the integer

    `+1810 = **0** 000 0000 0000 0000 0000 0000 0001 00102`
    `−1810 = **1** 000 0000 0000 0000 0000 0000 0001 00102`  

4. Positive and negative numbers, using `Two’s complement representation`  

      * The positive numbers are also represented as before:  
        `0a30 ...a0 means 0×231 +a30 ×230 +···+a1 ×2+a0`
      * To represent a negative number, take its complement to 231:  
        `1a30 ...a0 means −1×231 +a30 ×230 +···+a1 ×2+a0`
      For example:  
        `0111=0*2^3+1*2^2+1*2^1+1*2^0`
        `1111= -1*2*3+1*2^2+1*2^1+1*2^0`
        If a number starts with `1`, then it is negative:  
        `0111 1111 1111 1111 1111 1111 1111 1111<sub>2</sub>` <- biggest number
        `1000 0000 0000 0000 0000 0000 0000 0000<sub>2</sub>`<-smallest number


5. Two’s complement arithmetic: negation

    Rules for forming negation −N of an integer N (in two’s complement notation)
    * Take the Boolean negation of each bit of the integer (including the sign bit) That is, **set each 1 to 0 and each 0 to 1.**

    * Treating the result as an unsigned binary integer, add 1.

    * **Subtraction**
      Subtraction is achieved using addition x − y = x + (−y):
    to subtract y from x, negate y and add the result to x

    * **Addition** is the same as the addition of unsigned numbers

    * Overflow: if two numbers are added, and they are both positive or both negative, then overflow occurs if the result the opposite sign

    * The two’s complement representation allowed us to deal with the integer numbers in the interval between −231 and +231 − 1

    * `C=0`:Add A+B

    * `C=1`:SubtractA−B(becausebi⊕1=¬bi)

6. Scientific notation

7. Convert fraction to binary (through multiplying it by 2)

    To convert a decimal number with both integer and fractional parts, convert each part separately and combine the answers 


    convert 0.687510 to binary
    `0.6875 × 2 = 1.3750 `
    `0.3750 × 2 = 0.7500` 
    `0.7500 × 2 = 1.5000` 
    `0.5000 × 2 = 1.0000`

    `integer = 1` 
    `integer = 0` 
    `integer = 1` 
    `integer = 1`

    The result is read from the first integer downwards:
    0.6875<sub>10</sub> = 0.1011<sub>2</sub>

8. Exponents have 8 bits for single precision 

## Week 3 Set Theories

1. Set Theories 
    * A set must be distinguished from its description
    * All elements of a set are distinct
    * The elements of a set are not ordered in any way
    * A set can be an element of another set

2.  Set Operations

    + **Union** of sets `A` and `B` is the set `A∪B = {x|x∈A or x∈B}`

    + **Intersection**of sets `A` and `B` is the set `A∩B = {x|x∈A and x∈B}`
        + if `A∩B = ∅` then `A` and `B` are called disjoint

    + **Complement** of a set `B` relative to a set `A` is the set `A−B = {x|x∈A and x∈/B}`
        + A − B is also called the difference of A and B  
        
    * **Absolute completment** 
        + Given a universal set `U` and `A ⊆ U`, the complement of `A` (in `U`) is the set `−A = U−A = {x∈U|x∈/A}`
    
    * **Powerset**
        + The powerset of a set A is defined to be the `set of all subsets of A Notation`: Pow(A) = {X | X ⊆ A}  

        + Powerset notation: `Pow(A) = 2^A`  

3. Set equalities

    + Associative laws:
      + `A∪(B∪C)=(A∪B)∪C, A∩(B∩C)=(A∩B)∩C`

    + Commutative laws:
      + `A∪B=B∪A, A∩B=B∩A`

    + Identity laws (where U is the universal set):
      + `A∪∅=A, A∪U =U, A∩U =A, A∩∅=∅`

    + Distributive laws:
      + `A∩(B∪C)=(A∩B)∪(A∩C), A∪(B∩C)=(A∪B)∩(A∪C)`

    + Complement laws (where U is the universal set): 
      + `A∪−A=U, −U =∅, −(−A)=A, A∩−A=∅`

4. Functions

    A function from a set `A` to a set `B` is a binary relation `R ⊆ A × B` in which **every** element of `A` is R-related to a unique element of `B`, or, in other words: **for each `a ∈ A`, there is precisely one pair of the form `(a, b)` in R**.

5. Function Notation

    * We write  `f :A→B` to indicate that `f` is a function from `A` to `B` 
    * `A` is called the **domain** of `f`. `B` is called the **codomain** of `f`

    * The range of `f` is the set `f(A) = {f(x)|x∈A}`

    * Every element of the domain has to be mapped somewhere
    in the codomain

    * But not everything in the codomain has to be a value of a domain element

    * One element cannot be mapped to 2 different places

    * But it can happen that 2 different elements are mapped to the same place

6. Injective functions (one-to-one functions)

    * A function `f : A → B` is called an **injective** (or **‘one-to-one’**) function if for all `a1,a2 ∈ A`, if `f(a1) = f(a2)` then `a1 = a2`

7. Surjective functions & Bijection
    * `f : A → B` is **surjective** (or ‘onto’) if the range of f coincides with the codomain of f, that is, if for every b ∈ B there exists a ∈ A with b = f(a).

8. Cardinality and Bijections 

    * Sets A and B have the same **cardinality** if there is a bijection from A to B. In this case we write |A| = |B|.

    * A has cardinality strictly greater than the cardinality of B if there is an injective function from B into A, but A and B do not have the same cardinality. In this case we write |A| > |B|.

    * An infinite set A is countable if it has the same cardinality as N. (i.e. a one-to-one relationship between numbers in A vs. numbers in N)
    
    * An infinite set A is uncountable if it is not countable.

9. `R` (real numbers) is uncountable. Cantor's proof. 
    * Definition of countable is one to one correspondence with natural numbers
    * The number of subsets of any set `A` is `2^A`

10. Graphs
    * The dots are called `vertices` (or `nodes`). 
    * The lines or arrows are called `edges`.
    * Undirected graphs terminology:
        + If there is an edge e between vertices u and v, we say that:
            + `u` and `v` are adjacent, and
            + `e` is incident with `u` and `v`
        + The degree of a vertex is the number of edges incident with it.
            + A vertex of degree zero is called `isolated`. So an isolated vertex is not adjacent to any vertex.
            + A vertex of degree one is called `pendant`. So a pendant vertex is adjacent to exactly one other vertex.
        + handshaking theorem:
            + `number of edges = sum of the degrees of vertices/ 2`
    * Directed graphs terminology:
        + If there is an edge `e` going from vertex `u` to `v`, we say that
            + `u` is adjacent to `v`,
            + `u` is the initial or start vertex of `e`, and
            + `v` is the terminal or end vertex of `e`.
        + The `in-degree` of a vertex v is the number of edges with v as their terminal vertex. 
        + The `out-degree` of a vertex v is the number of edges with v as their initial vertex. (A loop at a vertex contributes 1 to both the in-degree and the out-degree of this vertex.)
        + number of edges = sum of the in-degrees of vertices = sum of the out-degrees of vertices.

11. Paths
    * A path is a sequence of vertices travelling along edges.
    * The length of a path is the number of edges in it.
    * A path is called simple if it does not contain the same edge twice.
    * A **Hamiltonian path** is a simple path passing through every vertex exactly once. 

12. Cycles
    * A cycle is a path beginning and ending with the same vertex.
    * The length of a cycle is the number of edges in it.
    * A cycle is called simple if it does not contain the same edge twice.
    * A **Hamiltonian cycle** is a simple cycle passing through every vertex exactly once.

13. Isomorphism of graphs
    * A property P of graphs is called an `invariant` if it is ‘preserved under isomorphisms’: 
        + If G and H are isomorphic graphs, and `G` has property `P`, then `H` has property `P` as well.
    * Some examples of invariants
        + the number of vertices
        + the number of edges
        + the number of vertices of each degree
        + containing a triangle (K3) as a subgraph
        + containing two K4s as disjoint subgraphs
        + containing a simple cycle of length 4
        + having a path of length 2 between two vertices of degree 2

    * Isomorphism may be used to track transactions between nodes (e.g. clients) to detect money-laundering activities. 

14. Alphabets and words
    * if `w=xy` then x is a **prefix** of w,and y a **suffix** of w
        + e.g., `tor` is a prefix and `se` is a suffix of `tortoise`
        + if `sigma` is empty, then `sigma star` has one element: `sigma`

## Week 4. Finite state machines (automata), Introduction to the Theory of Computation
This week covers three parts: 

1. Automata theory and Turing machines
    * Deals with definitions and properties of precise mathematical models of computers and computations

2. Computability theory
    * What problems computers can and cannot solve? 

3. Complexity theory
    * What makes some problems computationally hard and others easy?

4. Finite automata or finite-state machines
    * A finite automata is a theoretical model for programs using a constant amount of memory regardless of the input form
    * Finite control device: at any moment can be in one of its states. It is hard-wired how it changes from one state to another
    * Some special states:
      + one initial state
      + some accepting states
    * how a finite automata works:
        + As the input is finite, at some moment the reading head reaches the end of the input word (that is, the first blank cell).
        + If at this moment the control device is in one of the accepting states, then the input word is accepted by the automaton.
        + Otherwise, the input word is not accepted (or rejected)
    * Deterministic Finite Automaton (DFA)
        + For every cell in the transition table, there is a unique state. -> for the same input to go through the same transition, the output is the same, thus deterministic.
        + Configuration: a pair of state plus words, e.g. (q, abba), q is the state, abba is the word
        + Language and DFAs: DFAs accept certain words, while may reject others. If we collect all words accepted by a DFA A, we obtain the language of A


## Week 5. Nondeterministic automata. Determinism vs. nondeterminism. (Sections 2.2 and 2.3 of "Theory of Computing. A gentle ## Week introduction")  

1. Nondeterminism = multiple output possibilities for the same input
  It checks all possibile computations. If at least one of them works (i.e. ends up at an accepting stage), then the input is considered accepted.

2. Advantages of non-deterministic automata
    * Nondeterministic finite automata are **much easier** to design than deterministic ones
        + They allow us to model how ‘programs’ are built from ‘subprograms’
    * Whatever can be done by a nondeterministic finite automaton can also be done (though usually in a bit more complicated way) by a deterministic one.
        + But deterministic automata would be much bigger than that of the deterministic equivalent
    * In other words, nondeterminism does not increase the computational power of finite automata

3. Characteristics of non-deterministic finite automata (NFA)
    * There could be no outgoing arrows -> automaton might be stuck there
    * There could be multiple outgoing arows-> same input, but different output
    * epsilon jump -> no input, but the status still changed 

4. When is words accepted by NFAs
  * A word w is accepted by an NFA A if **there exists** a computation of A on input w ending up with a configuration (q, ε), for some favourable state q.
  * So an NFA can reject an input word because every computation on this input is
        + either ‘stuck’
        + or ends up with a configuration (q′, ε), but q′ is not a favourable state.

5. Computation of NFAs
  * There can be more than one computation on an input word (because for the same input, there can be multiple outputs)
  * Nondeterminism can be viewed as a kind of parallel computation wherein sev- eral ‘processes’ can be running concurrently.

6. Differences between NFAs and DFAs
    * There can be more than one arrow labelled by the same symbol coming out of a state (e.g., there are two a-arrows out of r).
    * There can be no arrow labelled by some symbol coming out of a state (e.g., there is no b-arrow out of q).
    * There can be arrows labelled by not symbols from the input alphabet but by the empty word ε. These arrows represent ‘jumps’ (e.g. there is a jump from s to q).

7. Equivalent of NFA(Nondeterministic Automata) and DFA(Deterministic Finite Automata)
    * Two automata A and A′ are said to be equivalent if they accept the same language
    * In a DFA no choice, no ‘getting stuck’, no `ε-jumps` are allowed
    * To convert an NFA to DFA, the price is an exponential increase to the size of the automata
    * DFA makes things more compact (le.g. ess states)
    * 2^number of states of the original NFA in the worst case


## Week 6. Regular languages. (Section 2.4 of "Theory of Computing. A gentle introduction")  

1. `(a U b)^*` is equal to `{a,b}^*`

2. A **regular language** is any language that is described by a regular expression.
    * Not all languages are regular
    * Regular languages are precisely those languages that are accepted by finite automata.

3. Converting regular languages to finite automata

4. Finite automata may be regarded as programs that use fixed amounts of memory (represented by states) regardless of the input.

5. Finite automata can be used as recognition devices: they accept certain inputs and reject others.

6. Nondeterminism does not increase the computational power of finite au- tomata, but nondeterministic automata are easier to design than
deterministic ones.

7. The languages accepted by finite automata are precisely the regular ones.

## Week 7. Context-free languages and pushdown automata. (Sections 3.1 and 3.3 of "Theory of Computing. A gentle introduction")   

## Week 8. Turing machines. (Sections 4.1 and 4.2 of "Theory of Computing. A gentle introduction") 

## Week 9. The halting problem. Undecidable problems. 

## Week 10. Data structures: representations and operations.  

## Week 11. Lists, trees, forests, binary trees.  

## Week 12. Tree traversal and other operations; binary search trees.  

## Week 13. Organisation of disk storage; methods of file organisation; B-trees.  

## Week 14. Algorithms: design and analysis; algorithmic complexity; space utilisation.  

## Week 15. Sorting and searching.