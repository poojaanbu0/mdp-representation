# MDP REPRESENTATION
## AIM:
The representation of real world scenario using Markov Decision Process by stating all the states,actions and environment with respective rewards.

## PROBLEM STATEMENT:
Traffic signal control optimization

### Problem Description
To learn the best timing for each traffic signal light to improve traffic flow while ensuring safety 

### State Space
The traffic signal has 3 Intersections or 3 states

### Sample State
Intersection 1 : 0
Intersection 2: 1
Intersection 3: 2

### Action Space
There are 3 action space :
green : move forward 
yellow : get ready 
red : stop

### Sample Action
Action : yellow -> get ready 
can change to red / move another intersection / stay yellow

### Reward Function
green: 10,    # Reward for keeping the light green
yellow: 5,    # Reward for transitioning to yellow
red: -5       # Penalty for being in red

### Graphical Representation


## PYTHON REPRESENTATION:
```
import random

P = {
    0: {
        "green": [
            (0.9, 0, "yellow", 10, False),  # 90% chance to go to yellow, reward 10
            (0.1, 0, "green", 10, False)    # 10% chance to stay green, reward 10
        ],
        "yellow": [
            (0.7, 0, "red", 5, False),       # 70% chance to go to red, reward 5
            (0.2, 1, "green", 10, False),    # 20% chance to go to intersection_2 green, reward 10
            (0.1, 0, "yellow", 5, False)     # 10% chance to stay yellow, reward 5
        ],
        "red": [
            (0.8, 0, "green", -5, True),     # 80% chance to go to green, penalty -5
            (0.2, 0, "red", -5, True)        # 20% chance to stay red, penalty -5
        ]
    },
    1: {
        "green": [
            (0.9, 1, "yellow", 10, False),  # 90% chance to go to yellow, reward 10
            (0.1, 1, "green", 10, False)    # 10% chance to stay green, reward 10
        ],
        "yellow": [
            (0.7, 1, "red", 5, False),       # 70% chance to go to red, reward 5
            (0.2, 0, "green", 10, False),    # 20% chance to go to intersection_1 green, reward 10
            (0.1, 1, "yellow", 5, False)     # 10% chance to stay yellow, reward 5
        ],
        "red": [
            (0.8, 1, "green", -5, True),     # 80% chance to go to green, penalty -5
            (0.2, 1, "red", -5, True)        # 20% chance to stay red, penalty -5
        ]
    },
    2: {
        "green": [
            (0.9, 2, "yellow", 10, False),  # 90% chance to go to yellow, reward 10
            (0.1, 2, "green", 10, False)    # 10% chance to stay green, reward 10
        ],
        "yellow": [
            (0.7, 2, "red", 5, False),       # 70% chance to go to red, reward 5
            (0.2, 1, "green", 10, False),    # 20% chance to go to intersection_2 green, reward 10
            (0.1, 2, "yellow", 5, False)     # 10% chance to stay yellow, reward 5
        ],
        "red": [
            (0.8, 2, "green", -5, True),     # 80% chance to go to green, penalty -5
            (0.2, 2, "red", -5, True)        # 20% chance to stay red, penalty -5
        ]
    },
    3: {  
        "green": [
            (0.9, 3, "yellow", 10, False),  # 90% chance to go to yellow, reward 10
            (0.1, 3, "green", 10, False)    # 10% chance to stay green, reward 10
        ],
        "yellow": [
            (0.7, 3, "red", 5, False),       # 70% chance to go to red, reward 5
            (0.2, 2, "green", 10, False),    # 20% chance to go to intersection_3 green, reward 10
            (0.1, 3, "yellow", 5, False)     # 10% chance to stay yellow, reward 5
        ],
        "red": [
            (0.8, 3, "green", -5, True),     # 80% chance to go to green, penalty -5
            (0.2, 3, "red", -5, True)        # 20% chance to stay red, penalty -5
        ]
    }
}
P
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/d66f2aa8-1aee-49a9-9160-7b3532280541)

## RESULT:
Thus, the MDP for a stochastic model (Traffic signal optimization) using python is implemented successfully.
