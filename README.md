# CVE-2024-11728
KiviCare – Clinic &amp; Patient Management System (EHR) WordPress Plugin Unauthenticated SQL Injection PoC

This repository contains a Proof of Concept (PoC) script for exploiting an SQL Injection vulnerability in the KiviCare – Clinic &amp; Patient Management System (EHR) WordPress Plugin, versions up to and including 3.6.4. The vulnerability allows unauthenticated attackers to execute arbitrary SQL queries via the visit_type[service_id] parameter in the tax_calculated_data AJAX action.
For more details, please refer to the [blog post](https://samogod.com/2024/12/11/cve-2024-11728-kivicare-wordpress-unauthenticated-sql-injection/).

# CVE-2024-11728 - KiviCare WordPress Plugin Unauthenticated SQL Injection PoC

## Description

The KiviCare plugin is vulnerable due to insufficient escaping of user-supplied input in the `visit_type[service_id]` parameter. This allows attackers to append additional SQL queries, potentially leading to data extraction or other malicious activities.

## Usage

### Prerequisites

- Python 3.x
- Required Python packages: `requests`, `argparse`, `urllib3`

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/CVE-2024-11728.git
   cd CVE-2024-11728
   ```

2. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

### Running the Script

To execute the script, use the following command:
```bash
python3 CVE-2024-11728.py -u <target_url> [-t <timeout>] [-v]
- -u, --url: Target URL (e.g., http://example.com)
- -t, --timeout: Request timeout in seconds (default: 10)
- -v, --verbose: Enable verbose output for debugging
```
### Example
```bash
python3 CVE-2024-11728.py -u https://wordpress.samogod.com -v
```
## Important Notes

- **Nonce Handling**: The script currently requires a valid `_ajax_nonce` value. This value is session-specific and must be obtained manually or through an automated process.
- **Legal Disclaimer**: This script is intended for educational purposes and authorized security testing only. Unauthorized use of this script against systems you do not own or have explicit permission to test is illegal.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

