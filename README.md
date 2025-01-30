# Domain Email Security Checker

A simple Go program that checks the email security configurations (MX, SPF, and DMARC) of a given domain.

## Features
- Checks if the domain has an **MX (Mail Exchange) record**.
- Verifies if the domain has an **SPF (Sender Policy Framework) record**.
- Retrieves the **SPF record content**.
- Checks if the domain has a **DMARC (Domain-based Message Authentication, Reporting & Conformance) record**.
- Retrieves the **DMARC record content**.
- Outputs the results in CSV format.

## Code
The program follows these steps:
1. Reads domain names from the standard input.
2. Uses `net.LookupMX(domain)` to check for MX records.
3. Uses `net.LookupTXT(domain)` to retrieve TXT records and check for SPF policies.
4. Uses `net.LookupTXT("_dmarc." + domain)` to check for DMARC policies.
5. Prints the results in CSV format.
