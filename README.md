# AI-Assisted Performance Testing & Quality Engineering Dashboard

## Overview
A Python and Streamlit dashboard for comparing Apache JMeter test runs and generating Excel and PowerPoint performance reports. The project demonstrates a practical workflow for reviewing API performance-test results and presenting findings.

## Features
- Upload baseline and current-run JMeter CSV result files.
- Compare response times and transaction-level metrics.
- Review throughput and observed error rates.
- Visualize baseline-versus-current performance.
- Export Excel reports with charts and detailed result data.
- Export PowerPoint reports for sharing test summaries and findings.
- Review failed requests, quality-gate outcomes, and investigation notes.

## Technology Stack
- Python
- Streamlit
- Pandas and NumPy
- Matplotlib
- Apache JMeter
- OpenPyXL
- python-pptx

## Project Structure
```text
ai-performance-quality-dashboard/
├── ai_performance_quality_dashboard_all_updates_v5_ppt_chart_bullet_fixes.py
├── public_api_smoke_and_load_test.jmx
├── requirements.txt
├── README.md
└── sample_data/
    ├── baseline.csv
    └── current_run.csv
```

The filenames above are suggested names. Use the actual filenames you upload to your repository.

## Setup and Run Locally

### 1. Install Python
Install a compatible Python 3 version and ensure Python is available from Command Prompt.

### 2. Install dependencies
Open Command Prompt in the project folder and run:

```bash
python -m pip install -r requirements.txt
```

### 3. Start the dashboard
Run the following command, replacing the script name if your file has a different name:

```bash
python -m streamlit run ai_performance_quality_dashboard_all_updates_v5_ppt_chart_bullet_fixes.py
```

Open the local URL printed by Streamlit, typically `http://localhost:8501`.

## Using the Dashboard
1. Run the JMeter test plan or use the included sanitized sample CSV files.
2. Upload the baseline and current-run CSV files in the dashboard.
3. Review response-time, throughput, and error metrics.
4. Review transaction-level comparisons and investigation notes.
5. Download the generated Excel and PowerPoint reports.

## JMeter Test Plan
The sample JMeter plan exercises five GET transactions against JSONPlaceholder, a public practice API:
- Get Single Post
- Get Posts List
- Get Single User
- Get Comments for Post 1
- Get Single Album

Use modest request volumes and respect the service's terms. This test plan demonstrates the JMeter-to-reporting workflow; it does not establish the maximum capacity of the public API or represent a benchmark of your own application. For capacity, stress, or endurance testing, use an environment you own or are explicitly authorized to test.

## Interpreting Results
- **Response time:** the elapsed time recorded for a request. Transaction summaries commonly report averages across samples.
- **Throughput:** requests completed per unit of time. Verify whether a report shows overall-run throughput or transaction-level throughput.
- **Error rate:** the percentage of failed samples, according to the result file and dashboard's success/failure logic.
- **Baseline comparisons:** meaningful regression comparisons should use equivalent test conditions, including workload, ramp-up, loop count, environment, and test data.

Timestamp-derived test duration may be an estimate if the CSV does not contain the exact start and end times of the entire run. Treat estimated throughput accordingly.

## Data and Privacy
Only commit sample data that you are permitted to share. Remove personal information, credentials, tokens, internal URLs, customer data, and employer-confidential information before uploading files to a public repository.

## Known Limitations
- Results depend on the completeness and format of the JMeter CSV files.
- Estimated duration from sample timestamps may differ from JMeter's official test duration.
- Different workloads should not be presented as a controlled performance-regression comparison.
- This repository is a portfolio demonstration and should be validated in the target environment before production use.

## License
No license is specified yet. Add a license file if you want to define how others may use, modify, and distribute this project.
