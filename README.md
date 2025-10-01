# Raya-RPA-Assessment-Task

---

## 1. Project Overview

This repository contains a complete UiPath RPA solution for the "Verify Account Positions" process, split into two main projects:

- **Dispatcher**: Extracts work items from the ACME web application and uploads them to Orchestrator queues.
- **Performer**: Processes the queued work items, automating both web and desktop interactions to verify account positions in ACME systems.

The solution is built on the UiPath Robotic Enterprise Framework (REFramework) for robust exception handling, logging, and scalability. It is designed for unattended execution on cloud-hosted virtual machines via UiPath Orchestrator.

---

## 2. Recordings & Images

All demonstration recordings and screenshots are located in the `Recordings` folder at the root of this repository. Preview below:

<p align="center">
	<img src="Recordings/Dispatcher%20Recording.gif" alt="Dispatcher Recording" width="350" />
	<img src="Recordings/1.png" alt="Screenshot 1" width="350" />
</p>

<p align="center">
	<img src="Recordings/2.png" alt="Screenshot 2" width="350" />
	<img src="Recordings/3.png" alt="Screenshot 3" width="350" />
</p>

> You can preview these files for a visual walkthrough of the automation process.

---

## 3. Project Structures

### Dispatcher Structure

**Main Folders & Files:**

| Folder/File | Description |
|-------------|-------------|
| ACMEWeb/ | Web automation workflows (login, navigation, extraction) |
| Common/ | Shared components (Control, Email) |
| Data/ | Config, input, output, and temp data |
| Dispatcher/ | Dispatcher-specific workflows |
| Documentation/ | Project documentation |
| Exceptions_Screenshots/ | Screenshots on exceptions |
| Framework/ | REFramework core workflows |
| Tests/ | Test cases and templates |
| Main.xaml | Main entry workflow |
| project.json | Project metadata and dependencies |

**ACMEWeb Navigation Table:**

| Workflow | Purpose |
|----------|---------|
| ACMEWeb_ExtractWorkItems.xaml | Extracts work items from ACME web |
| ACMEWeb_InitializeApp.xaml | Initializes the ACME web app |
| ACMEWeb_Login.xaml | Handles login to ACME web |
| ACMEWeb_NavigateWorkItems.xaml | Navigates to work items page |

**Framework Components:**

| Workflow | Purpose |
|----------|---------|
| CloseAllApplications.xaml | Closes all apps |
| ExtractAndUploadQueueItems.xaml | Uploads items to Orchestrator queue |
| InitAllApplications.xaml | Initializes all apps |
| InitAllSettings.xaml | Loads config/settings |
| KillAllProcesses.xaml | Kills processes |
| RetryCurrentTransaction.xaml | Handles transaction retries |
| SetTransactionStatus.xaml | Updates transaction status |
| TakeScreenshot.xaml | Takes screenshots on error |

### Performer Structure

**Main Folders & Files:**

| Folder/File | Description |
|-------------|-------------|
| ACMEDesktop/ | Desktop automation workflows (login, navigation, processing) |
| ACMEWeb/ | Web automation for updating work items |
| Common/ | Shared components (Control, Email) |
| Data/ | Config, input, output, and temp data |
| Documentation/ | Project documentation |
| Email/ | Email notification workflows |
| Exceptions_Screenshots/ | Screenshots on exceptions |
| Framework/ | REFramework core workflows |
| Tests/ | Test cases and templates |
| Main.xaml | Main entry workflow |
| project.json | Project metadata and dependencies |

**ACMEDesktop Navigation Table:**

| Workflow | Purpose |
|----------|---------|
| ACMEDesktop_InitializeApp.xaml | Initializes ACME desktop app |
| ACMEDesktop_Login.xaml | Handles login to ACME desktop |
| ACMEDesktop_NavigateToAccountTransactions.xaml | Navigates to account transactions |
| ACMEDesktop_NavigateToClientAccounts.xaml | Navigates to client accounts |
| ACMEDesktop_NavigateToClientDetails.xaml | Navigates to client details |
| ACMEDesktop_NavigateToClientSearch.xaml | Navigates to client search |
| ACMEDesktop_SumAccountTransactions.xaml | Sums account transactions |

**ACMEWeb Navigation Table:**

| Workflow | Purpose |
|----------|---------|
| ACMEWeb_ExtractWorkItemData.xaml | Extracts work item data |
| ACMEWeb_InitializeApp.xaml | Initializes ACME web app |
| ACMEWeb_Login.xaml | Handles login to ACME web |
| ACMEWeb_NavigateToUpdateWorkItem.xaml | Navigates to update work item |
| ACMEWeb_NavigateWorkItems.xaml | Navigates to work items page |
| ACMEWeb_UpdateWorkItem.xaml | Updates work item status |

---

## 4. Key Features & Functions

- End-to-end automation of the "Verify Account Positions" process using UiPath REFramework
- Dispatcher extracts work items from ACME web and uploads to Orchestrator queue
- Performer processes queue items, automating both web and desktop ACME systems
- Robust exception handling and logging (screenshots on error)
- Modular workflows for easy maintenance and scalability
- Designed for unattended execution on cloud VMs via Orchestrator
- Test cases and templates included for validation

---

## 5. Assets Used (Dispatcher & Performer)

Both projects use the following assets (to be configured in UiPath Orchestrator):

| Asset Name            | Type         | Purpose                                 |
|----------------------|--------------|-----------------------------------------|
| ACME_Credentials     | Credential   | Login credentials for ACME systems      |
| OrchestratorQueueName| Text/Queue   | Name of the queue for work items        |
| Config.xlsx          | File         | Centralized configuration for workflows |

> _Add or update assets as needed for your environment._

---

## 6. Cloud Orchestrator & Unattended VMs

This solution is published to UiPath Cloud Orchestrator and configured to run on unattended virtual machines. This enables fully automated, scheduled, and scalable execution without human intervention.

---

## 7. Required Configuration

Before running the process, ensure the following prerequisites are met:

1. **Microsoft Edge browser** is installed
2. **UiPath extension for Edge** is activated (including for private windows)
3. **ACME System 3** is installed and accessible

---

## 8. Packages Used

Both Dispatcher and Performer use the following UiPath packages:

| Package Name                  | Version    |
|-------------------------------|------------|
| UiPath.Excel.Activities       | 3.2.1      |
| UiPath.Mail.Activities        | 2.4.10     |
| UiPath.System.Activities      | 25.10.0    |
| UiPath.Testing.Activities     | 25.10.0    |
| UiPath.UIAutomation.Activities| 25.10.16   |

---

## 9. Workflow Whiteboard Images

> _Add images of your workflow whiteboards for Dispatcher and Performer here._

---