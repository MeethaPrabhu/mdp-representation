# MDP REPRESENTATION

## AIM:
To create a MDP (Markov Decision Process) for the undertaken problem statement

## PROBLEM STATEMENT:

### Problem Description
Maze-Navigator, a simple game that takes place within 3x3 grid or possibly 9 states and 4 actions
### State Space
The game had 3x3 states or simply 9 states

### Sample State
The sample states are in the coordinates form [(0,0), (0,1), (0,2), (1,0), (1,1), (1,2), (2,0), (2,1), (2,2)]

### Action Space
There are four actions 
Left   - 0

Right  - 1

Down   - 2

Up     - 3

### Sample Action


### Reward Function
Moving to the next state  - +1
Staying in the same state - -1
Reaching the goal state   - +10

### Graphical Representation
![WhatsApp Image 2024-08-20 at 20 33 25_abeea98f](https://github.com/user-attachments/assets/a4dce949-1c52-469f-8bac-0ebf20d35da7)


## PYTHON REPRESENTATION:
```
solver_mdp = {
    # State 0: Top-left corner (0,0)
    0: {
        1: [(0.9, 1, -1, False), (0.1, 0, -1, False)],  # Right action: 90% move to (0,1), 10% stay in (0,0)
        2: [(0.9, 3, -1, False), (0.1, 0, -1, False)],  # Down action: 90% move to (1,0), 10% stay in (0,0)
    },
    # State 1: Top-middle (0,1)
    1: {
        0: [(0.9, 0, -1, False), (0.1, 1, -1, False)],  # Left action: 90% move to (0,0), 10% stay in (0,1)
        1: [(0.9, 2, -1, False), (0.1, 1, -1, False)],  # Right action: 90% move to (0,2), 10% stay in (0,1)
        2: [(0.9, 4, -1, False), (0.1, 1, -1, False)],  # Down action: 90% move to (1,1), 10% stay in (0,1)
    },
    # State 2: Top-right corner (0,2)
    2: {
        0: [(0.9, 1, -1, False), (0.1, 2, -1, False)],  # Left action: 90% move to (0,1), 10% stay in (0,2)
        2: [(0.9, 5, -1, False), (0.1, 2, -1, False)],  # Down action: 90% move to (1,2), 10% stay in (0,2)
    },
    # State 3: Middle-left (1,0)
    3: {
        1: [(0.9, 4, -1, False), (0.1, 3, -1, False)],  # Right action: 90% move to (1,1), 10% stay in (1,0)
        2: [(0.9, 6, -1, False), (0.1, 3, -1, False)],  # Down action: 90% move to (2,0), 10% stay in (1,0)
        3: [(0.9, 0, -1, False), (0.1, 3, -1, False)],  # Up action: 90% move to (0,0), 10% stay in (1,0)
    },
    # State 4: Center (1,1)
    4: {
        0: [(0.9, 3, -1, False), (0.1, 4, -1, False)],  # Left action: 90% move to (1,0), 10% stay in (1,1)
        1: [(0.9, 5, -1, False), (0.1, 4, -1, False)],  # Right action: 90% move to (1,2), 10% stay in (1,1)
        2: [(0.9, 7, -1, False), (0.1, 4, -1, False)],  # Down action: 90% move to (2,1), 10% stay in (1,1)
        3: [(0.9, 1, -1, False), (0.1, 4, -1, False)],  # Up action: 90% move to (0,1), 10% stay in (1,1)
    },
    # State 5: Middle-right (1,2)
    5: {
        0: [(0.9, 4, -1, False), (0.1, 5, -1, False)],  # Left action: 90% move to (1,1), 10% stay in (1,2)
        2: [(0.9, 8, 100, True), (0.1, 5, -1, False)],  # Down action: 90% move to (2,2) (goal), 10% stay in (1,2)
        3: [(0.9, 2, -1, False), (0.1, 5, -1, False)],  # Up action: 90% move to (0,2), 10% stay in (1,2)
    },
    # State 6: Bottom-left (2,0)
    6: {
        1: [(0.9, 7, -1, False), (0.1, 6, -1, False)],  # Right action: 90% move to (2,1), 10% stay in (2,0)
        3: [(0.9, 3, -1, False), (0.1, 6, -1, False)],  # Up action: 90% move to (1,0), 10% stay in (2,0)
    },
    # State 7: Bottom-middle (2,1)
    7: {
        0: [(0.9, 6, -1, False), (0.1, 7, -1, False)],  # Left action: 90% move to (2,0), 10% stay in (2,1)
        1: [(0.9, 8, 100, True), (0.1, 7, -1, False)],  # Right action: 90% move to (2,2) (goal), 10% stay in (2,1)
        3: [(0.9, 4, -1, False), (0.1, 7, -1, False)],  # Up action: 90% move to (1,1), 10% stay in (2,1)
    },
    # State 8: Bottom-right (2,2) - Goal State
    8: {
        # No actions needed since this is the terminal state
    }
}
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/a1bd1a47-b6a7-4d7a-9397-f42b71cb0e68)

## RESULT:
Thus, the MDP for a stochastic model (game) using python is implemented successfully
