# Gas Turbine Risk Modeling: ML and Feature Engineering for Failure Prediction (NASA C-MAPSS Dataset)

## *A pipeline for estimating engine failure risk using sensor data (application mirrors LM6000 gas turbine)*

**Highlights**
- Visualizations: Graphs and information of key data for quick comprehension
- Feature engineering: Lag/rolling features for degradation patterns
- Multiple models: Linear Regression, Random Forest, XGBoost

## Table of Contents
1. [Dataset](#dataset)
2. [Methodology](#methodology)
3. [Results](#results)
4. [Installation](#installation)
5. [Acknowledgments](#acknowledgments)

## Dataset
**NASA C-MAPSS FD001**: [Train](/train_FD001.txt), [Test](/test_FD001.txt), [RUL](/RUL_FD001.txt)
- 100 training engine units and 100 test engine units
- 21 sensors
- 3 operational settings

```python
# Sample data loading
train = pd.read_csv("data/train_FD001.txt", sep = " ", header = None)
```
## Sensor Degradation Plot Example (Sensor 2)
![Sensor Degradation Plot](/sensor_2_visualization.png)

## Methodology
### Feature Engineering
1. Lag Features: sensor "X"_lag_1 (value of previous cycle, where "X" denotes sensor number)
2. Rolling Features: 10-cycle moving mean/standard deviation
3. Noise Reduction: Dropped weakly correlated sensors (1, 5, 10, 16, 18, 19)

### Models
| Model            | NASA Score | Training Time (s) |  
|------------------|------------|-------------------|  
| Linear Regression| 15.60      | 0.01              |  
| Random Forest    | 13.68      | 0.13              |  
| **XGBoost**      | **10.60**  | 0.02              |

*Benchmarked on AMD Ryzen 7 5800H (16 threads), 16GB RAM*

## Results
### Top Predictive Features (for XGBoost model)
1. sensor 15_r_mean_10\* (sensor 15 = Bypass ratio): Indicates fan efficieny loss. Raises the overall temparature of the engine.
2. sensor 21_r_mean_10\* (sensor 21 = Low Pressure Turbine Coolant Bleed): Indicates clogged coolant bleeding paths. As a result, exhaust temperatures rise.
3. sensor 20_r_mean_10\* (sensor 20 = High Pressure Turbine Coolant Bleed): Indicates clogged coolant bleeding paths. As a result, High Pressure Compressor outlet temperatures rise.

**\*r_mean_10 denotes a rolling mean with a window of 10.**

## Installation
### Prerequisites:
- Python 3.8+ installed
- Jupyter Notebook or JupyterLab installed
- Required libraries: install with ```pip install pandas numpy scikit-learn xgboost matplotlib seaborn```

### Files Needed
Make sure the following files are in the **same directory** as the notebook:
- `Machine Learning for Engine Failure Prediction using C-MAPSS.ipynb`
- `train_FD001.txt`
- `test_FD001.txt`
- `RUL_FD001.txt`

### Run Instructions
1. Open terminal or Anaconda Prompt.
2. Navigate to folder containing the project.
3. Launch Jupyter Notebook by entering the following command:

   ```bash
   jupyter notebook
4. In the browser window that opens, click on .ipynb file ()
5. Run notebook cells in order (Shift+Enter)

## Acknowledgments
Dataset: [NASA CMAPSS Jet Engine Simulated Data](https://data.nasa.gov/dataset/cmapss-jet-engine-simulated-data)
