# Homework 1: Introduction and Multi-armed Bandits

**Hamed Batani · Reinforcement Learning · Fall 2026**

This assignment combines derivations of bandit learning rules with numerical comparisons of exploration strategies. My submission includes written theoretical answers, a simulation notebook with saved plots and discussion, and exported result figures.

## Materials

- **[Course question sheet](questions/RL_HW1.pdf):** original six-page assignment, covering theoretical and implementation parts.
- **[My theoretical answers](theoretical-solutions/main.pdf):** six-page PDF, with [editable LaTeX source](theoretical-solutions/main.tex).
- **[My simulation answers](simulation/HW1_402101339.ipynb):** notebook containing implementations, saved outputs, and interpretation.
- **[Result figures](simulation/results/):** 18 exported PNG figures grouped by question and subpart.

## Theoretical part

| Problem | Topic | Content of my answers |
|---|---|---|
| 1 | Upper Confidence Bound (UCB) | Estimated reward, uncertainty bonus, sample count, and exploration coefficient |
| 2 | Gradient bandit | Softmax differentiation, stochastic gradient ascent, and the role of an action-independent reward baseline |
| 3 | Reward estimation | Incremental sample average, expansion of the constant-step-size recursion, and adaptation versus noise |
| 4 | Optimistic initialization | Greedy action sequences under optimistic and zero initial estimates; implications for exploration |

## Simulation part

| Question and part | Experiments | Output folder |
|---|---|---|
| Q1, Part 1 | Ten-armed Gaussian bandits, epsilon-greedy sample averages, short/long trajectories, moving reward average, and repeated fixed/random environments | `simulation/results/question_1/part_1/` |
| Q1, Part 2 | Constant-step-size sweep and comparison with sample averages, including time to 80% optimal-action selection | `simulation/results/question_1/part_2/` |
| Q1, Part 3 | Tracking changing arm means under random-walk drift | `simulation/results/question_1/part_3/` |
| Q2, Task 1 | Epsilon-greedy exploration-rate sweep | `simulation/results/question_2/task_1/` |
| Q2, Task 2 | UCB versus epsilon-greedy using reward, optimal-action percentage, and cumulative regret | `simulation/results/question_2/task_2/` |
| Q2, Task 3 | Gradient bandits with and without an average-reward baseline | `simulation/results/question_2/task_3/` |

The repeated experiments use 2,000 runs. Q1's main comparisons span 1,000 steps; Q2 uses 500 steps. The notebook records seeds and reuses environments and reward-noise draws across relevant algorithm comparisons.

## Interpretation and significance

Bandits isolate the exploration–exploitation problem without state-transition dynamics. They make it possible to study how limited observations shape decisions, why greedy estimates can neglect promising actions, and how uncertainty-aware or stochastic policies collect useful information. Comparing stationary and changing rewards also shows why an estimator that averages all past data may adapt poorly when the underlying environment drifts.

The notebook discusses parameter choices in relation to the experimental horizon and evaluation criterion. Its observations are finite-simulation results rather than universal rankings of algorithms. In Q1 Part 3, the assignment's prose and equation disagree about drift variance; my notebook follows the equation, using standard deviation 0.1 and variance 0.01.

See [the simulation guide](simulation/) for execution instructions and [the archive notes](../../ARCHIVE_NOTES.md) for verification limits.
