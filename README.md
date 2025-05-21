<TODO: Jeff Kim>: <TODO: 70668132>

Comments to TA about your implementation (optional):
- Examples: known bugs or incomplete implementation
For procedurally generated path, I implemented biased DFS. I first generate a path going from the start to the exit, then I add the tiles in based on
previous coordinates and the next coordinates. To generate the path, I look at all the directions I could travel and if there is no issue, I put that direction
into a list with a weight. If the path is going towards the exit, I give the direction extra weight. I then randomly choose a direction to travel with 
emphasis on the weight and repeat. To make the path look more natural, I always go two tiles up, down, left, or right. This makes the path look much more natural
when I is generated. 

- To test if map is loaded/ has a valid path, I utilized level 6, which has a straight path from start to finish with one pathway removed. Additionally, I utilized 
level 9 to ensure a non-saved level would count as an invalid level.

- for points, I decided to use a more structured approach for the points. Invaders with the lowest amount of HP give the least amount of points but give at least 2
The second most hp invaders give a range between 4-7, and the enemies with the most hp give 6-9 points. I thought this was more fair because the tougher enemies
are difficult to beat compared to the fast low hp ones.