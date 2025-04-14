I know aware there may be more optimal approaches but but based on the given path, my logic proceeds as follows::
Firstly we see the cost of movement of in all the four directions 
And then the movement will happen in that direction where cost is minimum given that the priority of movement is right, down, left, up.
Because ultimate goal is to move from point S to G.
We begin by initializing the minimum cost to infinity then we see that in which direction is the cost minimum by comparing with min_cost(which is setted as infinity) and then adding it to the actual cost.
Also we add the coordinates of the new point we go in the path list then finally we print the coodinates of the robot of which the path he chooses and we print the final cost. 
