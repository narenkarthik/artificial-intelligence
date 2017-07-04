# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Naked twins, like elimination & only-choice strategies reduces the possible values for boxes in the Sudoku. Repeating this constraints over and over against the input space reduces the number of possible values to minimum or in best case solves the Sudoku. I have created `naked_ns()` method which can be used to build `naked_twins()`, `naked_triplets()`, `naked_quadruplets()` and so on...

I have implemented the `naked_twins()` and `naked_triplets()` using `naked_ns()` in the submitted solution. The `naked_ns()` can be used to implement higher order functions like `naked_quadruplets()` and above to quicken the constraint propagation to solve more complex and bigger sudoku like 16X16 sudoku or 25X25 sudoku as the input space in these puzzles are magnitudes higher.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Diagonal sudoku have an additional restriction which actually helps in quicker constraint propagation. This is because unlike each of the 81 boxes in the regular sudoku, which has 3 set of peers, which is 20 peer boxes, the diagonal sudoku has 64 boxes each with 3 set of peers having 20 peer boxes and 17 boxes each with 4 set of peers having 26 peers. This helps in restricting and zeroing in on unique values for each of these 17 boxes by adding 6 boxes to consider in elimination, only-choice and `naked twins()` and `naked_triplets()`. 

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the `assign_value` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login) for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

