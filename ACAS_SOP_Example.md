# **Standard Operating Procedure (SOP) for Handling Scan Results in ACAS**

## **1. Purpose**
Here is an example that outlines the procedures for handling the results of vulnerability scans and compliance checks conducted using ACAS tools (Nessus, SecurityCenter, PVS, LCE). 
The purpose is to ensure that vulnerabilities and non-compliance issues are addressed in accordance with DoD policies, thereby securing the organization’s network and systems.

---

## **2. Scope**
This procedure applies to all personnel involved in the process of reviewing, analyzing, and remediating vulnerabilities and compliance issues discovered by ACAS scanning tools. It covers the following:
- **Vulnerability Analysis**
- **Compliance Auditing**
- **Prioritization and Risk Assessment**
- **Remediation**
- **Reporting and Documentation**

---

## **3. Roles and Responsibilities**

### **3.1 Vulnerability Manager**
- Oversee the scan review process.
- Ensure that all identified vulnerabilities are addressed according to DoD priorities.
- Maintain documentation of vulnerability remediation efforts.

### **3.2 System Administrators**
- Investigate and resolve vulnerabilities identified in ACAS scans.
- Work with relevant teams to patch systems or apply mitigations.

### **3.3 Compliance Officer**
- Review scan results to ensure compliance with DoD regulations (e.g., NIST SP 800-53, DISA STIGs).
- Recommend corrective actions for non-compliant systems.

### **3.4 Security Operations Team**
- Monitor and support incident detection using LCE logs and alerts.
- Ensure ongoing system health and security posture.

---

## **4. Procedure for Handling Scan Results**

### **4.1 Review and Analyze Scan Results**
Once the scan is completed by Nessus, PVS, or any other ACAS component, the following steps must be taken:

1. **Access Results**:
   - Login to the **SecurityCenter** interface.
   - Navigate to **Scans** > **Scan Results**.
   - Review results by selecting the relevant scan and ensuring that all devices and systems were scanned.

2. **Initial Review**:
   - Ensure that all findings are categorized by severity (Critical, High, Medium, Low).
   - Verify that there are no false positives or errors within the scan.

3. **Vulnerability Mapping**:
   - Map vulnerabilities to relevant **DoD security standards** (e.g., DISA STIGs, NIST SP 800-53) to verify if they are considered a compliance issue.
   - Prioritize vulnerabilities based on risk to the mission, data sensitivity, and potential impact.

4. **Compliance Check**:
   - Review vulnerabilities that impact compliance with DoD policies, such as configuration issues or system misalignments with security standards.
   - Identify any non-compliant configurations, particularly those violating the **DISA STIGs** or **NIST 800-53** requirements.

### **4.2 Prioritize Vulnerabilities**

Vulnerabilities should be triaged and prioritized based on risk and criticality:

1. **Critical Vulnerabilities (High Severity)**:
   - Must be addressed immediately.
   - Escalate to senior leadership if remediation is delayed.
   - Follow the **DoD Vulnerability Management Framework** for expedited resolution.

2. **High Vulnerabilities**:
   - Must be addressed within **15 calendar days** (DoD policy).
   - Review patches or configuration changes to mitigate the issue.
   
3. **Medium Vulnerabilities**:
   - Address within **30 calendar days** (DoD policy).
   - Review system configurations and apply changes if necessary.

4. **Low Vulnerabilities**:
   - Address based on risk and impact, potentially within **45 calendar days** (DoD policy).
   - Low-risk vulnerabilities should be monitored for any escalation.

5. **False Positives**:
   - If identified as a false positive, document and close the issue. Ensure that relevant evidence (e.g., logs, configurations) is attached for review.

### **4.3 Risk Assessment**
- Perform a risk assessment of each identified vulnerability, considering the following factors:
  - **Potential Impact**: What is the potential damage if the vulnerability is exploited?
  - **Exploitability**: How easy is it to exploit the vulnerability?
  - **Exposure**: What systems or data are exposed to this vulnerability?
  - **Mitigation Availability**: Are there available patches or workarounds?

### **4.4 Remediation Actions**

1. **Immediate Remediation (Critical and High Vulnerabilities)**:
   - Apply patches, configuration changes, or workarounds within the timelines outlined by DoD policies.
   - For critical vulnerabilities, escalate remediation efforts to senior management for visibility and action.
   - Ensure patching is verified and documented in the remediation process.

2. **Long-Term Remediation (Medium and Low Vulnerabilities)**:
   - Schedule patches or configuration changes within the next available maintenance window.
   - If a patch or mitigation is unavailable, implement compensating controls such as network isolation, enhanced monitoring, or system lockdown.
   - Verify effectiveness after remediation is applied by re-scanning the system.

3. **Document Remediation**:
   - Each remediation action must be documented in the system logs, along with the reason for the action taken.
   - Remediation efforts should include the person responsible, time of action, and impact.

### **4.5 Verification**

1. **Re-scan Systems**:
   - After remediation, re-scan the affected systems to verify that vulnerabilities were effectively mitigated.
   - Update remediation status in SecurityCenter (e.g., “Fixed” or “In Progress”).

2. **Compliance Verification**:
   - Ensure that systems now align with relevant **DoD security baselines** (e.g., DISA STIGs, NIST 800-53) after remediation.
   - Revalidate compliance post-remediation to confirm that the security posture is acceptable.

### **4.6 Reporting and Documentation**

1. **Create Reports**:
   - Generate reports from SecurityCenter detailing the vulnerabilities identified, remediation actions taken, and results of re-scanning.
   - Use DoD-standard formats for compliance reports where required (e.g., for Risk Management Framework (RMF) or continuous monitoring).

2. **Escalation**:
   - If remediation is not completed within the required timeframe, escalate the issue to higher-level management or the ISSO (Information Systems Security Officer) for further action.
   - Provide status updates and remedial action plans as necessary.

3. **Maintain Documentation**:
   - Retain a record of all scan results, remediation actions, and compliance verifications in accordance with DoD retention policies.
   - Ensure that these documents are readily available for auditing and review by external entities.

---

## **5. Compliance with DoD Policies**

### **5.1 Vulnerability Management (DoD Policy)**
- Follow the **DoD Vulnerability Management Framework**, which outlines timelines for remediation based on severity:
  - **Critical vulnerabilities** must be remediated within **72 hours**.
  - **High vulnerabilities** must be remediated within **15 calendar days**.
  - **Medium vulnerabilities** must be remediated within **30 calendar days**.
  - **Low vulnerabilities** should be addressed within **45 calendar days**.

### **5.2 Continuous Monitoring**
- ACAS should be integrated into a continuous monitoring program to ensure that vulnerabilities and compliance issues are regularly assessed and addressed.
- Ensure that systems are continuously scanned and evaluated for changes in risk posture.

---

## **6. Conclusion**

By following these procedures, the organization can maintain a secure network environment, ensure compliance with DoD regulations, and mitigate security risks in a timely manner.

