# Gas Turbine Risk Modeling: ML and Feature Engineering for Failure Prediction (NASA C-MAPSS Dataset)

## *A pipeline for estimating engine failure risk using sensor data (applications mirror LM6000 gas turbine)*

**Highlights**
- Visualizations: Graphs and information of key data for quick comprehension
- Feature engineering: Lag/rolling features for degradation patterns
- Multiple models: Linear Regression, Random Forest, XGBoost

## Table of Contents
1. [Dataset](#dataset)
2. [Methodology](#methodology)
3. [Results](#results)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Future Work](#future-work)
7. [Acknowledgments](#acknowledgments)

## Dataset
**NASA C-MAPSS FD001**: #ADD LINK HERE
- 100 training engine units and 100 test engine units
- 21 sensors
- 3 operational settings

```python
# Sample data loading
train = pd.read_csv("data/train_FD001.txt", sep = " ", header = None)
```
Sensor Degradation Plot Example (Sensor 2): ![Sensor Degradation Plot](/sensor_2_visualization.png)
