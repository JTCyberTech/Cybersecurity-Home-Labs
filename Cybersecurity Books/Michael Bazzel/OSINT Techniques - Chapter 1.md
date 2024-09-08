# Chapter 1: Computer Optimization

## Ensuring a Clean Host for Investigations

### Introduction

To ensure the integrity of your investigations, it is crucial that your host machine is free from contamination. This includes checking for:

- **Viruses**
- **Malicious software**
- **Spyware**
- **Tracking cookies from services like Amazon, Facebook, Google, etc.**
- **Evidence of previous investigations in bookmarks, documents, or downloads**

If any of these are present, your computer may be contaminated, which could compromise your case if it goes to court. In such cases, an expert witness could expose your machine's history, and unrelated evidence could jeopardize the investigation.

### Importance of a Clean Host

1. **Digital Contamination:**
   - Every website visit leaves temporary files, session details, and account data on your machine.
   - Persistent cookies from services like Amazon and Google can track your activity across the web, revealing your digital footprint.

2. **Potential Complications:**
   - If you use a contaminated machine for investigations, you risk exposing personal activity during legal proceedings. For example, if an exact clone of your machine is requested, personal data could surface and affect the case outcome.

## Recommended Approach

1. **Dedicated Machine:**
   - Use a dedicated machine solely for online investigations.
   - Avoid any personal usage or unnecessary activity on this machine.

2. **Reformat and Reinstall:**
   - Simply deleting files or running cleaning applications is insufficient.
   - To truly eliminate contamination, you should completely reformat the machine and reinstall all software.

### Recommendations by Operating System

- **Windows**
- **macOS**
- **Linux**

#

# Microsoft Windows Host

## Overview

Many users will have a Windows-based computer for their OSINT (Open Source Intelligence) investigations. While Windows may not be the ideal choice for this work, it is often necessary due to employer requirements or personal preference.

## Windows Versions

- **Windows 10:**
  - Recommended for OSINT work.
  - Supported with updates until October 2025.
  - Offers stability and compatibility for various applications.

- **Windows 11:**
  - Functional for OSINT, but may present additional challenges.
  - Future updates and features might impact its usability for investigations.

## Considerations for Windows Hosts

1. **Version Selection:**
   - Assess which Windows version you have and determine if an upgrade or downgrade is necessary.
   - Windows 10 is currently the preferred version due to its extended support period.

2. **System Wipe (Optional):**
   - A complete system wipe can help ensure a clean environment.
   - Reinstalling Windows may be required to remove all previous data and potential contamination.


#

# Complete System Wipe

## Backup Important Data

1. **Connect External Drive:**
   - Attach a USB external drive to your computer.
   - Copy important documents, configuration files, and media from common locations:
     - Desktop
     - Downloads
     - Documents
   - Ensure all necessary data is backed up before proceeding.

## Reformatting the Machine

### For Windows 10

1. **Access Reset Settings:**
   - Navigate to: `Start` > `Settings` > `Update & Security` > `Recovery`
   - Click the `Get started` button under `Reset this PC`.

2. **Choose Reset Option:**
   - Select `Remove everything`.
   - You will be presented with two options:
     - **Just remove my files**
     - **Remove files and clean the drive**
   - Choose `Remove files and clean the drive` to ensure thorough data removal.

3. **Reinstallation:**
   - If the option to clean the drive is not available, or if you have an older Windows version, use the original installation media or a restore CD.
   - During setup, refuse to create a Microsoft account and use only essential login information.
   - To prevent Microsoft from requesting an online account, disconnect from the internet before beginning the reset process.

4. **Setup Privacy Settings:**
   - Opt for `Customize Settings` during setup.
   - Disable options that collect keystrokes and send usage data to Microsoft.

### For Windows 11

1. **Access Reset Settings:**
   - Navigate to: `Start` > `System Settings` > `Recovery` > `Reset PC`.
   - Select the option to `Remove your files`.

2. **Choose Local Reset:**
   - Opt for the `Local` reset option if available.
   - Follow all confirmation screens and allow the system to restart as needed.

3. **Online Account Requirement:**
   - Windows 11 may require an online account, but disconnecting from the internet can help bypass this requirement.
   - Be aware that future versions of Windows may enforce online accounts more strictly.

By following these steps, you will ensure a fresh and secure operating system free from previous contamination.
