# Rubiks-Cube-Solver <br/>
Program that solves the Rubik's cube <br/>

### Rubik's Cube Basics: <br/>
  Rubik's cube movements are typically written in terms of 6 basic letters that represent the Front (F), Back (B), Left (L), Right (R), Up (U), and Down (D) faces on a Rubik's cube relative to the person holding the cube. <br/>
  The letters by themselves (such as F) represent a clockwise 90 degree movement, while letters with an apostrophe (such as R') denote a counterclockwise 90 degree movement and letters with a '2' (such as U2) stand for a double movement in any direction. <br/>
  Any other amount of movements in either clockwise or counterclockwise direction will yield the same result as either of the three movements I explained. Thus, if any redundancy is found, the algorithm can be simplified. <br/>
  Examples of redundancy: <br/>
  - L L' = no moves (doesn't change anything, because the move was reverted), <br/>
  - B B2 = B' (three moves in the clockwise direction can simply be written as a single move in the counterclockwise direction), and <br/>
  - D2 D D2 D2 = D' (seven movements in the clockwise direction equal 4 + 3 movements, where after the first four the cube reverts to its original state, so the net change in the cube is three clockwise movements or simply one counterclockwise movement). <br/>
A Rubik's cube has three types of pieces or "cubies": <br/>
  - 6 centers that have one sticker each are fixed respect to each other, <br/>
  - 12 edges that have two stickers each, and <br/>
  - 8 edges that have three stickers each. <br/>
  A collection of one or more movements that lead to a particular state are called algorithms. The "particular state" can sometimes be a scrambled cube, so although it may seem counterintuitive, "scramble algorithms" exist. <br/>
  

### Synopsis: <br/>
  The program creates a double array of "pieces" (objects) and assigns a numerical value to each relevant piece (note that what my program refers to as pieces are actually stickers, but the program moves the cube as if they were entire pieces or "cubies"). <br/>
  The program takes in the user's scrambler algorithm, simplifies it, and performs those movements on a solved Rubik's cube. <br/>
  The scrambler algorithm is translated and added into a queue called "scramblerAlg", then the elements of the queue are added into a linked list in which the algorithm can be simplified. <br/>
  The program utilizes what is commonly referred to as the "beginner's method", a simple 7-step method to solve the Rubik's cube, showing the user each step (graphically and with words). <br/>
  Each step in the beginner's method is represented by a function, and each function calls other helper functions, which in turn call functions that perform individual face moves (for example F, D' R2, L, etc.). <br/>
  Each individual face move is added to a queue called "solverAlg". Then this queue is passed in to the simplifier method, which as explained earlier, copies the content of the queue into a linked list and simplifies it, and then returns those values to the queue. <br/>
  The program outputs the algorithm (set of individual face moves) it used and writes down the simplified version that the user can use to solve the cube, given the scramble he/she provided at the beginning. <br/>
  
