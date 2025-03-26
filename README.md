# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.

## POLICY EVALUATION FUNCTION
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V=np.zeros(len(P))
      for s in range(len(P)):
        for prob,next_state,reward,done in P[s][pi(s)]:
           V[s]+=prob*(reward+gamma *prev_V[next_state]*(not done))
      if np.max(np.abs(prev_V-V))<theta:
        break
      prev_V=V.copy()
    return V
```

## OUTPUT:

### First Policy:
![Screenshot 2025-03-26 104408](https://github.com/user-attachments/assets/ecf64855-d0c2-454d-b892-0338d6bb101c)
![Screenshot 2025-03-26 104435](https://github.com/user-attachments/assets/56fe727b-69b4-4018-b388-0c1003cbfe47)

### Second Policy:
![Screenshot 2025-03-26 104448](https://github.com/user-attachments/assets/c92c8979-55e7-4d8e-85f0-ee3611869ebb)
![Screenshot 2025-03-26 104536](https://github.com/user-attachments/assets/465bfb2f-df26-4978-a666-1e5eda5e0b7d)

### First and Second compared them:
![Screenshot 2025-03-26 104556](https://github.com/user-attachments/assets/f0bd4e21-8520-4668-85c2-80a068a4f4e9)

## RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.
