# Automated Web Security Scanner

**Student:** Syeda Aairah Ahmed  
**Program:** IBM SkillsBuild Cyber Security 2026  
**Project level:** Beginner

## 1. Project description
This Python/Jupyter project checks selected HTTP security response headers and flags a small number of CORS response-header patterns for human review. It displays findings in a table and can export the offline sample findings to CSV.

This is an educational checker, not a complete vulnerability scanner. A missing header or wildcard CORS value is not automatically proof of a vulnerability.

## 2. Features
- Checks Content-Security-Policy (CSP)
- Checks Strict-Transport-Security (HSTS)
- Checks X-Content-Type-Options
- Checks Referrer-Policy
- Checks Permissions-Policy
- Reviews `Access-Control-Allow-Origin`
- Includes reproducible offline sample headers
- Optional single-request live check for authorized targets
- Exports findings to `sample_scan_results.csv`

## 3. Technologies
- Python 3.10+
- Jupyter Notebook
- `requests`
- `pandas`
- HTTP response headers and basic CORS concepts

## 4. Files
- `Syeda_Aairah_Ahmed_AutomatedWebScanner.ipynb` — notebook code and explanation
- `requirements.txt` — Python dependencies
- `Syeda_Aairah_Ahmed_ProjectReport.docx` — project report

## 5. Installation and execution
1. Install Python 3.10 or newer.
2. Put the notebook and `requirements.txt` in the same folder.
3. (Recommended) create a virtual environment.

### Windows
```bash
py -m venv .venv
.venv\Scripts\activate
```

### macOS/Linux
```bash
python3 -m venv .venv
source .venv/bin/activate
```

4. Install packages:
```bash
python -m pip install -r requirements.txt
```

5. Start Jupyter:
```bash
jupyter notebook
```

6. Open `Syeda_Aairah_Ahmed_AutomatedWebScanner.ipynb` and run cells from top to bottom. The offline sample does not contact any website and should run first.

## 6. Dataset and test data
No external dataset is required. The notebook includes fictional response headers to provide a reproducible offline demonstration.

Reference material:
- OWASP Secure Headers Project: https://owasp.org/www-project-secure-headers/
- MDN HTTP headers: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers
- MDN CORS: https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS

## 7. Optional live check
The notebook includes `scan_authorized_url(url)`. Only use it against a website you own or have explicit permission to assess. It makes one GET request, follows redirects, and uses a timeout. It does not crawl links or attempt exploitation. Uncomment the example lines in the notebook and replace the example URL with an authorized target.

## 8. Expected sample results
The offline sample includes CSP and X-Content-Type-Options, omits HSTS, Referrer-Policy, and Permissions-Policy, and uses `Access-Control-Allow-Origin: *`. Expected outcomes include Present for the two included headers, Missing for the three omitted headers, and Review for the wildcard CORS value.

## 9. Limitations
This is not a full web application assessment. It does not test authentication, authorization, business logic, server-side code, TLS configuration, or every CORS behavior. Header presence does not guarantee correct configuration.

## 10. Responsible use
Only test systems you own or have explicit permission to assess. Do not use this tool to disrupt services, access private information, or bypass access controls.
