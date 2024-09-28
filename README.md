# AWS ScoutSuite Project 🚀

## Overview 📖
This project utilises **ScoutSuite**, an open-source security auditing tool, to assess the security posture of AWS accounts. The primary goal is to identify potential vulnerabilities across various AWS services, ensuring that best practices for security are being followed.

## Objective 🎯
The main objectives of this project are to:

| Objectives                                              |
|--------------------------------------------------------|
| Conduct a security audit of an AWS account using ScoutSuite. |
| Identify security vulnerabilities in AWS services, particularly focusing on S3 findings. |
| Generate a comprehensive report detailing the results of the audit. |

## Tools Used 🛠️
- **AWS**: Amazon Web Services account for deploying resources.
- **ScoutSuite**: Multi-cloud security auditing tool.
- **PuTTY**: SSH client for connecting to the EC2 instance.
- **Git Bash**: Command line interface for running Unix-like commands on Windows.

## Steps Taken 🗂️

### 1. Set Up AWS IAM Roles
In this step, IAM roles were configured to allow EC2 instances to interact with AWS services securely.

![AWS Roles Configuration](screenshots/AWS%20Roles%20Screenshot.PNG)


### 2. Launch EC2 Instance
An EC2 instance was launched with the **Amazon Linux 2023 AMI** to run ScoutSuite.

![PuTTY Terminal](screenshots/PuTTY%20Terminal%20Screenshot.PNG)

### 3. Install and Configure ScoutSuite
ScoutSuite was installed on the EC2 instance. The following command was used to perform the audit:

![scout command](screenshots/scout%20command%20screenshot.PNG)



### 4. Downloading the Report
After running the scan, the complete report folder was downloaded from the EC2 instance to the local machine.

![Downloading Report](screenshots/Downloading%20report%20folder%20screenshot.PNG)

### 5. Analysing Results
The results of the audit were primarily focused on S3 services, which indicated **18 rules** that require attention. Below is a detailed analysis of the findings related to S3:

#### S3 Findings Analysis
- **Total Rules Found**: 18 rules related to S3 configuration issues.
- **Common Issues Detected**:
  - **Publicly Accessible Buckets**: Some S3 buckets may be publicly accessible, posing a risk of unauthorised data exposure.
  - **Unrestricted Bucket Policies**: Certain buckets have policies that allow public access, increasing the risk of data leaks.

#### Recommendations 💡
To address the S3 findings, I recommend the following actions:

| Recommendations                                          |
|---------------------------------------------------------|
| **Review Bucket Policies**: Tighten policies to ensure only authorised users can access sensitive data. |
| **Implement Access Logging**: Enable server access logging for all S3 buckets to monitor unauthorised access attempts. |
| **Use AWS Config**: Continuously monitor configurations to ensure compliance with security policies. |
| **Regular Audits**: Conduct regular audits with tools like ScoutSuite to identify and remediate vulnerabilities promptly. |

### 6. ScoutSuite Results Overview
The dashboard displayed the results of the AWS services audit. The following is a summary of the findings:

- **S3**: 18 rules identified.
- Other services showed no findings, indicating either they are not in use or properly configured.

![Overall Results](screenshots/S3%20results%20screenshot.PNG)

## Conclusion 🏁
This project demonstrates the effective use of ScoutSuite in auditing AWS environments. While the S3 bucket had findings, the other services were found to be secure (or not present). The recommendations provided aim to enhance the security posture of the AWS account.

## Future Improvements 🚀
- Expand the audit to include additional AWS services by creating and configuring those services.
- Regularly rerun the audit to track improvements and changes in security posture.
