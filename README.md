# DBT Fun

## Introduction

This exercise is designed to enable a team to demonstrate their knowledge of good software and data engineering practices. 

It should take around half a day to complete.

Please use the Python script to generate the required sample data instructions can be found in the README.md under data_generator.

### Instructions

The purpose of this exercise is to complete a small data pipeline that aggregates and transforms input data according to requirements driven by our engagement team. The details of this are given later in this document.

Please build out your solution and submit a PR once complete

You will be required to have an AWS account. 

You will also need a trial Snowflake account to complete the task.

The aim of this exercise is to write code that processes existing data sources so that it meets requirements.

As part of solving this, we are looking to understand:

* Your problem-solving approach.
* Your ability to turn your solution into working code and choose appropriate technology.

## Task 

    The task involves developing a data pipeline 
    using synthetic sample data.

    Our engagement team has reached out to your 
    data engineering team requesting we create a data
    mart to enable self service analytics.

    They have also requested a data contract to show how many times 
    each of our insureds purchases lines in a given period
    so that they can predict what coverage they will need next. 
    They will also need to see endorsements!

The input data sources are comprised of insureds (in CSV format), reinsurance treaties (CSV), speciality lines (CSV),
policies (in JSON Lines format) and claims (JSONL). Their details are presented below:

### Acceptance Criteria

A data contract showing how many times each of our insureds purchases our lines in a given period, so that we can predict 
the coverage they will need next.

Create a warehouse (facts and dimensions) that will support self service capabilities.

To arrive at this the following steps will need to be completed:

* Create a secure S3 bucket
* Upload data to bucket
* Ingest data from bucket to Snowflake
* Create models in DBT

The data contract should look like the below:

| insured_id | risk_score | industry | line_category | policy_count | total_base_premium | total_endorsement_premium | endorsement_premium_percentage | total_endorsements | modification_behavior | purchase_behavior |
|------------|------------|----------|---------------|--------------|-------------------|---------------------------|------------------------------|-------------------|---------------------|-------------------|
| IN1 | 7 | Technology | cyber | 3 | 45000.00 | 8500.00 | 18.9 | 5 | Moderate Modifier | Frequent Buyer |
| IN1 | 7 | Technology | professional_liability | 2 | 28000.00 | 2100.00 | 7.5 | 2 | Light Modifier | Occasional Buyer |
| IN2 | 4 | Healthcare | medical_malpractice | 1 | 65000.00 | 0.00 | 0.0 | 0 | No Modifications | Single Purchase |

### Further Implementation Details
The repo contains a starter project that includes the input data sources, a virtual environment with some dependencies you may find useful and some basic tests to ensure the environment is ready - but only for Python.

It is highly preferred to use Infrastructure-as-Code (Terraform) for completing the above tasks. 

Areas of automation and improvements can be highlighted in the code. 

The code and design should meet the above requirements, and should consider future extension or maintenance by different members of the team.
