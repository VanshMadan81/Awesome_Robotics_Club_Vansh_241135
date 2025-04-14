I know aware there may be more optimal approaches but according to the path given:
Firstly we see the cost of movement of in all the four directions 
And then the movement will happen in that direction where cost is minimum given that the priority of movement is right, down, left, up.
Because ultimate goal is to move from point S to G.
We take the initial cost as infinity then we see that in which direction is cost minimum by comparing with min_cost and then adding it to the actual cost.
Also we add the coordinates of the new point we go in the path list then finally we print the coodinates of the robot of which the path he chooses and we print the final cost. 
