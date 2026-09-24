# Hybrid RL-RBS Irrigation Control

This repository contains an anonymous code package for a hybrid irrigation-control approach that combines:

- Proximal Policy Optimization (PPO) for reinforcement-learning-based irrigation decisions.
- Rule-Based System (RBS) logic for interpretable irrigation scheduling and comparison.
- AquaCrop-OSPy simulations for crop-growth, water-use, and productivity evaluation.

## Hybrid Workflow

The hybrid PPO+RBS workflow is organized around three stages:

1. RBS scheduling
   - `RBS-1.py` implements a rule-based irrigation schedule using crop, soil, evapotranspiration, precipitation, and water-balance parameters.
   - `RBS-2.py` extends the rule-based logic with dynamic environmental information, including sensor and forecast-style inputs.

2. PPO learning
   - `RL-PPO.py` implements a PPO agent integrated with AquaCrop-OSPy.
   - The agent observes climate and crop-state information, selects irrigation depths, and receives rewards based on productivity, water use, water stress, and excessive irrigation penalties.

3. Productivity and water-use comparison
   - `CompareProductivity.py` compares irrigation strategies through AquaCrop simulations.
   - The comparison focuses on fresh yield, dry yield, potential yield, seasonal irrigation depth, and water-saving behavior.

## Main Files

- `RBS-1.py`: baseline rule-based irrigation scheduling.
- `RBS-2.py`: enhanced RBS scheduling with dynamic environmental conditions.
- `RL-PPO.py`: PPO-based reinforcement learning irrigation controller.
- `CompareProductivity.py`: simulation-based comparison between RBS and RL/PPO irrigation strategies.
- `irrigation_soil.py`: soil-moisture-oriented AquaCrop simulation support.

## Requirements

Install the main dependencies with:

```bash
pip install aquacrop gym numpy pandas torch matplotlib seaborn rule-engine openpyxl
```

