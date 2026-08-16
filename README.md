# CST8919 Assignment 2：Cloud Service Alternatives Report

Name: Bosi Chen  
Student Number: 041040774  
Course: CST8919 — DevOps - Security and Compliance, Spring/Summer 2026

---

## Introduction

This report compares selected Microsoft Azure security, monitoring, identity, governance, and threat detection services with their closest equivalents in Amazon Web Services (AWS) and Google Cloud Platform (GCP).

The comparison focuses on five cloud services covered in CST8919:

* Microsoft Entra ID
* Azure Monitor and Log Analytics
* Azure Policy
* Microsoft Defender for Cloud
* Microsoft Sentinel

For each service, the report compares its general purpose, core features, security and compliance capabilities, pricing model, and integration with DevSecOps practices.

## Quick Comparison

| Core Feature                       | Azure                         | AWS                           | GCP                              |
| ---------------------------------- | ----------------------------- | ----------------------------- | -------------------------------- |
| Identity and access management     | Microsoft Entra ID (Azure AD) | AWS IAM + IAM Identity Center | Cloud Identity + Cloud IAM       |
| Monitoring, logging, and analytics | Azure Monitor & Log Analytics | Amazon CloudWatch             | Cloud Monitoring + Cloud Logging |
| Governance and policy enforcement  | Azure Policy                  | AWS Config                    | Organization Policy Service      |
| Cloud security posture management  | Microsoft Defender for Cloud  | AWS Security Hub              | Security Command Center          |
| SIEM and security operations       | Microsoft Sentinel            | Security Hub + Security Lake  | Google Security Operations       |

---

### Microsoft Entra ID

#### Overview

1. **Azure:** Microsoft Entra ID

Microsoft Entra ID (formerly Azure Active Directory) is Microsoft's cloud-based identity and access management service. It provides authentication, authorization, single sign-on, role-based access control, and other identity security capabilities.

2. **AWS:** AWS IAM and IAM Identity Center

AWS Identity and Access Management (IAM) controls access to AWS resources through users, roles, and policies. AWS IAM Identity Center extends identity management by providing centralized workforce access and single sign-on across multiple AWS accounts and applications.

3. **GCP:** Cloud Identity and IAM

Google Cloud Identity provides identity management and single sign-on capabilities, while Google Cloud IAM controls authorization to Google Cloud resources through roles and permissions.

#### Feature Comparison

| Feature                     | Microsoft Entra ID | AWS IAM / IAM Identity Center                    | Cloud Identity / IAM           |
| --------------------------- | ------------------ | ------------------------------------------------ | ------------------------------ |
| Single Sign-On              | Yes                | Yes                                              | Yes                            |
| Multi-Factor Authentication | Yes                | Yes                                              | Yes                            |
| Role-based access           | Yes                | Yes                                              | Yes                            |
| Federation                  | Yes                | Yes                                              | Yes                            |
| Conditional access          | Yes                | Available through AWS identity/security controls | Context-aware access available |
| Identity governance         | Yes                | Available                                        | Available                      |

#### Security & Compliance

All three platforms provide identity and access controls that can be used to support compliance requirements such as least privilege, multi-factor authentication, access auditing, and separation of duties.

- Microsoft Entra ID additionally provides capabilities such as Conditional Access and Identity Protection. 
- AWS uses IAM policies, roles, permission boundaries, and other identity services to control access. 
- Google Cloud combines Cloud Identity and IAM roles and policies to provide similar controls.

#### Pricing Model

- Microsoft Entra ID has a free tier and paid licensing tiers for advanced identity capabilities. 
- AWS IAM is generally available without an additional charge, while organizations pay for the AWS resources used with it and may incur costs for related identity services. 
- Google provides free and premium Cloud Identity offerings, with costs depending on the selected identity capabilities.

#### DevSecOps Integration

Identity services are important in DevSecOps because CI/CD pipelines and automation tools require secure identities to access cloud resources. All three platforms support service identities, role-based permissions, APIs, command-line tools, and Infrastructure as Code solutions that allow permissions to be managed automatically.

### Azure Monitor and Log Analytics

#### Overview

1. **Azure:** Azure Monitor and Log Analytics

Azure Monitor collects metrics, logs, and telemetry from applications and Azure resources. Log Analytics allows collected log data to be queried and analyzed using Kusto Query Language (KQL).

2. **AWS:** Amazon CloudWatch

Amazon CloudWatch provides monitoring, logging, metrics, dashboards, alarms, and observability capabilities for AWS resources and applications.

