# Snake-AI

A snake game AI written in c/c++.

The goal is to eat all the food and make the map fill with the snake's bodies. 

## What can this program do?

* Play classic snake game.

* Watch how an AI snake eat food.

* Used as a console/terminal graphics library.

## Getting Started

Compile and run

```bash
$ make
$ make run
```

For usage, see function [main()](./src/main.cpp)

## Keyboard Control

| Key | Feature |
|:---:|---------|
|W|move up|
|A|move left|
|S|move down|
|D|move right|
|Space|pause/resume game|
|Esc|terminate game|

## Demo

* Snake AI

  ![](img/AI.gif)
   
Graph algorithms (green area is scanned when searching and red area is the path)

* Dijkstra

  ![](img/dijkstra.gif)

* Dijkstra + A*

  ![](img/dijkstra_Astar.gif)

Other algorithms

* Maze generate

  ![](img/maze.png)

## How does the AI algorithm work?

Function [Snake.decideNext()](./src/Snake.cpp) will compute the next move direction(***D***) of the snake.

Procedure:

1. Compute the shortest path(***P1***) from the origin snake(***S1***)'s head to food.
 
2. Move a virtual snake ***S2***(the same as ***S1***) to eat the food along ***P1***.
 
3. Compute the longest path(***P2***) from the ***S2***'s head to its tail. If ***P2*** exists, let ***D*** be the first direction in ***P1***. Otherwise go to step 4.
 
4. Compute the longest path(***P3***) from the ***S1***'s head to its tail. If ***P3*** exists, let ***D*** be the first direction in ***P3***. Otherwise go to step 5.
 
5. Let ***D*** be the direction that makes the snake the farthest from the food.

For more in Chinese, please see [中文博客](http://blog.csdn.net/qq_22885773/article/details/51888925)

## Todos

* Optimize AI algorithm

  AI algorithm is imperfect since the snake sometimes moves to an insoluable situation(just run the program and you will see).

## License

See the [LICENSE](./LICENSE.md) file for license rights and limitations.
