# ACAS (Assured Compliance Assessment Solution) Setup Guide

## **1. Pre-Requisites**
Before starting the installation, ensure you have:
- **A dedicated server or VM** for each component (SecurityCenter, Nessus, PVS, LCE).
- **Operating Systems**: ACAS is typically deployed on **Linux (CentOS/RedHat)** or **Windows**.
- **Access to ACAS software** (Nessus, SecurityCenter, PVS, LCE) through official DoD or Tenable channels.
- **Proper network configuration** to integrate the components (e.g., ensure no firewall rules block necessary ports).

---

## **2. Install Nessus (Vulnerability Scanner)**

Nessus is the core of ACAS for scanning vulnerabilities.

### **Steps**:
1. **Download Nessus**:
   - Go to the [Tenable website](https://www.tenable.com/downloads/nessus) to download the Nessus installation package for your operating system.
   - Alternatively, you can get Nessus through official DoD channels if applicable.

2. **Install Nessus**:
   - For **Linux (CentOS/RedHat)**:
     ```bash
     sudo yum install -y https://download.tenable.com/nessus3dl.php?file=nessus-<version>-es7.x86_64.rpm
     sudo systemctl start nessusd
     sudo systemctl enable nessusd
     ```
   - For **Windows**:
     - Run the installer and follow the prompts.

3. **Configure Nessus**:
   - Access Nessus via a web browser: `https://<Nessus_Server_IP>:8834/`.
   - Set up an administrator account during the first-time setup.

4. **License Nessus**:
   - You will need to activate Nessus with a valid license key (you can use a free trial or paid license depending on your organization’s setup).

---

## **3. Install SecurityCenter (Centralized Management)**

SecurityCenter is the platform that centralizes your Nessus scans, vulnerabilities, and reports.

### **Steps**:
1. **Download SecurityCenter**:
   - Go to [Tenable SecurityCenter](https://www.tenable.com/products/tenable-sc) to download the appropriate version for your system.

2. **Install SecurityCenter**:
   - For **Linux**:
     ```bash
     sudo yum install -y <SecurityCenter_Package>
     sudo systemctl start tenable-sc
     sudo systemctl enable tenable-sc
     ```
   - For **Windows**:
     - Run the installer and follow the setup prompts.

3. **Configure SecurityCenter**:
   - Once installed, access the SecurityCenter web interface via `https://<SecurityCenter_IP>:443/`.
   - Set up an admin user and configure necessary settings like email, notifications, and integration options.

4. **Integrate Nessus with SecurityCenter**:
   - In SecurityCenter, go to **Configuration** > **Nessus Scanners**.
   - Add the Nessus server you installed earlier by providing the Nessus IP and credentials.

---

## **4. Install Passive Vulnerability Scanner (PVS)**

PVS is used to scan your network for vulnerabilities without actively scanning the systems. It’s used for passive monitoring.

### **Steps**:
1. **Download PVS**:
   - Get the installation package from Tenable or your DoD portal.

2. **Install PVS**:
   - For **Linux**:
     ```bash
     sudo yum install -y <PVS_Package>
     sudo systemctl start pvs
     sudo systemctl enable pvs
     ```
   - For **Windows**:
     - Run the installer and follow the prompts.

3. **Configure PVS**:
   - Access PVS via a web browser: `https://<PVS_Server_IP>:8834/`.
   - Set up your admin account.

4. **Integrate PVS with SecurityCenter**:
   - Go to SecurityCenter and configure PVS integration under **Configuration** > **PVS**.
   - Add your PVS instance using the IP and credentials.

---

## **5. Install Log Correlation Engine (LCE)**

The LCE is used to aggregate and correlate logs from various devices and systems in the network.

### **Steps**:
1. **Download LCE**:
   - Obtain the LCE installation package from Tenable.

2. **Install LCE**:
   - For **Linux**:
     ```bash
     sudo yum install -y <LCE_Package>
     sudo systemctl start lce
     sudo systemctl enable lce
     ```
   - For **Windows**:
     - Follow the installation wizard.

3. **Configure LCE**:
   - Access LCE via a web browser: `https://<LCE_Server_IP>:8834/`.
   - Set up the LCE user interface and configure connections to the systems you wish to collect logs from.

4. **Integrate LCE with SecurityCenter**:
   - Go to SecurityCenter and configure LCE under **Configuration** > **LCE**.
   - Provide the necessary details to establish communication between SecurityCenter and LCE.

---

## **6. Configure Network and User Access**

1. **Firewall Configuration**:
   - Ensure the necessary ports are open between the SecurityCenter, Nessus, PVS, and LCE components. The following ports are typically required:
     - **8834**: For Nessus and SecurityCenter communication.
     - **443**: For SecurityCenter web access.
     - **UDP 514**: For LCE to receive log data.
   - If using **cloud services** or external networks, ensure appropriate security measures like VPNs are in place.

2. **User Setup**:
   - Set up user accounts and permissions in SecurityCenter to define who can access scans, reports, and configuration settings.
   - Roles can range from **Administrator** to **Read-Only** users, depending on the level of access needed.

---

## **7. Running Vulnerability Scans and Compliance Checks**

1. **Create Scan Policies**:
   - In SecurityCenter, create scan policies for the type of vulnerability assessments you want to perform (e.g., network scanning, web app scanning).
   
2. **Run Scans**:
   - Initiate vulnerability scans from SecurityCenter, targeting your network devices, servers, and other systems.
   - You can schedule scans to run at specific times to avoid network congestion.

3. **Compliance Audits**:
   - Configure compliance checks based on **NIST SP 800-53**, **DISA STIGs**, or other security frameworks.
   - Review the compliance status of your systems and make necessary corrections.

---

## **8. Review Reports and Remediation**

1. **Review Scan Results**:
   - After scans are completed, review the results in SecurityCenter.
   - Reports will show discovered vulnerabilities, along with severity ratings.

2. **Prioritize Remediation**:
   - Use the reports to prioritize which vulnerabilities need immediate attention, considering risk factors, such as exposure and exploitability.

3. **Track Compliance**:
   - Use compliance dashboards to ensure your systems are following DoD security standards.
   - Correct non-compliant configurations and re-scan to verify remediation.

---

## **9. Ongoing Maintenance**

1. **Regular Scanning**:
   - Schedule regular vulnerability and compliance scans to continuously monitor your network.

2. **Update Signatures**:
   - Keep Nessus, PVS, and LCE up to date with the latest vulnerability signatures and patches.

3. **Log Monitoring**:
   - Monitor logs and alerts from LCE to detect potential security incidents or misconfigurations in real-time.

4. **Documentation and Reporting**:
   - Maintain detailed records of scan results, compliance checks, and remediation efforts for auditing purposes.

---

## **Conclusion**

By following these steps, you will set up a fully functional **ACAS (Assured Compliance Assessment Solution)** to assess network vulnerabilities and ensure compliance with security standards. Make sure to continually update your systems and scans to stay ahead of emerging vulnerabilities and threats.

If you encounter any specific issues during installation, refer to the official Tenable documentation or DoD-specific guides for additional configuration details.
