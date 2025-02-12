# Nikto web server scanner

Nikto is a web server scanner that can identify various potential issues and vulnerabilities. Here are some of the
things Nikto can find:

* Outdated server software
* Default files and configurations
* Insecure files and scripts
* Configuration issues
* Potentially dangerous files
* Server and software misconfigurations
* Directory indexing
* Cross-site scripting (XSS) vulnerabilities
* SQL injection vulnerabilities
* Remote file inclusion (RFI) vulnerabilities
* Server information disclosure

## Example
```bash
nikto -h http://example.com -output scan_results.txt
```
