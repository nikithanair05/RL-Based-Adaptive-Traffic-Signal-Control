# 🚦 RL-Based Adaptive Traffic Signal Control

### Intelligent Traffic Management Using Reinforcement Learning and SUMO

An AI-powered adaptive traffic signal control system that uses Reinforcement Learning (RL) to optimize traffic flow at signalized intersections. The project implements and compares Q-Learning, Deep Q-Network (DQN), and Proximal Policy Optimization (PPO) against traditional traffic signal controllers using the SUMO microscopic traffic simulator.

## 📌 Project Overview

Traditional traffic signal systems rely on fixed-time schedules that cannot adapt to changing traffic conditions.

This project introduces a Reinforcement Learning-based approach where intelligent agents observe traffic conditions, select optimal signal phases, and improve their decisions through continuous interaction with the simulated environment.

The four-way intersection is formulated as a Markov Decision Process (MDP).

- **State:** Current signal phase, lane-level vehicle density and queue length.
- **Action:** Selection of the next green signal phase.
- **Reward:** Reduction in total vehicle waiting time.

## 🎯 Objectives

- Develop a four-way traffic intersection using SUMO.
- Implement Q-Learning, DQN and PPO algorithms.
- Compare RL agents with traditional traffic controllers.
- Evaluate performance under different traffic demand conditions.
- Analyze robustness against noisy sensor readings.
- Reduce vehicle waiting time, congestion and CO₂ emissions.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming |
| SUMO | Traffic simulation |
| TraCI | SUMO communication |
| Gymnasium | RL environment |
| Stable-Baselines3 | DQN and PPO |
| PyTorch | Deep learning |
| NumPy | Numerical computations |
| Matplotlib | Visualization |

## 🧠 Algorithms Implemented

### 1. Q-Learning
A tabular reinforcement learning algorithm that learns optimal traffic signal decisions using state-action values and an epsilon-greedy strategy.

### 2. Deep Q-Network (DQN)
Uses a neural network to approximate Q-values and select appropriate traffic signal actions.

### 3. Proximal Policy Optimization (PPO)
A policy-gradient reinforcement learning algorithm that learns optimized signal control policies through stable policy updates.

## 🚥 Baseline Controllers

The RL agents are compared against three conventional traffic control methods:

- **Fixed-Time:** Uses predefined signal durations.
- **Actuated:** Uses vehicle detection to extend or terminate green phases.
- **Max-Pressure:** Selects phases based on traffic pressure between incoming and outgoing lanes.

## 🏙️ Simulation Environment

The simulation uses a four-way isolated intersection developed in SUMO.

| Parameter | Description |
|---|---|
| Intersection | Four-way intersection |
| Approach arms | 4 |
| Lanes per approach | 3 |
| Total incoming lanes | 12 |
| Road length | 300 metres |
| Vehicle type | Passenger cars |
| Decision interval | 5 seconds |
| Episode duration | 3600 seconds |
| Minimum green time | 10 seconds |
| Yellow interval | 3 seconds |

### Traffic Demand Profiles

Four traffic demand conditions are considered:

1. Low Demand – 250 vehicles/hour per approach.
2. Medium Demand – 500 vehicles/hour per approach.
3. High Demand – 750 vehicles/hour per approach.
4. Time-Varying Demand – Simulates changing traffic intensity and rush-hour conditions.

## 📊 Experimental Results

### Average Waiting Time Comparison

| Traffic Demand | Fixed-Time | Actuated | Max-Pressure | Q-Learning | DQN | PPO |
|---|---:|---:|---:|---:|---:|---:|
| Low | 22.6 | 11.8 | 12.6 | 14.6 | 14.2 | **11.6** |
| Medium | 23.9 | 17.9 | 13.6 | 14.5 | 15.9 | **12.9** |
| High | 34.0 | 26.9 | 17.8 | 19.9 | 22.0 | **17.3** |
| Varying | 25.9 | 20.6 | 15.2 | 16.5 | 17.7 | **14.4** |

*All values represent average waiting time in seconds.*

### Key Findings

- PPO achieved the lowest average waiting time across all four demand conditions.
- Reduced waiting time by approximately **44–49% compared with Fixed-Time control**.
- PPO performed comparably to or slightly better than Max-Pressure control.
- Q-Learning and DQN also outperformed Fixed-Time and Actuated control.
- At high demand, PPO reduced CO₂ emissions to 389.6 kg compared with 473.1 kg for Fixed-Time control.

