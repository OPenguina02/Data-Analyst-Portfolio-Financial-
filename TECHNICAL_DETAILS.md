# Technical Implementation

## Technology Stack

**Development Tools**

* Visual Studio Code
* Python 3.x
* Power BI Desktop
* Git & GitHub

**Python Libraries**

```python
pandas
numpy
random
datetime
```

## Project Architecture

The project follows an end-to-end analytics workflow:

```text
Data Generation
→ Data Modeling
→ KPI Development
→ Dashboard Visualization
```

Dataset generation is fully automated using Python scripts and produces a relational dataset that can be imported directly into Power BI.

## Dataset Structure

### Fact Tables

* Loan
* Payment

### Dimension Tables

* Customer
* Individual Customer
* Corporate Customer
* Product
* Branch
* Staff
* Policy
* Calendar

### Supporting Tables

* Policy Product
* Policy Branch
* Staff Branch History

## Generation Flow

```text
Branch
 ├─ Staff
 │   └─ Staff Branch History
 │
 ├─ Policy
 │   ├─ Policy Product
 │   └─ Policy Branch
 │
Customer
 ├─ Individual Customer
 └─ Corporate Customer

Product

Loan
 └─ Payment
```

## Business Logic

### Loan Status

* ACTIVE
* CLOSED
* DEFAULT

### Revenue Model

```text
Revenue
= Interest Revenue
+ Penalty Revenue
```

### Penalty Logic

```text
Penalty Amount
= Original Loan Amount
× Penalty Rate
× Overdue Months
```

Penalty rates are defined at product level.

## Power BI Development

### Core KPIs

* Total Loan Count
* Total Loan Amount
* Outstanding Amount
* Revenue
* Default Rate
* Default Outstanding Rate

### Analysis Areas

* Portfolio Performance
* Branch Performance
* Product Performance
* Risk Monitoring

## Reproducibility

Install dependencies:

```bash
pip install pandas numpy
```

Run the Python generation scripts, then import the generated CSV files into Power BI Desktop.

No external APIs, databases or proprietary datasets are required.

## Disclaimer

All data is synthetically generated for portfolio purposes and does not represent real customers, employees, branches, transactions or financial performance.
