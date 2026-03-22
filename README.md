# LogInsight — Web Traffic Analysis Tool

[![GitHub Repo](https://img.shields.io/badge/GitHub-Repo-2E2E2E?logo=github&logoColor=white)](https://github.com/finnxiii/loginsight)
![IEUK 2025](https://img.shields.io/badge/IEUK%202025-Technology%20&%20Engineering-purple)

LogInsight is a Python-based command-line tool for analysing web server logs to detect suspicious traffic patterns, monitor API usage, and identify traffic spikes.

Developed as part of the IEUK 2025 programme, the project demonstrates practical application of log parsing, data aggregation, and heuristic-based anomaly detection for real-world system monitoring.

> [!NOTE]
> This repository contains a lightweight log analysis tool that parses structured log files, aggregates traffic data, and highlights potential anomalies such as bot activity and abnormal request patterns.

---

## Overview

LogInsight processes web server logs and extracts key metrics to help understand traffic behaviour:

- Total and API request volume  
- Per-IP and per-endpoint activity  
- Suspicious user agents (bots, crawlers, scripts)  
- Hourly traffic distribution  
- High-frequency or abnormal request patterns  

The tool is designed to work with structured logs and provide immediate, human-readable insights via the command line.

---

## System Architecture

1. **Parsing Layer**  
   Log entries are parsed using regular expressions and converted into structured records.

2. **Aggregation Layer**  
   Traffic data is aggregated using efficient Python data structures:
   - Requests per IP  
   - Requests per endpoint  
   - Hourly traffic counts  

3. **Detection Layer**  
   Heuristic rules are applied to identify suspicious behaviour:
   - Known bot patterns in user agents  
   - High-frequency API usage  

4. **Reporting Layer**  
   The system outputs summarised insights including:
   - Traffic statistics  
   - Top IPs and endpoints  
   - Suspicious activity  
   - Time-based traffic trends  

---

## Key Features

- Regex-based parsing of structured log data  
- Efficient aggregation using `Counter` and `defaultdict`  
- Heuristic detection of automated or suspicious traffic  
- Time-based analysis for identifying traffic spikes  
- Command-line interface for quick inspection  
- Docker support for reproducible execution  

---

## Tech Stack

### Software
- Python 3.8+  
- Standard libraries: `re`, `collections`, `datetime`  

### Infrastructure and Tools
- Docker (optional containerised execution)  
- Command-line interface  

---

## Design Considerations

- **Simplicity vs Flexibility:**  
  The tool prioritises a clear and lightweight implementation while supporting structured log formats.

- **Heuristic Detection:**  
  Bot detection is rule-based, trading completeness for interpretability and ease of extension.

- **Performance:**  
  Uses in-memory aggregation for fast analysis of moderate-sized log files.

Future improvement: Extend support for multiple log formats and enable streaming analysis for large-scale logs.

---

## Usage

Run the analyzer with a log file:

```bash
python analyze_logs.py sample-log.log
