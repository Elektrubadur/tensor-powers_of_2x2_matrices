# tensor-powers_of_2x2_matrices
A Wolfram Mathematica code relying on representation theory to be able to efficiently perform computations with large tensor powers of 2x2 matrices. 
## **Description and Usage**  

The code consists of two main files:  

### **`m2tensorpowerblocks.nb`**  
- This script performs representation theory computations and exports the results for later use.  
- Specifically, it computes certain polynomials of 4 variables (considered as entries of a generic \( 2 \times 2 \) matrix).
- The results do not depend on the actual matrices we then want to work with; so it is enough to run it once.
- The computed results are then used in `sl2reps.nb`.  

### **`sl2reps.nb`**  
- This script is used for "useful" computations and begins by **importing** the exported results from `m2tensorpowerblocks.nb`.  
- It defines a function that, for an integer $n > 0$ and a $2 \times 2$ matrix $M$, returns the diagonal blocks appearing in a special orthonormal basis — i.e., the **"block form"** — of $M^{\otimes n}$  

- The basis is determined by the representation theory of SL(2) and is independent of $M$ (see the computations done in the first file).  
- The function returns a **list of pairs**, where:  
  - The **second element** of each pair is a block (a matrix).  
  - The **first element** is the **multiplicity** of that block in the decomposition of $M^{\otimes n}$.  

### **Notes**  
- The output list is ordered by increasing block size.  
- Each block has a unique size; the largest block is an $(n+1) \times (n+1)$ matrix.  
- There is exactly one block per odd/even positive dimension, depending on whether \( n+1 \) is even or odd.  
- All other computations in the file rely on this function.
---

### **Authors**  
- **Mihály Weiner** (Budapest University of Technology and Economics)  
- **Sloan Nietert** (Cornell University)  