3. **GCP**: Google Cloud Observability

Google Cloud Observability provides services such as Cloud Monitoring and Cloud Logging for collecting and analyzing application and infrastructure telemetry.

#### Feature Comparison

| Feature                | Azure Monitor | Amazon CloudWatch        | Google Cloud Observability |
| ---------------------- | ------------- | ------------------------ | -------------------------- |
| Metrics                | Yes           | Yes                      | Yes                        |
| Centralized logging    | Yes           | Yes                      | Yes                        |
| Log queries            | KQL           | CloudWatch Logs Insights | Logging query tools        |
| Alerts                 | Yes           | Yes                      | Yes                        |
| Dashboards             | Yes           | Yes                      | Yes                        |
| Application monitoring | Yes           | Yes                      | Yes                        |

#### Security & Compliance

Centralized logging helps organizations maintain audit trails and detect abnormal activity. Each platform provides access controls, encryption, logging, retention capabilities, and integrations with security services that can support regulatory and compliance requirements.

#### Pricing Model

The three services generally follow usage-based pricing. Major cost factors include the volume of logs ingested, log retention, queries, metrics, and additional monitoring capabilities.

#### DevSecOps Integration

Monitoring services can collect logs and metrics from applications deployed through CI/CD pipelines. Alerts can notify DevSecOps teams when abnormal behavior, application failures, or security events occur. APIs, command-line tools, and Infrastructure as Code can also be used to automate monitoring configuration.

### Azure Policy

#### Overview

1. **Azure**: Azure Policy

Azure Policy is a governance service used to evaluate Azure resources against organizational rules. Policies can audit non-compliant resources, deny invalid deployments, modify configurations, and enforce organizational standards.

2. **AWS**: AWS Config

AWS Config records resource configurations and evaluates resources against Config rules. It can identify resources that do not comply with organizational requirements and can be combined with remediation mechanisms.

3. **GCP**: Organization Policy Service

Google Cloud Organization Policy Service allows administrators to define centralized constraints that control how resources can be configured across an organization, folder, or project.

#### Feature Comparison

| Feature                        | Azure Policy | AWS Config                         | Organization Policy               |
| ------------------------------ | ------------ | ---------------------------------- | --------------------------------- |
| Policy enforcement             | Yes          | Primarily evaluation through rules | Yes                               |
| Compliance evaluation          | Yes          | Yes                                | Yes                               |
| Centralized governance         | Yes          | Yes                                | Yes                               |
| Resource configuration control | Yes          | Yes                                | Yes                               |
| Automated remediation          | Supported    | Supported through integrations     | Supported for applicable policies |

#### Security & Compliance

The three governance services can help organizations prevent or identify insecure configurations. Example policies can restrict resource locations, require specific configuration settings, prevent publicly accessible resources, or enforce organizational security requirements.

#### Pricing Model

- Azure Policy itself generally does not add a separate charge for policy evaluation, although related services may create costs. 
- AWS Config uses usage-based pricing based on factors such as configuration items and rule evaluations. 
- Google Cloud Organization Policy Service API usage is free.

#### DevSecOps Integration

Policy-as-code allows governance requirements to become part of automated infrastructure deployment. Policies can be managed using APIs, CLI tools, Terraform, and other Infrastructure as Code technologies. This helps prevent non-compliant infrastructure from reaching production.

### Microsoft Defender for Cloud

#### Overview

1. **Azure**: Microsoft Defender for Cloud

Microsoft Defender for Cloud provides cloud security posture management and workload protection. It identifies security weaknesses, provides recommendations, evaluates compliance, and detects threats against cloud workloads.

2. **AWS**: AWS Security Hub

AWS Security Hub provides centralized cloud security management by aggregating security findings and evaluating the security posture of AWS environments.

3. **GCP**: Security Command Center

Google Security Command Center provides centralized security posture management, vulnerability detection, threat detection, and security findings for Google Cloud environments.

#### Feature Comparison

| Feature                     | Defender for Cloud | AWS Security Hub                             | Security Command Center   |
| --------------------------- | ------------------ | -------------------------------------------- | ------------------------- |
| Security posture management | Yes                | Yes                                          | Yes                       |
| Security findings           | Yes                | Yes                                          | Yes                       |
| Compliance monitoring       | Yes                | Yes                                          | Yes                       |
| Vulnerability information   | Yes                | Through integrated AWS services              | Yes                       |
| Threat detection            | Yes                | Through Security Hub and integrated services | Yes                       |
| Multi-cloud capabilities    | Yes                | Primarily AWS with integrations              | Available in higher tiers |