### Robustness to Sensor Noise

| Algorithm | Increase in Waiting Time |
|---|---:|
| Q-Learning | +10% |
| DQN | +23% |
| PPO | **+3%** |

PPO demonstrated better robustness against noisy sensor readings.

## 📈 Evaluation Metrics

The system is evaluated using:

- Average Vehicle Waiting Time
- Average Travel Time
- Average Queue Length
- Vehicle Throughput
- Total CO₂ Emissions
- Robustness to Sensor Noise

## ⚙️ Installation and Setup

### Prerequisites

- Python 3.9 or above
- SUMO Traffic Simulator
- Git
- pip package manager

### 1. Clone the Repository

```bash
git clone https://github.com/nikithanair05/RL-Based-Adaptive-Traffic-Signal-Control.git
```

### 2. Navigate to the Project Directory

```bash
cd RL-Based-Adaptive-Traffic-Signal-Control
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install numpy pandas matplotlib gymnasium stable-baselines3 torch
```

### 5. Install SUMO

Download SUMO from:

https://sumo.dlr.de/docs/Installing/index.html

Configure the `SUMO_HOME` environment variable and ensure SUMO and its tools are accessible from Python.

## ▶️ Running the Project

1. Install SUMO and the required Python dependencies.
2. Configure the SUMO simulation environment.
3. Prepare the traffic demand and network configuration files.
4. Initialize the Gymnasium-based traffic environment.
5. Train the selected reinforcement learning agent.
6. Evaluate the trained agent against baseline controllers.
7. Analyze the performance metrics and visualization results.

*Note: Refer to the actual Python scripts and configuration filenames in the repository for execution commands.*

## 🔮 Future Enhancements

- Extend the system to multiple interconnected intersections.
- Implement coordinated traffic signal control.
- Integrate real-world traffic datasets.
- Explore advanced reward functions.
- Reduce excessive signal phase switching.
- Improve generalization under changing traffic conditions.
- Validate the system using real-time traffic sensor data.

## 👩‍💻 Project Contributors

**Honours Project – RL-Based Adaptive Traffic Signal Control**

- Aleena James
- Angela Maria Abhraham
- Nikitha Nair
- Nimisha S Shine

**Project Guide:** Ms. Neenu R

## 📚 References

1. Lopez et al. (2018). Microscopic Traffic Simulation using SUMO.
2. Varaiya, P. (2013). Max Pressure Control of a Network of Signalized Intersections.
3. Mnih et al. (2015). Human-Level Control Through Deep Reinforcement Learning.
4. Schulman et al. (2017). Proximal Policy Optimization Algorithms.
5. Raffin et al. (2021). Stable-Baselines3: Reliable Reinforcement Learning Implementations.
6. Watkins and Dayan (1992). Q-Learning.
7. Sutton and Barto (2018). Reinforcement Learning: An Introduction.

## ⭐ Conclusion

This project demonstrates the potential of Reinforcement Learning in developing intelligent and adaptive traffic signal control systems. Experimental results show that PPO can significantly reduce vehicle waiting time, improve traffic flow and reduce CO₂ emissions compared with conventional fixed-time traffic control.

**Building Smarter Intersections Through Artificial Intelligence and Reinforcement Learning.** 🚦

Single 4-way intersection (3 lanes/approach, protected left turns), 4 demand profiles
(low 250, medium 500, high 750 veh/h/approach, time-varying), 3 RL agents vs 3 baselines.

| file | purpose |
|---|---|
| src/make_network.py | builds the intersection with netconvert |
| src/make_routes.py  | seeded Poisson demand (low/medium/high/varying) |
| src/env.py          | the MDP: state, action, reward, KPIs (Gymnasium env over SUMO/TraCI) |
| src/controllers.py  | baselines: fixed-time, actuated, max-pressure |
| src/agents.py       | tabular Q-learning + DQN/PPO wrappers |
| src/train.py        | training (Q-learning, DQN, PPO) + ablation flags |
| src/evaluate.py     | fair evaluation on unseen seeds -> CSV |
| src/plot_results.py | figures |
| src/demo.py         | live demo (--gui shows SUMO window) |

Note: "Retrying in 1 seconds" printed at start of every episode is TraCI waiting for SUMO to open its socket. It is normal.
