# Reinforcement Learning — Academic Coursework

**Hamed Batani · Fall 2026**

This repository documents my coursework in Reinforcement Learning through mathematical derivations, computational experiments, and a classroom presentation. It brings together my study of exploration and reward estimation in multi-armed bandits with temporal abstraction in semi-Markov decision processes (SMDPs).

Reinforcement learning studies how an agent improves its decisions through interaction with an uncertain environment. Unlike supervised prediction, an agent's choices determine the experience it collects. Understanding the relationship between exploration, estimation, reward, and time is therefore central to evaluating learning algorithms.

## Repository contents

| Component | Subject | Materials |
|---|---|---|
| [Class presentation](presentations/semi-markov-decision-processes/) | Semi-Markov decision processes, action duration, and temporal abstraction | Four-slide presentation prepared and presented by me in class on **24 October 2026**, with an academic overview and explanatory notes |
| [Homework 1](homework/hw-01/) | Introduction and multi-armed bandits | Course question sheet, my theoretical solutions in PDF and LaTeX, simulation notebook with saved outputs, and 18 result figures |

## Academic focus

The homework examines how an agent balances exploration with exploitation, how sample-average and constant-step-size estimates respond to stationary and changing rewards, and how uncertainty bonuses and policy-gradient updates influence learning. The presentation extends the discussion from individual action choices to actions that persist for variable durations. Together, these materials connect foundational learning rules with the representation of decisions at multiple time scales.

## Reading and running the work

Start with the presentation guide for conceptual context or the homework guide for the question-to-file mapping. GitHub can display the PDFs, figures, and notebook's saved outputs directly. Instructions for running the simulation are provided in [the simulation guide](homework/hw-01/simulation/).

The original PDFs, LaTeX source, notebook, and figures are preserved unchanged. The saved experiments are archived coursework results; publication of this repository does not constitute a fresh execution or independent validation of every result. See [ARCHIVE_NOTES.md](ARCHIVE_NOTES.md) for the file review and reproduction limits.

## Attribution and references

The presentation and submitted solutions are my coursework. The assignment questions are course-provided materials and are identified separately. Foundational ideas and algorithms are credited to the literature in [REFERENCES.md](REFERENCES.md). The presentation's Waterloo CS885 inspiration credit is retained; it does not imply enrollment in or affiliation with Waterloo. No blanket license is applied to third-party course materials.
