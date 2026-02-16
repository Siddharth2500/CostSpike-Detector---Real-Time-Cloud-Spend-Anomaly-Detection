# 🚀 CostSpike-Detector - Real-Time Cloud Spend Anomaly Detection

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg?logo=python&logoColor=white)  
![Tool](https://img.shields.io/badge/Tool-Cost%20Anomaly%20Detector-FF5252.svg?logo=dollar-sign&logoColor=white)
![Features](https://img.shields.io/badge/Features-Real%20Time%20Detection-4CAF50.svg?logo=chart-line&logoColor=white)
![Reports](https://img.shields.io/badge/Reports-JSON-2196F3.svg?logo=json)  
![CI/CD](https://img.shields.io/badge/CI/CD-Ready-2088FF.svg?logo=githubactions)  
![Dependencies](https://img.shields.io/badge/Dependencies-None-green.svg?logo=python)

**CostSpike-Detector** is a **Python 3** tool designed for DevOps and FinOps teams to simulate and detect unexpected spikes in cloud-spend. It uses historical spend data, computes a baseline average, and flags new daily costs that exceed a configured threshold. The tool logs anomalies and writes a JSON report for consumption in pipelines or dashboards.

-----------

## 🛠 Tech & Languages

| Layer         | Tech / Format                | Purpose                                     |
|---------------|------------------------------|---------------------------------------------|
| Language      | **Python 3.10+**             | Main codebase                               |
| Core Logic    | JSON parsing + statistics + simulation | Compute averages, detect spikes        |
| Reports       | **JSON**                     | Output anomaly summary                       |
| Execution     | Script / Colab / Notebook    | Flexible runtime                             |
| Logging       | Console output + file write  | Quick feedback + persistent results          |

---

## 🌐 Architecture

Flow:  
1. Step 1 – Load `spend_history.json` containing daily cost data.  
2. Step 2 – For each new simulated day: generate a cost value, compare to historical average.  
3. Step 3 – If new cost > average × (1 + threshold%), mark as anomaly.  
4. Step 4 – Append to report’s `anomalies` list.  
5. Output `spend_anomaly_report.json` with timestamp, number of checked points and anomalies list.  
6. Use this report in CI/CD or dashboards for alerting or further analysis.

---

## ▶️ Run CostSpike-Detector

```bash
python cost_spike_detector.py --input data/spend_history.json --output data/spend_anomaly_report.json
