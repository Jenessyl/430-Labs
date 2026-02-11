# Names: Jenessy Jane Lustre & Paul Hartman
# Lab: lab3 (CSP)
# Date: February 11, 2026

### Exercise 4

8. If we only processed each arc once without re-qeuing, this can lead to a situation where the alforithm thinks an arc is valid when it isn't. Essentially, the algorithm should re-add arcs if a domain changes because that can eliminate or add arcs, and thus this information should remain up-to-date.

9. This reveals that easy Sudoku puzzles consists of predictable and a small number of valid arcs between variables. A property a puzzle might have is to have a great number of cells already filled in at the beginning. This would greatly reduce the amount of possible arcs between two variables and thus the algorithm does not need to search if it can already tell what to put into the cell due to the the added constraints.

It is like a "guess who" game where if you ask enough questions (add more constraints) and narrow it down, theres only a few or even one person it could possibly be.

### Exercise 5
10. Starting with the most constrained variable, especially in sudoku actually is not counter-intuitive. With a fail-first principle, the algorithm checks and discards checks that fail early. WIth it, you can guide an algorithm to the right solution faster by narrowing down the possibilities greatly at the start. This naturally reduces search effort as the alogorithm will spend less resources on invalid possibilities. 

