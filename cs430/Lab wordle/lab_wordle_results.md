# Names: Jenessy Jane Lustre & Paul Hartman
# Lab: lab 5 (Wordle)
# Date: February 19

### Exercise 1 
1. In the game of wordle, often, having a character be green emliminates the the most words from the remaining action space since it leaves no room for other possibilities in that space.

    Yellow can eliminate guesses but not to the extent of green since the information the algorithm gets from a yellow square is that the character is present but is in another one of the 5 slots.

    White has the possibility of eliminating more words than green. This is because if a character is white, that means all words with that character can be eliminated from the word list.

2. The feedback mechanism has to be deterministic because in Wordle, the main strategy of the game is to build off the info you received from previous guesses. If the feedback was probabilistic, guesses would be less accurate and may even lead to guesses that dont pass the propagated constraints.

### Exercise 2
3. A scenario where a greedy algoritm would not perform optimally would be if the answer word contained uncommon characters in uncommon slots, since it prioritizes the opposite. An agent that thinks ahead may be able to see the word is more uniquely constructed and change the types of guesses it prioritizes.

4. Having your first guesses with 5 distinct characters is the most reliable way to narrow your list of words greatly. As you make more guesses, it may be wasteful to do so as with the english language, some combinations of letters are more likely, like suffixes.

    For example, if "u" is found to be absent from the answer, it is better to guess a repeat of a letter you know is present than "q" even if the latter was distinct from the other letters.

5. If it didn't recalculate the frequencies, the agent could not take advantage of the information gained from each guess. Instead it would probably go down the list "Top 10 words by frequency score:" everytime so if the answer is not within the top five, it won't be able to solve the Wordle. The computational trade off is the time needed to recalculate the letter frequencies but that is negligible in comparison to the utility it provides the agent.

### Exercise 3
6. A guess that splits possibilities into equally-sized groups has more entropy because it is less specific. For instance compare a guess that splits the possibilities in half as opposed to one where it splits more unevenly but since the groups are smaller, there are less possible words the agent has to consider (if the word is in a smaller partition and not one of the larger ones).
7.
8.
9.
10.
11.
12.
13.
14.
15.
16.
17.
18.
19.
20.
21.
22.
23.
24