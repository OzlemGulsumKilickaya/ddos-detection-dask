# DDoS Detection on CIC-DDoS2019 using Dask

This project implements a scalable pipeline for detecting Distributed Denial of Service (DDoS) attacks using the [CIC-DDoS2019 dataset](https://www.unb.ca/cic/datasets/ddos-2019.html). Leveraging **Dask**, it processes large-scale network traffic data efficiently in Python.

## 🚀 Key Features

- Scalable data handling with Dask DataFrame
- CIC-DDoS2019 attack type coverage (e.g., DrDoS_DNS)
- Missing value analysis and cleanup
- Ready-to-extend for ML model training and real-time streaming

## 📂 Dataset

- Source: [CIC-DDoS2019](https://www.unb.ca/cic/datasets/ddos-2019.html)
- Format: CSV files by attack type and date
- Example used:  
/kaggle/input/cic-ddos2019-30gb-full-dataset-csv-files/01-12/DrDoS_DNS.csv


## 🧰 Tech Stack

- Python 3.10+
- Dask
- Pandas (optionally)
- Jupyter Notebook

## ⚙️ Installation

Install dependencies using pip:

pip install dask pandas

📒 Usage
You can run the notebook step-by-step to:

Load large CSV data with type specification:

import dask.dataframe as dd
df = dd.read_csv("DrDoS_DNS.csv", dtype={"SimillarHTTP": "object"})
Check for missing values:

missing_values = df.isnull().sum().compute()
print(missing_values[missing_values > 0])
View a sample:

print(df.head())

📁 Folder Structure

ddos-detection-dask/

│

├── notebooks/

│   └── DDoS_Detection_Dask.ipynb     # Main notebook

├── data/                             # (Not included – download from CIC)

│

├── README.md

├── .gitignore

└── LICENSE


🙌 Acknowledgments

Canadian Institute for Cybersecurity for providing the dataset.
