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

7. A playing to win strategy is good if the answer word is more common. For more uniquely constructed words, it would be better to choose a word that maximizes information gain as that will eventually put the agent in a position where it will be able to make a more accurate guess. The trade-off is using up a guess in hopes the information gained will allow for more accurate guess later.

8. The frequency heuristic may scale better as the word list grows. This is because the entropy agent evaluates each feedback it gets with each guess. This process may require more computation with a larger word pool compared to simply choosing the option with the highest frequency. The trade-off with optimality is that is requires more computation to make the best decision and as the word list grows, that becomes less feasible.

### Exercise 4
9. In a competitive and time-limited scenario, it is valuable to have a maxiumum limit of possible words between guess as you are able to discern how long it would take to make each guess (in the worse case).The minimax agent is risk averse which is important in time-limited scenarios since you don't have the resources to make more educated but more computationally heavy guesses.

10. The better strategy would naturally be one that can narrow down the word list in few guesses, especially because Wordle only allows five guesses. Therefore, Minimax's strategy seems to cater to this restriction better than entropy. By observing the output of Minimax, we can see it narrows down the list more severly than entropy especially during the first few guesses. While on average, it may take more guesses to get the right word, that is the trade off for more accurate guesses. 

11. They seem to converge, guessing the same word for the last few guesses and as the word pool decreases. Optimization criteria matters more when uncertainty is high because there is a lot more factors to consider in order to make a more optimal guess.

### Exercise 5
12. As you continue the game and have less guesses left, it is better to play it safe with Minimax that can gurantee the number of possible words left in the list rather than Entropy that may use an incorrect guess to gather information.

13. A factor that could influence this decision includes word list size, how common the words are in that list, and whether you are trying to prioritze using the least amount of guesses with more risk vs have more accurate guesses even if it takes more turns. A method that could determine the optimal threshold would be switching when the word list narrows down to a certain percentage of the whole list.

14. 
    a. Run frequency since it works well with bigger word pools. It scales better than the other heuristics. Probably not ideal for the last few guesses as it doesn't do well with more uniquely constructed words.

    b. Run entropy second to gather more specific information about the narrowed down word pool. Good for a middle stage (but not the end stage) because its more computationally efficient but it may make suboptimal guesses in order to get information.

    c. Run minimax last to decrease risk especially when there are fewer guesses left. Better in the end stage as it is computationally heavy.

### Exercise 6
15. Entropy, which is best on average, also has the best worst case, although it took significantly longer than the other agents. Optimization criteria matters because some algorithms work better in certain situations. For instance near the end of the game (4th-5th guess) you would rather optimize worst-case performance to decrease risk, while in the beginning portion of the game, it would be better to optimize average case performance as frequency does to narrow the word list down effectively.

16.
    a. With only common words, the frequency agent will probably do really well since that agent is tailored to prioritize common character sequences.

    b. For unusual letter patterns, the frequency agent will naturally do worst, and the entropy agent will be more likely to make guesses, not becuase they are the answer, but to gain information. For both a and b Minimax perform similarly since it isn't depending on letter patterns or statistics, rather it depends on the word list and the size of potential partitions.

    c. With the 12,000+ word list, frequency would probably do the best as it scales the best as the word list increases. Entropy and Minimax would probably perform the same because the existing benchmark uses a random sample of words which statistically is representative of the full dictionary. Since the hybrid is a combination of the previous agents discussed, it would have the same effects applied to it within each stage respectively.

    d. We can assume our findings for a, b, and c are pretty generalizable. In fact, the agents may even perform similarly with other spoken languages because rather than depending on the languages' actually grammar, it depends on patterns from the given word list. If you give the agents a different word list, they will probably perform similarly with generalizable results.

17. We can balance the trade-off between solution quality and computation speed by switching between agents depending on time limits. One practical decision is to have a have a frequency agent run and have a guess word ready by default, and if theres more time, it also runs minimax to a certain level of confidence. If it gets to that level, you use the minimax guess, otherwise you use the frequency guess.

### Exercise 7
18. LLMs output the most likely next token in a sequence and are usually trained to prioritize successful actions. The lack of requirement for explicit training suggests these models transfer abstract reasoning skills that can be applied and tailored to different tasks, as opposed to specific rules and strategies.

19. For the rule-based agents, the transparency is dependant on the viewer's understanding of the strategy and code. Whereas for the RL/LLM agents, the reasoning is displayed and can be read through logs in natural language.

    The trade-off between interpretability and performance is that the more transparent the agent's reasoning is, the more computational time is required. This is because LLMs operate with high-level abstraction which while easier to understand from a human POV, takes longer for computers to process.

20. For the frequency agent, it greatly prefers exploitation over exploration. The entropy agent greatly prefers exploration and the minimax balances both similarly to the LLM model. Mostly they handle the trade-off with the fact that the strategies converge when there are fewer guesses left.

### Exercise 8
21. Repeated letters lower the amount of information gained per guess because the repeated letter takes up a space where otherwise you could use to rule out another character. So for instance, for the word "SACRA," the agent has to guess something with two As and cannot use those spaces to gain more information about other characters (if you are trying to make a correct guess).

22. Frequency would handle the one letter case trying to guess the most common word out of the remaining word list, although this may not be correct.

    Entropy would try to use the word that lowers the amount of unknowns. In the case of the word list being one letter different, it cannot gain that much information regarding by doind so.

    Minimax would choose the word that results in the best worst case scenaro. In the one-letter case, they all have the same worst case so this strategy would not be too influential on the decision.

    The LLM would chose a word that it sees as most commonly effective, but once again, with only a one letter difference, the decicion is still left with a considerable amount of randomness.

    In conclusion, they all end up choosing the word with similar levels of randomness. Not one strategy is significantly better than the rest. This lines up with our previous observations that the strategies start to converge as the possible guesses narrows down.

23. For the frequency agent, you could still have a probability component even with an unknown state space; they will just be less precise. 
    
    Entropy may do really well in an unknown state space since it is focused on gaining information through actions rather than depending on preconceived patterns about the game or world. 
    
    Minimax may have trouble calculating the scores within an unknown state but may still perform okay within a infinite space.

    In general, all agents would have to adapt to possibly encountering an enormous state space. If there is still a time limit agents such as Minimax that takes a long time to run may need to strictly balance optimality and feasibility.

    Some assumptions from the Wordle game that may break down is that the agent's strategy is feasible for the input in the state space. In the case of an infinite state space, some agents such as the frequency agent's calculations will be less accurate. 
    
    Additionally, in Wordle, there are only three categories of which a variable can fall into, green, yellow, and grey. In situations beyond wordle, variables may fall in to less or even more categories of which the agent will then need to take into account.

    A further assumption is that some guesses will be more probable than others. This is integral to the many strategies of Wordle as some words and combinations of letters are more common than others. In a state where this characteristic is not present, the agents that rely on that information would have at least a decrease in effectiveness if not rendered useless entirely.
