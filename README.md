# SIEM-Detection-as-Code.
# SIEM Detection-as-Code (DaC)

## Overview
This repository serves as a centralized, version-controlled environment for managing Security Information and Event Management (SIEM) detection rules. By implementing a Detection-as-Code (DaC) methodology, this project automates the deployment and synchronization of security alerts across different SIEM platforms, specifically Splunk and IBM QRadar.

## Key Capabilities
- **Centralized Rule Management:** Detection rules are maintained in structured, standardized JSON formats.
- **Version Control & Auditing:** Every modification to a rule is tracked, providing a clear history of changes, peer reviews, and easy rollbacks.
- **Automated Deployment (CI/CD):** GitHub Actions are utilized to automatically push updated rules to the target SIEM environments.
- **Cross-Platform Support:** Directory structure is designed to handle rule configurations for multiple SIEM vendors independently.

## Project Structure
.
├── .github/workflows/   # CI/CD pipeline configurations (main.yml)
├── qradar/              # IBM QRadar specific detection rules (rules.json)
├── splunk/              # Splunk specific correlation rules (rules.json)
├── scripts/             # Python automation and API scripts (sync_splunk.py)
└── README.md            # Project documentation

## Workflow Execution
1. **Rule Modification:** A SOC Analyst creates or updates a detection rule within the respective "rules.json" file.
2. **Commit & Push:** The configuration changes are committed and pushed to the main branch.
3. **Pipeline Activation:** The GitHub Actions workflow (main.yml) detects the changes and triggers the CI/CD pipeline.
4. **API Integration:** The pipeline executes the Python automation scripts (sync_splunk.py), which authenticate via REST API and dynamically update the saved searches or rules directly in the SIEM production environment.

## Technologies Used
- **Platforms:** Splunk Enterprise, IBM QRadar
- **Scripting & Automation:** Python 3, REST APIs
- **CI/CD Pipeline:** GitHub Actions
- **Data Serialization:** JSON


