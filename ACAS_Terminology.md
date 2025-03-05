# ACAS Command Reference 
This document provides a list of essential ACAS commands and tasks for new admins to successfully conduct ACAS scans using **Nessus** and **SecurityCenter**.

## 1. Basic Commands for Starting and Managing Scans

### Create a Scan
- **Command/Action**: There is no specific terminal command for creating a scan. You will create scans via the **SecurityCenter** or **Nessus** web interface.
- **How to**: Navigate to the **Scans** tab and click on **Create Scan**.

### Launch a Scan
- **Command/Action**: After creating a scan, click **Launch** or **Start Scan** in the web interface.

### View Scan Progress
- **Command/Action**: Go to the **Scans** tab and select the scan you want to monitor. The status will be shown here.

### Stop a Scan
- **Command/Action**: In the **Scans** tab, select the scan you want to stop and click **Stop Scan**.

### View Scan Results
- **Command/Action**: After the scan is complete, go to the **Results** tab to view the findings. This can be done via the **SecurityCenter** or **Nessus** dashboard.

---

## 2. Managing Credentials

### Add Credentials for a Scan
- **Command/Action**: In **SecurityCenter**, go to the **Credentials** tab while configuring a scan and add the necessary system credentials (Windows, Unix, etc.).

### Test Credentials
- **Command/Action**: After entering credentials, you can click **Test** next to the credentials input field to verify if the provided credentials work.

---

## 3. Generating and Exporting Reports

### Generate a Scan Report
- **Command/Action**: Once the scan is complete, go to the **Reports** section and select the scan results to generate a report.

### Export Scan Report
- **Command/Action**: After generating the report, select the **Export** button and choose the desired format (PDF, HTML, CSV, etc.).

---

## 4. Scheduling Recurring Scans

### Schedule a Recurring Scan
- **Command/Action**: Go to the **Scans** section, click on **Schedule**, and set your preferred scan type, frequency (daily, weekly, monthly), and time.

---

## 5. User and Permissions Management

### Add a User
- **Command/Action**: In **SecurityCenter**, go to **User Management**, click **Add User**, and input the new user's credentials, roles, and permissions.

### Assign Permissions to User
- **Command/Action**: In **SecurityCenter**, go to **User Management** and assign the appropriate permissions based on the user’s role (admin, user, read-only).

---

## 6. Managing Plugins and Updates

### Check for Plugin Updates
- **Command/Action**: In **Nessus**, go to **Settings**, then **Plugin Feed** to check for and download the latest plugin updates.

### Install Plugins
- **Command/Action**: In **Nessus**, navigate to **Settings**, click **Update**, and install the latest plugins.

---

## 7. Troubleshooting Scans

### View Scan Logs
- **Command/Action**: In the **Results** or **Logs** tab, find the scan in question and view the detailed logs for errors or issues.

### Test System Connectivity
- **Command/Action**: Use **ping** or **telnet** to ensure the target system is reachable before running a scan.
    ```bash
    ping <Target IP>
    telnet <Target IP> 8834  # Port used by Nessus
    ```

---

## 8. Other Helpful ACAS Commands (CLI)

For those comfortable with the **command line interface (CLI)** for Nessus or SecurityCenter (via API calls):

### Start a Scan via API
- **Command/Action**: Use the **API** to start scans programmatically. Example:
    ```bash
    curl -k -X POST https://<ACAS_URL>/scans -d '{"scan_name": "Test Scan", "targets": "<target_ips>"}'
    ```

### Download Scan Results via API
- **Command/Action**: Fetch scan results using the API after the scan completes.
    ```bash
    curl -k -X GET https://<ACAS_URL>/scans/<scan_id>/results
    ```

### Check Plugin Versions
- **Command/Action** (Nessus CLI): To check the version of installed plugins:
    ```bash
    nessus -v
    ```

---

## 9. Backup and Restore Configuration

### Backup ACAS Configuration
- **Command/Action**: In **SecurityCenter**, navigate to **Settings** > **Backup** to back up the system configuration.

### Restore ACAS Configuration
- **Command/Action**: In **SecurityCenter**, navigate to **Settings** > **Restore** to restore the backup.

---

## 10. System Health and Maintenance

### Check ACAS System Health
- **Command/Action**: In **SecurityCenter** or **Nessus**, go to **System Status** to view real-time health metrics such as server status, CPU, and memory usage.

### Rebuild Nessus Database
- **Command/Action** (if needed for troubleshooting or performance):
    ```bash
    /opt/nessus/sbin/nessuscli fix --rebuild
    ```