#### Security & Compliance

All three services help organizations continuously evaluate cloud environments against security best practices and compliance frameworks. 

For example, Microsoft Defender for Cloud provides a regulatory compliance dashboard for assessing resources against supported standards and benchmarks. AWS Security Hub supports security standards such as CIS, PCI DSS, and NIST, while Google Security Command Center also provides compliance monitoring capabilities.

#### Pricing Model

Defender for Cloud pricing depends on the protection plans and workloads being protected. AWS Security Hub pricing depends on enabled capabilities and monitored resources. Google Security Command Center provides Standard, Premium, and Enterprise tiers, with Standard available without charge and advanced tiers using paid pricing models.

#### DevSecOps Integration

These services can identify vulnerabilities and misconfigurations during cloud operations and feed findings into automated security workflows. APIs and automation tools allow security findings to be incorporated into DevSecOps processes and remediation workflows.

### Microsoft Sentinel

#### Overview

1. **Azure**: Microsoft Sentinel

Microsoft Sentinel is a cloud-native Security Information and Event Management (SIEM) platform with security orchestration, automation, and response capabilities. It collects security data from multiple sources and uses analytics rules to identify suspicious activities.

2. **AWS**: AWS Security Hub and Amazon Security Lake

AWS does not provide a single service that maps exactly to Microsoft Sentinel. AWS Security Hub centralizes security findings, while Amazon Security Lake centralizes security data for analysis. Additional AWS services can be integrated to provide detection and automated response capabilities.

3. **GCP**: Google Security Operations

Google Security Operations provides cloud-based SIEM and SOAR capabilities for collecting security telemetry, detecting threats, investigating incidents, and automating security responses.

#### Feature Comparison

| Feature                         | Microsoft Sentinel | AWS Security Services                  | Google Security Operations |
| ------------------------------- | ------------------ | -------------------------------------- | -------------------------- |
| Centralized security data       | Yes                | Yes                                    | Yes                        |
| SIEM                            | Yes                | Through multiple services/integrations | Yes                        |
| Threat detection                | Yes                | Yes                                    | Yes                        |
| Incident investigation          | Yes                | Yes                                    | Yes                        |
| Automated response / SOAR       | Yes                | Through integrations and automation    | Yes                        |
| Threat intelligence integration | Yes                | Yes                                    | Yes                        |

#### Security & Compliance

SIEM platforms support compliance by centralizing security logs and maintaining information that can be used for auditing, threat investigation, and incident response. They can also correlate events from multiple systems to identify suspicious behavior that may not be visible from a single log source.

#### Pricing Model

- Microsoft Sentinel pricing is primarily influenced by security data ingestion, analytics, and retention. 
- AWS costs depend on the combination of security services being used and their respective usage models. 
- Google Security Operations generally uses enterprise-oriented pricing based on the selected offering and usage or subscription agreement.

#### DevSecOps Integration

SIEM and SOAR platforms can receive logs from applications, infrastructure, identity systems, and CI/CD environments. Detection rules can identify suspicious activities, while automated workflows can trigger notifications or remediation actions when security incidents are detected.

### Overall Analysis

Although Azure, AWS, and Google Cloud provide similar security services, the services themselves are organized differently.

- Microsoft provides relatively integrated services such as Defender for Cloud and Sentinel that connect security posture management, monitoring, threat detection, and incident response with the wider Azure ecosystem.
- AWS frequently separates these capabilities across specialized services. For example, AWS Config focuses on resource configuration and compliance, CloudWatch provides monitoring, and Security Hub aggregates security findings. Therefore, an Azure service does not always have a direct one-to-one AWS equivalent.
- Google Cloud follows a similar approach but provides centralized products such as Security Command Center for cloud security and Google Security Operations for SIEM and SOAR.

From a DevSecOps perspective, all three platforms provide APIs, command-line tools, identity controls, monitoring, and Infrastructure as Code integrations. This allows security requirements to be incorporated throughout the development and deployment lifecycle rather than being applied only after deployment.

## Conclusion

Azure, AWS, and Google Cloud all provide services that address identity management, monitoring, governance, cloud security posture, and threat detection. While the names and architectures of these services differ, their overall security goals are similar.

The main difference is how each cloud provider divides these capabilities among its services. Understanding these differences is important for DevSecOps professionals because equivalent security architectures may require different combinations of services when moving workloads between cloud platforms.