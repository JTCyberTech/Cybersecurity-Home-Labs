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

#

# Antivirus & Antimalware Recommendations

## Windows Antivirus Solutions

- **Microsoft Products:**
  - **Windows 7:** Use Microsoft Security Essentials.
  - **Windows 10 & 11:** Use Windows Defender, the default antivirus included with the installation.

  **Note:** Privacy enthusiasts may have concerns about Microsoft's data collection practices. Microsoft products do collect usage data, and this includes their antivirus solutions. Given this, the additional data collected by these antivirus tools might not be a significant concern for users already disclosing information to Microsoft.

## Additional Protection

- **Malware Protection:**
  - **Recommended Tool:** Malwarebytes
    - **Why:** Provides additional protection against malware beyond what is offered by Windows Defender.
    - **Installation:**
      1. Go to [Malwarebytes](http://www.malwarebytes.com/) and select the "Free Download" option.
      2. Perform a default installation.
    - **Usage:**
      - **Weekly Routine:** Launch Malwarebytes weekly, update the database, and conduct a full scan.
      - **Prompt Responses:** Decline any premium features or trials; the free version is sufficient.

## Importance

- **Benefits:**
  - Enhances overall Windows computing experience.
  - Helps maintain system performance and prevent malware infections.
  - Protects the integrity of online investigations by ensuring a clean system.

- **Best Practices:**
  - **"Staples":** These antivirus and antimalware steps are the basic requirements for any computer user.
  - **Host System Usage:** Ideally, avoid using your host operating system for web browsing or investigations to minimize risks. However, having these protections in place is a prudent measure to ensure the integrity of your work.

Always prioritize the security of your system to safeguard your investigations and computing environment.

#

# Managing Microsoft Telemetry

## Overview

Microsoft's Telemetry service collects extensive data from your computer, including:

- **Typed text** on the keyboard
- **Microphone transmissions**
- **Index of all media files** on your computer
- **Webcam data**
- **Browsing history**
- **Search history**
- **Location activity**
- **Health activity** from Health Vault, Microsoft Band, etc.
- **Privacy settings** across Microsoft applications

This data collection can reveal personal details and online activities. Microsoft claims this is to enhance user experience, but many find it invasive.

## Disabling Telemetry

To minimize data collection, follow these steps:

1. **Download O&O ShutUp10:**
   - Visit [O&O Software](https://www.oosoftware.com/en/shutup10) to download the latest version.
   - Install and launch the software.

2. **Configure Settings:**
   - The interface shows options with red (disabled) and green (enabled) icons.
   - **Red** indicates data is sent to Microsoft.
   - **Green** means data collection is blocked.
   - Example: "Sharing of handwriting data disabled" (Red) can be switched to green to block this data.

3. **Choose Privacy Levels:**
   - **"Recommended":** Blocks basic data collection and advertisement IDs.
   - **"Recommended and somewhat recommended":** Blocks more, excluding Windows updates, Defender, and OneDrive.
   - **"Apply all settings":** Blocks all possible data collection.

   My preference is **"Recommended and somewhat recommended"** with **"Microsoft OneDrive Disabled"** to keep updates and Defender active while enhancing privacy.

4. **Apply and Verify:**
   - After selecting settings, reboot your system.
   - Reopen O&O ShutUp10 to verify your settings are applied.
   - Check settings after Windows updates to ensure they remain as configured.

5. **Adjust as Needed:**
   - If issues arise due to privacy settings, you can reverse changes within the application.

By using O&O ShutUp10, you can better manage Microsoft's data collection and protect your privacy.

#

# System Cleaner

## Previous Recommendations
- **Old Recommendation:** CCleaner
  - **Issues:** Unethical practices, adware, and user metrics collection.

## Current Recommendation
- **Preferred Tool:** BleachBit
  - **Website:** [bleachbit.org](https://bleachbit.org)
  - **Features:** Aggressive cleaning similar to CCleaner.
  - **Usage:** Select all options except "Wipe Free Space" to avoid time-consuming operations.
  - **Purpose:** Removes leftover internet history, temporary files, and unwanted data.
  - **Frequency:** Run weekly on Windows or Linux hosts.

# Virtual Private Network (VPN)

## Importance of VPN
- **Function:** Extends a private network across a public network like the internet.
- **Benefits:** Masks your identity online by encrypting traffic and concealing your IP address.
  
## Comparison to Tor
- **Tor:** 
  - **Pros:** Hides entire connection.
  - **Cons:** Slow speeds and potential access issues with services like banks and social networks.
  
- **VPN:** 
  - **Recommendation:** Use for everyday browsing due to better speed and accessibility.

## VPN Recommendations
- **Corporate VPNs:** Not recommended for investigations due to lack of privacy.
- **Paid VPN Services:** Recommended over free VPNs which are often slow and insecure.
  - **Providers:** Proton VPN and Private Internet Access (PIA).
  - **Website for Details:** [Intel Techniques VPN](https://inteltechniques.com/vpn.html)
  
## VPN Usage Tips
- **Preferred Providers:** Proton VPN and PIA.
  - **Proton VPN:** Generally preferred due to fewer blocks.
  - **PIA:** Larger provider but may face blocks.
- **Installation:** Easy for Windows and Mac; protects entire host and virtual machines.
- **Personal Policy:** Always use a VPN on all internet-connected devices.
- **Example Use:** Proton VPN at home for all traffic, switch to PIA when needed to bypass restrictions.

## Conclusion
- **VPN Account Management:** Maintain active accounts with reputable VPNs, paid with Bitcoin for privacy.
- **Affiliate Options:** Current VPN options available on [Intel Techniques VPN](https://inteltechniques.com/vpn.html).

#

# Apple macOS Host

## Why macOS for OSINT?

- **Preference for macOS:** Despite potential criticisms, macOS is preferred over Windows and Linux for OSINT use.
- **Personal Setup:**
  - **Linux Laptop:** Used solely for personal activity.
  - **MacBook Pro:** Utilized for OSINT with M1 Apple Silicon chip, known for speed and superior VM performance.
  - **Third Computer:** Dedicated to breach data work, detailed in Section Three.

## Complete System Wipe

To ensure a clean start, follow these steps to completely wipe and reset your macOS system:

1. **Backup Data:**
   - Backup valuable files from common locations like Desktop, Downloads, and Documents folders.

2. **System Updates:**
   - Ensure your macOS is updated to the latest version (currently Ventura).

3. **Reset Process (for M1):**
   - Open "System Settings" and search for "reset."
   - Select "Transfer or Reset" and click "Erase All Content and Settings."
   - Enter your password, click continue, confirm the erase option, and reboot the device.
   - Connect to Wi-Fi if needed for "Activation Lock."
   - Complete activation (enter account password if prompted).
   - Restart and set up the device:
     - Select language and region.
     - Click "Not Now" in Accessibility and Data and Privacy screens.
     - Confirm choices without enabling Location Services, Screen Time, or Siri.
     - Provide a generic computer name and secure password.
     - Choose desired time zone and settings.

## Installing Security Applications

1. **Rosetta Installation:**
   - Install Rosetta to run applications that do not support ARM-based devices smoothly.
   - Confirm installation with the following command:

   ```bash
   softwareupdate --install-rosetta --agree-to-license 

