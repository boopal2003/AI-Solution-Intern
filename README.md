# AI Solution Intern Case Study

## **Overview**
This project is a case study aimed at automating investment report generation for a mid-sized asset management firm using Generative AI. The solution focuses on creating tailored, compliant, and insightful reports based on portfolio performance data and client-specific requirements.

## **Key Objectives**
- Automate investment report generation with comprehensive portfolio performance analysis.
- Tailor reports to align with diverse client profiles.
- Ensure compliance with financial reporting standards by including necessary disclosures.

---

## **Features**

### **1. Automated Investment Report Generation**
- Generates customized investment summaries using portfolio data such as:
  - Year-to-Date (YTD) Returns
  - Asset Allocation (Equities, Bonds, Cash)
  - Risk Metrics (Sharpe Ratio, Standard Deviation)
- Compares portfolio performance against benchmarks like:
  - S&P 500
  - Bloomberg US Aggregate Bond Index

### **2. Tailored Content**
- Customizes reports based on client profiles, including:
  - Investment Goals (e.g., Long-term growth, Capital Preservation)
  - Risk Tolerance (e.g., Moderate, Low, High)

### **3. Compliance Assurance**
- Includes mandatory disclaimers such as:
  - "Past performance is not indicative of future results."
  - "This report is for informational purposes only."
- Adheres to financial reporting standards.

---

## **How It Works**
### **Prompt**
The following prompt structure is designed to generate comprehensive investment report summaries:
```
Input Data Structure:
1. Client Profile:
   - Name: [Client Name]
   - Investment Goals: [Investment Objectives]
   - Risk Tolerance: [Risk Profile]

2. Portfolio Performance Metrics:
   - Year-to-Date Returns: [Value]
   - Annualized Returns: [Value]
   - Asset Allocation:
     - Equities: [Percentage]
     - Bonds: [Percentage]
     - Cash: [Percentage]
   - Risk Metrics:
     - Sharpe Ratio: [Value]
     - Standard Deviation: [Value]

3. Benchmarks:
   - Equities Benchmark: [Benchmark Name and Return Value]
   - Bonds Benchmark: [Benchmark Name and Return Value]

Required Output Format:
- Header: Include the client’s name and report date.
- Section 1: Portfolio Performance Summary.
  - Compare portfolio metrics with benchmarks.
  - Highlight alignment with the client’s goals and risk tolerance.
- Section 2: Actionable Insights.
  - Suggest portfolio adjustments to improve performance or manage risks.
- Section 3: Compliance Disclosures.
  - Standard financial disclaimers:
    - "Past performance is not indicative of future results."
    - "This report is for informational purposes only and does not constitute financial advice.
```

### **Test Samples**
Three distinct test samples have been developed to demonstrate different output scenarios. The data is structured in JSON format as follows:
#### **Sample - 1**
This sample will produce "Portfolio is currently underperforming the S&P 500 benchmark. Review individual holdings for optimization opportunities." as a output.
```json
{
    "client_profile": {
        "name": "John Doe",
        "investment_goals": "Long-term growth",
        "risk_tolerance": "Moderate"
    },
    "portfolio_data": {
        "year_to_date_returns": 8.5,
        "annualized_returns": 7.2,
        "asset_allocation": {
            "equities": 60,
            "bonds": 30,
            "cash": 10
        },
        "risk_metrics": {
            "sharpe_ratio": 1.5,
            "standard_deviation": 12.3
        }
    },
    "benchmarks": {
        "equities": {
            "S&P 500": 9.0
        },
        "bonds": {
            "Bloomberg US Aggregate Bond Index": 2.5
        }
    }
}
```
#### **Sample - 2**
this sample will produce "Consider reducing equity exposure to better align with your moderate risk tolerance." as an output
```
{
  "client_profile": {
    "name": "Sarah Johnson",
    "investment_goals": "Long-term growth",
    "risk_tolerance": "Moderate"
  },
  "portfolio_data": {
    "year_to_date_returns": 11.2,
    "annualized_returns": 9.8,
    "asset_allocation": {
      "equities": 75,    
      "bonds": 20,
      "cash": 5
    },
    "risk_metrics": {
      "sharpe_ratio": 1.4,
      "standard_deviation": 14.5
    }
  },
  "benchmarks": {
    "equities": {
      "S&P 500": 10.5
    },
    "bonds": {
      "Bloomberg US Aggregate Bond Index": 3.0
    }
  }
}
```
#### **Sample - 3**
This sample will produce "High cash position may be dragging on returns. Consider deploying capital into investment opportunities" as an output.
```
{
  "client_profile": {
    "name": "Michael Brown",
    "investment_goals": "Balanced growth",
    "risk_tolerance": "Moderate"
  },
  "portfolio_data": {
    "year_to_date_returns": 5.2,
    "annualized_returns": 4.8,
    "asset_allocation": {
      "equities": 45,
      "bonds": 35,
      "cash": 20
    },
    "risk_metrics": {
      "sharpe_ratio": 1.2,
      "standard_deviation": 10.1
    }
  },
  "benchmarks": {
    "equities": {
      "S&P 500": 9.5
    },
    "bonds": {
      "Bloomberg US Aggregate Bond Index": 2.8
    }
  }
}
```
### **Outcomes**
Below is a sample output generated by the report summary generator based on client investment data:

![image](https://github.com/user-attachments/assets/dbf6b38d-49e2-4eb1-abf9-fadb01006835)

---
## **Code Implementation**
The project includes two different implementations of the investment report generator:

### **1. Direct JSON Input Version**
the first implementation accepts a JSON-formatted client data structure and generates an immediate report. This version is ideal for batch processing, API integration, or when working with existing client data systems. It can process multiple client portfolios efficiently and is suitable for integration with other financial systems.

### **2. Interactive Input Version**
The second implementation provides an interactive command-line interface where users can input client data step by step. This version guides users through the data entry process with clear prompts and validation, making it perfect for testing, demonstration purposes, or when manual data entry is needed. It's particularly useful for financial advisors who want to generate quick reports during client meetings.

Both versions use the same core report generation logic and produce identical output formats, differing only in how they collect input data. Users can choose the implementation that best suits their needs based on their use case and integration requirements.

---

## **Project Structure**

### **Files and Directories**
- **`code/`**: Contains the Python implementation.
  - `case_study.ipynb`: Jupyter Notebook with the full implementation.
- **`outputs/`**: Includes sample generated reports for test cases.
- **`README.md`**: This file, providing an overview of the project.

### **Implementation Highlights**
- **Prompt Engineering**: Designed to ensure tailored and compliant outputs.
- **Test Cases**: Three scenarios tested:
  1. Moderate Risk Investor
  2. Conservative Investor
  3. Aggressive Investor
- **Debugging**: Focused on input validation, prompt refinement, and output accuracy.

---

## **Proposed Improvements**
- **Automation**: Automate data ingestion from financial APIs.
- **Real-Time Feedback**: Implement dynamic feedback loops to refine prompts.
- **Compliance Framework**: Add automated checks for regulatory compliance.

---

## **Acknowledgments**
This project was developed as part of the AI Solution Intern Case Study. 

---

## **Contact**
For any queries or feedback, please contact Boopalamani J at boopalamani2003@gmail.com.
