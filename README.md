🧬 ModelN-Inspired Cloud ETL Pipeline

A deployable, interview-ready data engineering project simulating a pharmaceutical pricing workflow — inspired by Bayer’s use of Model N, Snowflake, and AWS Glue. Built to demonstrate key cloud engineering skills across AWS, Snowflake, PySpark, Lambda, Step Functions, Terraform, and CI/CD.

⸻

🎯 Purpose

This project simulates a real-world ETL pipeline for pharmaceutical rebate compliance using:
	•	AWS Glue (PySpark) for data validation
	•	Snowflake for clean warehousing
	•	Lambda for event-based alerts
	•	Step Functions for orchestration
	•	Terraform for infrastructure as code
	•	GitHub Actions for CI/CD

✅ Built to align with Bayer’s Cloud Engineer role.

⸻

🗂 Project Structure

pharma-revenue-x/
├── glue/
│   └── modeln_etl_job.py          # PySpark ETL validation logic
├── lambda/
│   └── alert_lambda.py           # Sends alerts if rebate violations detected
├── data/
│   └── modeln_sample.json        # Simulated Model N input
├── terraform/
│   ├── main.tf
│   ├── glue.tf
│   ├── lambda.tf
│   ├── snowflake.tf
│   └── iam.tf
├── .github/
│   └── workflows/
│       └── deploy.yml            # GitHub Actions CI/CD
├── architecture.drawio           # Architecture Diagram
└── README.md


⸻

⚙️ Flow Overview

graph TD
  A[S3 Raw JSON] --> B[Glue PySpark Job]
  B --> C[Validate rebate rules]
  C -->|valid| D[Snowflake Table]
  C -->|violations| E[S3 Alerts Bucket]
  E --> F[Lambda Function]
  F --> G[SNS Alert or Email]


⸻

📥 Sample Input (modeln_sample.json)

[
  {
    "transaction_id": "T123",
    "customer_id": "C001",
    "sku": "SKU001",
    "unit_price": 100.00,
    "rebate_amount": 20.00,
    "transaction_date": "2025-07-20"
  }
]


⸻

🔧 Tech Stack
	•	AWS Glue – PySpark-based data validation
	•	Snowflake – Cloud warehouse, optimized tables
	•	AWS Lambda – Trigger alerts
	•	AWS Step Functions – Orchestrates Glue + Lambda
	•	Terraform – Infrastructure as Code
	•	GitHub Actions – CI/CD for provisioning + updates
	•	IAM + S3 + KMS – Security best practices

⸻

✅ What It Demonstrates

Capability	Demo Element
Serverless ETL	Glue Job with PySpark
Data Quality Enforcement	Rebate rule validation
Lakehouse Pipeline	S3 → Snowflake via Glue
Event-driven Design	Lambda triggers on violations
Workflow Orchestration	Step Functions
CI/CD Automation	GitHub Actions + Terraform
Security Best Practices	IAM roles + KMS (if added)


⸻

📈 Use Cases
	•	Interview demo for Cloud/Data Engineer roles
	•	Internal PoC for pharma pricing workflows
	•	Extendable pipeline for AuroGenix Cloud Agents

⸻

📌 Next Steps
	•	Deploy Terraform infra to AWS
	•	Run ETL job via Step Function
	•	Visualize Snowflake output with Power BI / Tableau / Flask UI
	•	Extend: add stored procedures, Snowflake alerts

⸻

🧠 Author

Built by Salman Shaik for Bayer Cloud Engineer interview readiness and future AuroGenix infra foundations.

⸻

🛡 Disclaimer

This is a simulated project for educational and professional demonstration purposes only. No proprietary data or logic from Bayer or Model N is used.