# Semi-Markov Decision Processes and Temporal Abstraction

**Prepared and presented by Hamed Batani in Reinforcement Learning class on 24 October 2026.**

**[View the original presentation](SMDP.pdf)** · Four slides

## Subject and motivation

I prepared this presentation to explain why the duration of an action matters in sequential decision-making. A conventional discrete-time Markov decision process describes transitions at successive decision epochs. An SMDP extends this representation by associating transitions with a potentially variable holding time. This makes it possible to evaluate decisions whose consequences unfold over different durations, rather than treating every high-level action as one identical unit of time.

The presentation develops this intuition through blitz chess and autonomous-driving maneuvers. The first example motivates accounting for time spent on a decision; the second illustrates how a maneuver can be represented as a temporally extended skill instead of a long sequence of primitive control commands. These are conceptual examples, not implemented chess or autonomous-driving systems.

## Why the topic is important

Temporal abstraction allows a high-level policy to reason about meaningful activities while a lower-level policy executes their constituent actions. In the options framework, an option consists of an initiation set, an internal policy, and a termination condition. Markov options over an underlying MDP induce an SMDP at their decision boundaries [2]. This provides a mathematical connection between ordinary reinforcement learning and planning with reusable skills.

Duration also changes how rewards and future outcomes should be compared. For an option lasting $\tau$ primitive time steps, the discounted return accumulated during execution is

$$
R_t^{(\tau)} = \sum_{k=0}^{\tau-1}\gamma^k r_{t+k+1}.
$$

A corresponding optimality relation is

$$
Q^*(s,o)=\mathbb{E}\left[R_t^{(\tau)}+\gamma^\tau\max_{o'}Q^*(S_{t+\tau},o')\mid S_t=s,O_t=o\right].
$$

Here, $0\leq\gamma<1$ discounts each primitive time step. The expectation includes both the terminal state and duration. For continuous physical time, an exponential discount such as $e^{-\beta\tau}$ can play the analogous role. This accounting is useful when decision intervals vary or when a skill spans many low-level interactions [2].

## Slide guide

| Slide | Focus | Learning objective |
|---|---|---|
| 1 | Standard MDP and decision epochs | Distinguish decision index from elapsed physical time |
| 2 | Blitz chess and decision duration | Motivate time-budget-aware decision-making |
| 3 | Autonomous driving and high-level skills | Explain accumulated reward and duration-dependent discounting |
| 4 | Synthesis | Relate variable-duration decisions to temporal abstraction |

## Modeling qualifications

The original slides are preserved as presented. Their motivating comparisons should be interpreted with the following qualifications:

- A standard MDP can incorporate clocks, time costs, and time-dependent rewards when its state is defined appropriately. SMDPs explicitly represent variable durations; they do not imply that MDPs cannot model time.
- An SMDP state must still contain enough information for the required Markov property. In blitz chess, remaining clock time can affect available decisions and timeout risk. A board-only state with an external time penalty is generally insufficient for exact clock-dependent planning unless additional assumptions or a sufficient time representation are specified.
- The factorization $p(s',\tau\mid s,a)=p(s'\mid s,a)p(\tau\mid s,a,s')$ is a conditional-probability factorization. It does not assume that next state and duration are independent.
- Temporal abstraction can reduce the number of high-level decisions, but improvements in exploration, generalization, or sample efficiency depend on the options, representation, and task. The slides do not establish universal performance or convergence guarantees.
- For $0<\gamma<1$, a shorter duration preserves more of an identical positive continuation value. Total option value also depends on accumulated rewards and the terminal state; faster execution alone does not guarantee a better option.

## References

[1] Sutton, R. S., and Barto, A. G. (2018). *Reinforcement Learning: An Introduction*, second edition. [MIT Press](https://mitpress.mit.edu/9780262039246/reinforcement-learning/).

[2] Sutton, R. S., Precup, D., and Singh, S. (1999). Between MDPs and semi-MDPs: A framework for temporal abstraction in reinforcement learning. *Artificial Intelligence*, 112(1–2), 181–211. [Publisher](https://www.sciencedirect.com/science/article/pii/S0004370299000521).

Additional credits shown in the original slides, including Waterloo CS885 and Bradtke and Duff (1994), are retained in the PDF.
