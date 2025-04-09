# Experimental Setup and Results

## 1. Environment Configuration

### System Specifications
(Table 1) Listing OS, CPU, RAM, installed software (AFL++, PyTorch, PPO settings).

### Target Binaries
OpenSSL, Uroboros SPEC CPU2006 benchmarks.

### Table 1: Experimental Environment

| Component       | Details                |
|-----------------|------------------------|
| OS              | Kali Linux (VM)        |
| Processor       | 4-core CPU             |
| RAM             | 8GB                    |
| Fuzzing Tool    | AFL++ (QEMU mode)      |
| RL Framework    | PyTorch                |
| Target Binaries | OpenSSL 1.1.1f, Uroboros SPEC CPU2006 |

## 2. Experimental Design

### 2.1 PPO Implementation Details
Architecture Diagram: Illustrating integration of AFL++ with PPO (Fig. 1).

Mathematical foundation of PPO (Equation 1).

Hyperparameter Tuning: Learning rate, batch size, clipping parameter.

### Figure 1: Black-Box Fuzzing Framework Architecture
(A well-labeled system architecture diagram with modules: Input Generator, Execution Engine, Feedback Analyzer, RL Module.)

## 3. Performance Evaluation..

### Metrics Used
- Code Coverage (%) – Explored paths in binaries.
- Crash Discovery Rate (Crashes/sec) – Identifying vulnerabilities.
- Execution Speed (Test cases/sec) – Processing efficiency.



Architecture Diagram – A labeled system architecture diagram.

- 1.Line Graph – Code coverage over time for AFL++ vs. AFL++ + PPO.

- 2.Bar Chart – Execution speed comparison.

- 3.Comparison Tables – Crash discovery rate and RL algorithm comparison.

 line graph for code coverage over time.

```
import matplotlib.pyplot as plt
import numpy as np

# Sample Data
time = np.arange(0, 10, 1)  # Time in hours
afl_coverage = np.array([10, 20, 30, 38, 45, 50, 55, 58, 60, 62])  # AFL++ coverage %
ppo_coverage = np.array([12, 25, 40, 50, 60, 68, 72, 75, 78, 80])  # AFL++ + PPO coverage %

# Create the plot
plt.figure(figsize=(8, 5))
plt.plot(time, afl_coverage, marker='o', linestyle='-', label="AFL++", color='blue')
plt.plot(time, ppo_coverage, marker='s', linestyle='--', label="AFL++ + PPO", color='red')

# Labels and Title
plt.xlabel("Time (Hours)")
plt.ylabel("Code Coverage (%)")
plt.title("Code Coverage Over Time")
plt.legend()
plt.grid(True)

# Save the figure
plt.savefig("/mnt/data/code_coverage.png")
plt.show()

```

Bar chart comparing execution speed for AFL++ vs. AFL++ + PPO.

```

# Sample Execution Speed Data (test cases per second)
methods = ["AFL++", "AFL++ + PPO"]
execution_speed = [150, 220]  # Number of test cases processed per second

# Create the bar chart
plt.figure(figsize=(6, 5))
plt.bar(methods, execution_speed, color=['blue', 'red'])

# Labels and Title
plt.ylabel("Execution Speed (Test Cases/sec)")
plt.title("Execution Speed Comparison")

# Save the figure
plt.savefig("/mnt/data/execution_speed.png")
plt.show()

```

comparison tables for crash discovery rate and RL algorithm performance. ​

```
import pandas as pd

# Crash Discovery Rate Table Data
crash_data = {
    "Metric": ["Unique Crashes Found", "Time to First Crash (min)", "Total Crashes Discovered"],
    "AFL++": [15, 45, 120],
    "AFL++ + PPO": [25, 30, 180]
}

crash_df = pd.DataFrame(crash_data)

# RL Algorithm Performance Table Data
rl_comparison_data = {
    "Algorithm": ["DQN", "TRPO", "A3C", "PPO"],
    "Stability": ["Medium", "High", "Medium", "High"],
    "Sample Efficiency": ["Low", "Medium", "Medium", "High"],
    "Ease of Implementation": ["High", "Low", "Medium", "High"],
    "Exploration Capability": ["Medium", "High", "Medium", "High"]
}

rl_df = pd.DataFrame(rl_comparison_data)

# Save tables as images
fig, ax = plt.subplots(1, 2, figsize=(12, 4))

# Crash Discovery Rate Table
ax[0].axis('tight')
ax[0].axis('off')
ax[0].table(cellText=crash_df.values, colLabels=crash_df.columns, cellLoc='center', loc='center')

# RL Algorithm Comparison Table
ax[1].axis('tight')
ax[1].axis('off')
ax[1].table(cellText=rl_df.values, colLabels=rl_df.columns, cellLoc='center', loc='center')

# Save the figure
plt.savefig("/mnt/data/comparison_tables.png")
plt.show()


```
# Sample Execution Speed Data (test cases per second)
methods = ["AFL++", "AFL++ + PPO"]
execution_speed = [150, 220]  # Number of test cases processed per second

# Create the bar chart
plt.figure(figsize=(6, 5))
plt.bar(methods, execution_speed, color=['blue', 'red'])

# Labels and Title
plt.ylabel("Execution Speed (Test Cases/sec)")
plt.title("Execution Speed Comparison")

# Save the figure
plt.savefig("/mnt/data/execution_speed.png")
plt.show()
```
comparison tables for crash discovery rate and RL algorithm performance. ​

### 3.1 Code Coverage Analysis
Graph (Fig. 2): Line graph showing code coverage over time for AFL++ vs. AFL++ + PPO.

### 3.2 Crash Discovery Rate
Comparison Table (Table 2) for different methods (AFL++, AFL++ + PPO, RL-enhanced fuzzing).

### Table 2: Crash Discovery Rate Comparison

| Method         | Unique Crashes Found | Time (hrs) |
|----------------|-----------------------|------------|
| AFL++          | X                     | Y          |
| AFL++ + PPO    | X+Δ                   | Y-Δ        |
| RL-enhanced    | X+2Δ                  | Y-2Δ       |

### 3.3 Execution Speed
Bar Chart (Fig. 3): Comparing execution speed for different configurations.

## 4. Comparative Analysis with Other RL Algorithms

### Comparison Table (Table 3): PPO vs. DQN vs. TRPO vs. A3C.

### Table 3: RL Algorithm Comparison in Fuzzing

| Algorithm | Code Coverage | Crash Rate | Convergence Time |
|-----------|----------------|------------|------------------|
| DQN       | Low            | Medium     | High             |
| TRPO      | Medium         | High       | High             |
| A3C       | Medium         | Medium     | Medium           |
| PPO       | High           | High       | Low              |

## 5. Discussion
Effectiveness of PPO in Fuzzing (graphical comparison).

Challenges: Test case redundancy, execution monitoring overhead.

## 6. Conclusion
Summary of results with recommendations for further improvements.
