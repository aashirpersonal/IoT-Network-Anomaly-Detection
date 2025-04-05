# Anomaly Detection in IoT Network Traffic

## Overview
This project explores the application of unsupervised learning techniques for anomaly detection in an IoT network traffic dataset. The goal is to identify unusual or suspicious patterns in network traffic that could potentially indicate security threats or network anomalies. By implementing multiple anomaly detection algorithms, the project provides a comprehensive comparison of different approaches for detecting security incidents in IoT networks.

## Dataset Information
- **Source**: Kaggle dataset "Intrusion in IoT" (https://www.kaggle.com/datasets/ymirsky/network-tor-traffic)
- **Size**: 1,048,575 records with 47 features
- **Content**: Network traffic features including flow duration, header length, protocol type, packet rates, flag information, and protocol-specific indicators
- **Labels**: Various attack types (DDoS, DoS, reconnaissance, etc.) and benign traffic

## EDA Summary
- The dataset contains a diverse range of network traffic anomalies, with DDoS and DoS attacks being the most prevalent
- No missing values were found in the dataset
- Several features showed high correlation, indicating redundancy in the feature space
- The distribution of attack types is imbalanced, with some attack categories having significantly more samples than others
- Protocol features (TCP, UDP, ICMP) and flag-related features (SYN, FIN, RST) provide valuable information for anomaly detection

## Models Used
1. **Isolation Forest**
   - An ensemble-based anomaly detection algorithm
   - Tested with various contamination rates (0.05, 0.1, 0.15, 0.2)
   
2. **Local Outlier Factor (LOF)**
   - A density-based algorithm that identifies local deviations in data
   
3. **One-Class SVM**
   - A support vector machine approach for novelty detection

## Evaluation Metrics
- **Precision**: Proportion of detected anomalies that are true anomalies
- **Recall**: Proportion of actual anomalies that were detected
- **F1-score**: Harmonic mean of precision and recall

## Results
- **Isolation Forest** achieved the best balance of performance metrics across different contamination rates
  - Higher contamination rates improved both precision and recall
  - Best F1-score of 0.30 achieved with contamination rate of 0.2
  - Precision of up to 0.89 indicates high confidence in detected anomalies
  
- The models generally showed high precision but lower recall, suggesting they are good at correctly identifying anomalies but miss some of the anomalous instances

## How to Run
1. Clone this repository
2. Download the "Intrusion in IoT" dataset from Kaggle: https://www.kaggle.com/datasets/ymirsky/network-tor-traffic
3. Place the "cleaned_iot.csv" file in the appropriate input directory
4. Run the Jupyter notebook "anomaly-detection-in-iot-network-traffic.ipynb"

## Dependencies
- Python 3.x
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- jupyter

```python
# Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

## Credits
This project is based on the "Intrusion in IoT" dataset available on Kaggle.

## License
MIT License

Copyright (c) 2024

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE. 