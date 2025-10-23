<img width="1024" height="538" alt="L_1 3" src="https://github.com/user-attachments/assets/cb66a744-8180-48e2-bdeb-d9a679974141" />


---

# Lesson 1.3: The Language of Learning: Rewards and Policies

In the last lesson, we established the main players (Agent, Environment) and the cycle of their interaction (State, Action). But we left a big question unanswered: How does the agent learn to choose *good* actions over *bad* ones?

The answer lies in two final key concepts: **Rewards** and **Policies**.

## The Motivation: Reward (R)

A **Reward** is a numerical signal that the environment sends back to the agent. It's feedback that says, "What you just did was good" or "What you just did was bad."

*   A **positive reward** is like a treat for a dog or earning points in a game.
*   A **negative reward** (sometimes called a penalty or cost) is like bumping into a wall or losing health points.
*   A **zero reward** is neutral, meaning the action was neither particularly good nor bad.

The agent's one and only goal is to **maximize the total reward it collects over time.** This simple, singular goal drives all of its learning.

**Roomba Example:**
*   `Action`: Move forward -> `State`: Bumps into a chair -> `Reward`: -5 (Ouch!)
*   `Action`: Start vacuuming -> `State`: Sucks up a pile of dirt -> `Reward`: +10 (Good job!)
*   `Action`: Move forward -> `State`: Moves to an empty, clean square -> `Reward`: -0.1 (A small penalty to encourage efficiency and discourage wasting battery)

### The Marshmallow Test: Cumulative vs. Immediate Reward

A smart agent doesn't just try to get the biggest reward *right now*. It tries to maximize the **cumulative reward** over the long run. This is one of the most important ideas in RL.

Think of the classic "marshmallow test." A child is offered one marshmallow now, or they can wait 15 minutes and get two.

*   An agent focused only on **immediate reward** would eat the one marshmallow right away.
*   An agent focused on **cumulative reward** would learn to wait, sacrificing a small immediate reward for a much larger future reward.

An RL agent must learn this same patience. It might need to take several actions with small negative rewards (like moving across a room, costing battery) to reach a state with a very large positive reward (like a huge mess to clean up).

## The Brain: The Policy (π)

So, the agent has a goal (maximize cumulative reward). But how does it decide which action to take to achieve that goal? That's the job of the **Policy**.

The **Policy (π)** is the agent's brain or strategy. It's the set of rules the agent uses to map a given state to an action.

*   **Simple Policy:** A set of hard-coded if-then rules.
    *   *Policy for a thermostat:* `IF the room temperature is > 72°F, THEN the action is 'turn on AC'.`
*   **Learned Policy:** In RL, the policy is what the agent learns and improves over time. It starts out random and, through trial and error (guided by rewards), gets better and better.
    *   *Policy for a chess AI:* The policy is a complex function that looks at the board state and chooses the move most likely to lead to a win.

Essentially, the entire goal of the Reinforcement Learning process is to find an **optimal policy**—a policy that is better than all other policies at maximizing the total cumulative reward.

## Diagram: The Full Agent-Environment Loop

Now we can complete our diagram. The agent's internal Policy (π) observes the State and Reward, and uses them to choose an Action.

<img width="619" height="565" alt="image" src="https://github.com/user-attachments/assets/d1d07a2a-72ec-4b14-8ea9-af418b2768ff" />



With these four components—State, Action, Reward, and Policy—we now have a complete, high-level picture of the Reinforcement Learning framework.

---

## 📝 Lesson 1.3 Quiz

**Q1:** An agent in a maze gets a reward of `+50` for finding the exit and `-1` for every step it takes. What behavior is this reward structure designed to encourage?

a) To explore as much of the maze as possible.
b) To find the exit using the shortest path possible.
c) To avoid walls at all costs, even if it means never reaching the exit.

<details>
  <summary>Click to see the answer</summary>
  
  **Answer: b) To find the exit using the shortest path possible.**
  
  *Explanation:* The agent gets a big reward for the goal, but it is penalized for every action it takes. This incentivizes the agent not just to find the exit, but to do so efficiently, minimizing the number of steps to maximize its total score (`50 - number_of_steps`).
</details>

<br>

**Q2:** In chess, a brilliant move might involve sacrificing your queen (a very valuable piece). Why might an RL agent learn to make such a move?

