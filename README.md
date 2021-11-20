# Inference-Agent-to-solve-maze
We return to the gridworld of Project 1. We have a dim by dim square grid, where cells are blocked with probability
p. A robot wants to navigate from the upper left to lower right corner as before. In the previous project, we looked at
Repeated A , and the e ect of the  eld of view - being able to see all four cardinal neighbors vs being `blindfolded',
and only being able to see/detect obstacles when you bump into them. One e ect of this is that with the larger
 eld of view, you can `passively perceive' the neighborhood around you, and learn the location of obstacles without
actually having to move in that direction - the blind robot can only actively perceive, via bumping into obstacles
directly. You should've seen that the passive perception robot has an advantage, as it learns about the environment
faster.
But what if you had partial information? Consider the following case: when the agent is in a cell, it can sense how
many obstacles are neighboring it, but not where they are. A given interior cell (not against the wall) has eight
possible neighbors (N,S,E,W,NW,NE,SW,SE) - the agent may sense that three of these neighbors are obstacles (for
instance), but not which three. (Cells along the borders have smaller neighborhoods but the same structure applies
- the agent senses how many of the neighboring cells are obstacles, but not which.)
Clearly this is informative - knowing that there are 0 neighboring obstacles means that you can move freely in any
direction. But for larger numbers of sensed obstacles, while this provides information, it is not necessarily clear
cut information. However, as the agent explores and determines that cells are in fact empty, the partial sensed
information can become more informative: if you know that there is a single obstacle nearby, you try to move in a
given direction and discover an obstacle, you immediately know the remaining directions are clear.
So consider the following setup: build an agent that is blind folded (can tell a cell is blocked when it attempts to move
there and fails, as in Project 1), but also has access to the partial sensing information. Design your agent to utilize
this partial information and the complete information (of discovering cells) to try to work out and understand its
environment faster. How does this hybrid agent compare in performance to your Project 1 Agents (the Blindfolded
Agent and the Agent That Can See Four Neighbors)? Notice that the agent for this project has a larger ' eld of
view' - it can see all eight neighbors at once - but it is partially obscured in that it can't know which neighbors are
blocked. Is this better or worse than seeing only the four cardinal neighbors perfectly?
