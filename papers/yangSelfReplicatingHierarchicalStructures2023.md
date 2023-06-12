# Self-Replicating Hierarchical Structures Emerge in a Binary Cellular Automaton

This is supposedly the first time a CA rule has been evolved through GP that can create self-replicating structures in a binary CA. First time that something has been self-replicating with only binary states and in two spatial dimensions.

The basic structure of the CA is a dead and alive system much like Convway's Game of Life. The difference are just the rules that lead to whether or not a center cell is considered dead.

Interesting that they purposefully keep the rules extremely simple which allows for computational efficiecy. It's less about *how* simple your rules are, and more about how long you have to search. If you have a system with enough states, then it's about the length of the search moreso than the complexity. 

To generate higher levels of complexity, they use *Novelty Search* from a feature map that they use to quantify complexity.

> Q: How is it that you can quantify it like this?

They note that the *Outlier* rule has 220 states that lead to alive and perhaps that is closer to the *edge of chaos*. This is more than the 140 rules in the Game of Life. 