a) Because the policy is random and makes mistakes.
b) Because the agent is focused on maximizing the immediate reward.
c) Because the agent has learned that this short-term loss leads to a much higher long-term cumulative reward (winning the game).

<details>
  <summary>Click to see the answer</summary>
  
  **Answer: c) Because the agent has learned that this short-term loss leads to a much higher long-term cumulative reward (winning the game).**

  *Explanation:* This is a perfect example of the "marshmallow test." Sacrificing the queen is a huge immediate penalty, but if the agent's policy has learned that this move opens up a path to checkmate a few turns later, it will choose the action that maximizes its chances of winning in the long run.
</details>

<br>

**Q3:** What is a **Policy (π)** in Reinforcement Learning?

a) The total score the agent has accumulated.
b) The agent's strategy for choosing an action in a given state.
c) A rule that the environment must follow.

<details>
  <summary>Click to see the answer</summary>
  
  **Answer: b) The agent's strategy for choosing an action in a given state.**

  *Explanation:* The policy is the core of the agent's decision-making. It's the function or "brain" that maps what the agent sees (the state) to what it does (the action).
</details>

---

## 🏁 Module 1 Wrap-up Quiz

You've completed the first module! Let's test your understanding of all the core concepts we've covered.

**Q1:** A company trains a robotic arm to sort apples and bananas. They do this by showing it 10,000 pictures of apples and 10,000 pictures of bananas, each with the correct label. The robot then uses this knowledge to place fruit from a conveyor belt into the correct bins. What type of Machine Learning is this?

a) Reinforcement Learning
b) Supervised Learning
c) Unsupervised Learning

<details>
  <summary>Click to see the answer</summary>
  
  **Answer: b) Supervised Learning**
  
  *Explanation:* The key is that the robot was trained on a pre-existing, labeled dataset ("pictures of apples... with the correct label"). It's learning to classify from a "teacher," not through its own trial and error. If, instead, the robot learned by trying to pick up fruit and getting a reward for placing it in the correct bin, that *would* be Reinforcement Learning. (Lesson 1.1)
</details>

<br>

**Q2:** You are building an RL agent to trade stocks. Which of the following is the best description of the **State, Action, and Reward**?

a) **State**: The current stock prices. **Action**: Buy, sell, or hold. **Reward**: Profit or loss.
b) **State**: Profit or loss. **Action**: The current stock prices. **Reward**: Buy, sell, or hold.
c) **State**: Buy, sell, or hold. **Action**: Profit or loss. **Reward**: The current stock prices.

<details>
  <summary>Click to see the answer</summary>
  
  **Answer: a) State: The current stock prices. Action: Buy, sell, or hold. Reward: Profit or loss.**

  *Explanation:* The **State** is what the agent observes to make a decision (stock prices, market trends, etc.). The **Action** is the decision it makes (buy, sell, hold). The **Reward** is the feedback it receives based on that action's outcome (the money it made or lost). (Lesson 1.2 & 1.3)
</details>

<br>

**Q3:** Your Roomba-cleaning agent isn't learning to clean the whole house. It just moves back and forth over a single small patch of dirt, collecting a small reward each time, and never explores to find the bigger messes in other rooms. What is the most likely problem?

a) The agent's policy is too focused on long-term cumulative reward.
b) The environment is broken and is not providing a state.
c) The agent's policy is too "greedy," focusing on immediate rewards instead of exploring for better long-term rewards.

<details>
  <summary>Click to see the answer</summary>
  
  **Answer: c) The agent's policy is too "greedy," focusing on immediate rewards instead of exploring for better long-term rewards.**

  *Explanation:* This is a classic RL challenge. The agent has found a "local maximum"—a strategy that gives it a small, reliable reward. It hasn't learned to make the short-term sacrifice (moving away from the known dirt and getting zero reward) to potentially find a much larger reward elsewhere. This is the "one marshmallow now" problem. (Lesson 1.3)
</details>

---

Congratulations on finishing Module 1! You now have a solid grasp of the fundamental concepts and vocabulary of Reinforcement Learning. In the next module, we will start to formalize these ideas with a mathematical framework.

[**&laquo; Previous Lesson: 1.2 The Core Components: Agents and Environments**](Lesson_1.2.md) | [**Next Module: 2. Markov Decision Processes &raquo;**](../../module-02-mdps/01-markov-property.md)
