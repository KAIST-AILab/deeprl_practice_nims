# Deep RL 실습
- 이 GitHub Repository는 2018년 9월 14일 진행할 성남 AI 교육실습을 위해 제작되었습니다.

## 설치
1. 이 GitHub Repository를 사용하고자 하는 로컬로 clone
2. 가상환경 생성 및 패키지 설치 `conda env create -f environment.yml`
3. Jupyter notebook 에서 각 실습자료 노트북 파일들(`1_Q-learning_maze.ipynb`, `2_DQN_classic_control.ipynb` )을 실행


## 실습 1 : Q-learning in 2D Maze

> 실습 1은 https://github.com/MattChanTK/gym-maze 를 기반으로 제작되었습니다.

A simple 2D maze environment where an agent (blue dot) finds its way from the top left corner (blue square) to the goal at the bottom right corner (red square).
The objective is to find the shortest path from the start to the goal.

<kbd>![Simple 2D maze environment](http://i.giphy.com/Ar3aKxkAAh3y0.gif)</kbd>

### Action space
The agent may only choose to go up, down, left, or right ("N", "S", "W", "E"). If the way is blocked, it will remain at the same the location.

### Observation space
The observation space is the (x, y) coordinate of the agent. The top left cell is (0, 0).

### Reward
A reward of 1 is given when the agent reaches the goal. For every step in the maze, the agent receives a reward of -0.1/(number of cells).

### End condition
The maze is reset when the agent reaches the goal.

## Maze Versions

### Pre-generated mazes
* 3 cells x 3 cells: _MazeEnvSample3x3_
* 5 cells x 5 cells: _MazeEnvSample5x5_
* 10 cells x 10 cells: _MazeEnvSample10x10_
* 100 cells x 100 cells: _MazeEnvSample100x100_

### Randomly generated mazes (same maze every epoch)
* 3 cells x 3 cells: _MazeEnvRandom3x3_
* 5 cells x 5 cells: _MazeEnvRandom5x5_
* 10 cells x 10 cells: _MazeEnvRandom10x10_
* 100 cells x 100 cells: _MazeEnvRandom100x100_

### Randomly generated mazes with portals and loops
With loops, it means that there will be more than one possible path.
The agent can also teleport from a portal to another portal of the same colour.
* 10 cells x 10 cells: _MazeEnvRandom10x10Plus_
* 20 cells x 20 cells: _MazeEnvRandom20x20Plus_
* 30 cells x 30 cells: _MazeEnvRandom30x30Plus_

## Installation
It should work on both Python 2.7+ and 3.4+. It requires pygame and numpy.

```bash
cd gym-maze
python setup.py install
```
## Examples
An example of finding the shortest path through the maze using Q-learning can be found here: https://github.com/tuzzer/ai-gym/blob/master/maze_2d/maze_2d_q_learning.py

![Solving 20x20 maze with loops and portals using Q-Learning](http://i.giphy.com/rfazKQngdaja8.gif)


## 실습 2 : Q-learning in 2D Maze
- `2_DQN_classic_control.ipynb`
