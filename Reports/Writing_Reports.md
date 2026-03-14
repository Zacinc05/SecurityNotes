Presentation Roadmap

- The Philosophy of Reporting  
  - Why the report is the most valuable part of the engagement  
- Assessment Archetypes  
  - Understanding how the type of test dictates the report's structure  
- The Modular Components  
  - A deep dive into every section of a professional report, from the Legal Notice to the technical Appendices  
- Technical Writing Standards  
  - How to document findings with enough detail for an engineer to replicate your work.  
- Adjusted CVSS Calculations  
  - How to properly assess the threat level of a vulnerability, assign a score to it, and report it accordingly  
- Professional Standards  
  - Tips for formatting, redacting sensitive data, and the final Quality Assurance (QA) process

Types of Reports

- Vulnerability Assessment  
  - Identify as many flaws as possible  
  - High-volume list of every potential flaw often found by an automated scanner  
  - Board coverage. Wide view of env.  
  - Typically no exploitation  
- Penetration Test  
  - Targeted test including manual testing and full proof of concept (POC)  
  - Focuses on the "Attack Chain". Prove how an attacker can move laterally  
  - Tell a story. How a low risk can lead to critical compromise  
- Compliance-Driven  
  - Written to satisfy specific bodies (GDPR, HIPAA, etc.)  
  - Map technical findings directly to legal violations  
  - Can be part of a typical penetration test  
- Specialized Tests  
  - Many Unique types  
    - WASA (Web Application reports)  
    - Physical Security Assessments  
    - Attestation Reports  
      - Short summaries for third-party vendors that don’t reveal sensitive technical details  
    - etc.  
  - Have different frameworks/deliverable from a common pen test

Report Difference

- Vuln assess vs Pen Test  
  - A vulnerability scan may list many issues  
  - A pentest report shows how three of those issues can be chained to cause mischief (i.e. damage, access, lateral movement)

Draft Reports

- Most orgs request/prefer initially use a draft report  
- Allows client to provide feedback or explain how they plan to address specific findings  
- Once both parties agree to content, you issue a final report.  
- Be ready to accommodate reasonable requests

Know the Audience

- Executive  
  - Looking for the ‘so what?’  
  - Not focused on the how, need to know safety  
  - Executive Summary is catered for them  
- Technical Staff  
  - Need the ‘how to’  
  - Report should contain enough information/guidance for developers/admins to recreate the issue and verify correction  
  - In technical part of report

Components of a Report

- Front Matter (Legal & Overview)  
  - Establish legal/admin boundaries to test  
  - Legal Disclaimer & Sensitivity Warning  
    - Explicitly states who owns the data and the penalties for unauthorized release.  
  - Contact Information  
    - Provides a clear line of communication between the testing team and client's emergency response contacts.  
  - Executive Summary  
    - High-level summary for executives  
  - Engagement Overview  
    - Goals and Scope  
    - what was allowed to be tested (IP ranges, domains, or physical locations)  
    - ensure the testers didn't stray into unauthorized systems.

- Executive Summary  
  - Most read part of the document  
  - for non technical stakeholders who allocate budgets  
  - Summarize total finding counts, severity, describes risks in terms of CIA triad  
  - 1-2 pages  
  - Refrain from Technical language  
  - Overview of what was tested  
  - Extremely broad overview of the most impactful things  
  - Include any other info found necessary for non technical execs to know  
- Defining Scope  
  - Rigid list of allowed targets  
    - List to stay within legal boundaries  
    - Class C networks, network eagles, hosts, etc.  
  - Best practice  
  - Should already be defined in pre-engagement contracts

Technical Report and Findings

- Calculate CVSS scores  
  - CVSS (Common Vulnerability Scoring System). 0.0 to 10.0  
  - Based on how easy a bug is to exploit and damage it does  
  - A raw CVSS score isn’t enough. Need Adjusted CVSS score, cater to client  
    - ex) outdated browser less risky on locked-kiosk than a ceo laptop  
  - Calculation  
    - https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator  
    - Only need to pay attention to the “Base Score Metrics  
    - The calculator will then give you a “CVSS 3.1 Vector”  
      (components of assessment, can adjust) and an OverallCVSS Score (double 0-10)  
  - Adjust Calculation  
    - Choose a likelihood category and an impact category  
      (very high, high, moderate, low, insignificant)  
    - Use best judgement to change score from calc slightly based on the circumstances of occurrence  
- Categorize  
  - After adjusted calculation and considerations  
  - critical 9-10, high 7-8.9, medium 4-6.9, low 1-3.9, informational 0-0.9  
  - List:  
    - Final adjusted score  
    - CVSS 3.1 Vector from calculator  
    - Likelihood and Impact  
    - Good to format in table, add affected system info  
      (IP, port, service, version)

Anatomy of Technical Finding

- Each finding should follow a consistent modular structure  
  - Adjusted CVSS Score  
    - 0-10 rating with likelihood/impact on business  
  - Details:  
    - High-level explanation of the vulnerability  
- Confirmation  
  - Step-by-step evidence, including specific commands used and terminal output, along with screenshots where necessary for understanding/proof  
  - Impact  
    - Worst-case scenario for the client  
  - Mitigation  
    - Actionable advice on how to fix the issue  
    - Be clear as can be. Broad isn’t bad if issue is uncertain

