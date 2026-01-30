# Lab3 (Adversarial Search)

## Names: Jenessy Jane Lustre & Paul Hartman 
## January 30, 2026

1.

2. When a game is more complex, it would require more than randomly choosen moves in order to win. An agent would need to be able to determine chance of success with certain moves, it would also need to keep track of the other players moves and determine how close either player is to winning/losing to make informed decisions.

3. 
    a) With random agents, the game only lasts a few seconds. If the agent had a lookahead feature in order to determine moves with the best success, that would take longer to calculate, and thus games would last longer if the agents wanted to make more intelligent decisions.

    B) To win the game, you have to outlast the other player. Beause the agents are making random moves, they often crash into themselves since they are not thinking ahead and planning a good route. Additonally, they do not try to apply certain strategies to sabotage the other player. If they do run into each other, it is by chance.

4. In Tron, there is a limited amount of empty space and players would want to have control of that space to increase their chances of winning. With the flood-fill heuristic, the agents prioritize taking steps to get access to the most empty space available. The flood is taking advantage of the first few seconds of the game in that it takes over spaces the other player does not have proximity to.

5. Sometimes as a result of trying to fill as much space as possible, the flood-fill agent would loop around itself and thus crash and lose the game. The flood-fill heuristic focuses on local optimality, where it chooses the best decision in the moment but this example clearly shows that that decision is not the best play to win the game in the long run.

6. 
    a) For flood-fill it requires a stack to keep track of possible movements whereas the random agent does not have to make that calculation. This is still acceptable because the game still runs relatively quick.
    b) The flood-fill agent tends to move in straight vertical lines. Besides making it easier to observe visual patterns, you can also observe game length and how effective a heuristic is in an actual game.

7. Computing exact game outcomes require an exponential amount of calculations, so the trade off would be less accurate computations are more feasible to run. Minimax starts outperforming flood-fill at depth 5. At this point, it has a 100% success rate. This possibly suggests that if your lookahead encapsulates more of the board, this significantly improve the win rate of the agent.

8. The agent prunes moves that will not affect the final decision and thus the agent does not waste calculations on moves that would probably lead to unfavorable decisions. A scenario in which this would be very effective would be if there were two moves the agent could make, and one of them leads to a loss. With pruning, the agent would ignore the losing decision entirely. Pruning tends to be more beneficial as the game goes on since there are less possible moves to make (and thus less flexibility in how an agent could win).

9. 
    a) Minimax seems to want to interfer with the greedy player. It cuts them off so that P2 has to loop around itself and crash. On the other hand, greedy seems concerned with just filling as many spaces as possible, without regard to what P1 is doing. In this example, this strategy is helpful to minimax as it helps it win 100% of the time. This could lead to a loss where minimax is so focused on trapping the other player that it can end up trapping itself. You can even see this when you run the play that if P2 was able to last a little longer, P1 would have crashed into itself. Another instance where this would not help minimax is if its opponent is playing suboptimally (like if it was choosing random moves) because minimax would not be able to make good predictions.

    *b) With more lookahead, an agent can make higher quality evaluations as long as the heuristic aligns with the goal.

10. MCTS seems to evaluate move quality rather than position quality, where it is not concerned with the whole domain of the board when deciding a move. Instead, it is only concerned with possible outcomes of a move, the information it gets from its simulations. Due law of large numbers, the more simulations MCTS is able to run, the more its predictions become closer to reality and thus it is able to make more accurate decisions.

11. UCB1 exploration parameter tells the agent which nodes to expand while minimax's depth parameter tells it how deep of an exploration of a node goes, and not necessarily which ones to choose. UCB1 addresses the exploration-exploitation trade-off in that it dynamically chooses which nodes it explores whereas the depth parameter explores all nodes until a certain point.

*12. A game with a deep tree, in order to make good predictions, minimax would have to check all nodes, requiring a higher depth value. On the other hand MCTS can focuses on promising moves rather than exploring all options. In short, if minimax does not have a high depth value, its evaluations will have less quality while MCTS is able to decide which moves are better with less computation.


13. If your LLM is well trained on the game and is given well structured prompts and high quality information, it will be able to give good responses. On the other hand, if the input is more vague, the LLM will not be able to do well in less common, specific instances. Additionally, LLMs take a lot of computational cost compared to traditional algorithms.

14. Prompt engineering is crucial for an LLM's performance because depending on the quality and structure of the prompt, you can get entirely different answers even if the prompt seems to ask for the same thing. For instance, saying "choose the best next move" is very vague and it can cause the LLM to miss important details. On the other hand, being more specific in the prompt, like asking it to imploy a certain strategy (like cutting off the opponent) or giving certain information like the opponent's strategy, results in better performance specific to the instance.

15. -

16. 