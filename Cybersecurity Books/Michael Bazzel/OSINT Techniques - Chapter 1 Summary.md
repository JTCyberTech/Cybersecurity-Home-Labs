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

#

# Antivirus & Antimalware for Mac Users

## Overview

- **Mac Security:**
  - Mac computers generally do not require built-in antivirus protection due to their secure software architecture.
  - While viruses are rare on Macs, they can still occur.

- **Commercial Antivirus Products:**
  - Free commercial antivirus products such as Avast and Kaspersky are not recommended.
  - These products can be more annoying than helpful and may have questionable business practices.

- **Importance of Protection:**
  - Despite the low incidence of viruses, it is irresponsible to have no protection at all.
  - During a federal trial testimony, having security software was crucial to avoid defense arguments about an infected workspace.
  - Open-source solutions are preferable for such scenarios.

## Recommended Approach

1. **Open-Source Security Applications:**
   - For Mac investigations, it's advised to have three security applications available for on-demand use, rather than running full-time.

2. **Installing Homebrew:**
   - **Homebrew (Brew):** A package manager for macOS that simplifies the installation of software.
   - **Installation Command:**
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```
   - Follow the on-screen instructions to complete the installation.

3. **Using Homebrew:**
   - Once Homebrew is installed, it can be used to install the recommended security applications.

This setup ensures that you have reliable tools available for investigation while maintaining a minimal footprint on your system's performance.

#

# Mac Security Tools

## Task Explorer

- **Description**: Task Explorer is a free Mac-only application that identifies all running processes and checks them through Virus Total. It alerts you to potential threats with a red flag.
- **Usage**: Run weekly to quickly identify viruses or suspicious files on your Mac. Note that it does not remove infections; further research is required for removal.
- **Installation**:
  ```bash
  brew install --cask taskexplorer

#

## KnockKnock

- **Description**: KnockKnock is a Mac application that scans for persistent programs set to launch automatically upon boot. It is useful for detecting malware that might inject itself into startup processes.
- **Usage**: Run KnockKnock weekly alongside Task Explorer to identify any persistent threats. The application will notify you about suspicious files but does not remove them.
- **Installation**:
  ```bash
  brew install --cask knockknock

#

## ClamAV

- **Description**: ClamAV is an open-source antivirus software for macOS. It is community-driven and free to use. It is not a real-time antivirus but performs scans when manually executed. It primarily identifies suspicious files and does not remove them by default.

- **Installation**:
  1. **Install ClamAV** using Homebrew:
     ```bash
     brew install clamav
     ```
  2. **Create necessary directories and adjust permissions**:
     ```bash
     sudo mkdir /usr/local/sbin
     sudo chown -R $(whoami):admin /usr/local/sbin
     ```
  3. **Link ClamAV**:
     ```bash
     brew link clamav
     ```
  4. **Configure ClamAV**:
     ```bash
     cd /opt/homebrew/etc/clamav/
     cp freshclam.conf.sample freshclam.conf
     sed -i 's/AExample/#Example/g' freshclam.conf
     ```

- **Usage**:
  1. **Update the antivirus database**:
     ```bash
     freshclam -v
     ```
  2. **Perform a scan**:
     ```bash
     clamscan -r -i /
     ```
     - The `freshclam -v` command updates the virus definitions.
     - The `clamscan -r -i /` command scans the entire system and reports any viruses found.
  3. **Remove suspicious files** (use with caution):
     ```bash
     clamscan -i -r --remove=yes /
     ```
     - This command will automatically remove files identified as malicious. Use it only if you are confident that the files are safe to delete.

- **Notes**:
  - ClamAV may occasionally report false positives. Research suspicious files online if detected.
  - Regular use of ClamAV is recommended for government investigations or environments requiring additional security.
  - ClamAV is not often used but can complement Task Explorer and KnockKnock by identifying threats not detected by them.

#

# Telemetry on Apple Computers

## Overview

Apple computers, like Windows machines, collect and send substantial amounts of telemetry data. While Apple claims this is to enhance user experience, it raises privacy concerns, especially for those conducting OSINT (Open Source Intelligence) investigations.

## Protection Options

1. **Software Firewall Applications:**
   - **Little Snitch:** A paid program that can block and monitor outbound connections.
   - **LuLu:** A free alternative that might offer similar protection.

2. **Need for Protection:**
   - For OSINT investigations, where you are not conducting research directly on macOS but using virtual machines (VMs), telemetry protection might not be critical. 
   - However, using a firewall can still be beneficial for added privacy.

## Resources

- For detailed guidance on minimizing macOS telemetry with Little Snitch, refer to the following blog posts:
  - [Minimizing macOS Telemetry](https://inteltechniques.com/blog/2021/08/03/minimizing-macos-telemetry/)
  - [macOS Telemetry Update](https://inteltechniques.com/blog/2021/08/18/macos-telemetry-update/)

## Conclusion

If you conduct investigations directly on macOS, enabling strong telemetry protection through a firewall is recommended. If you use virtual machines for investigations, it may be less critical but still worth considering.

#

# System Cleaner, VPN, and Password Manager for macOS

## System Cleaner

- **BleachBit:** Although BleachBit technically supports macOS, it is not well-maintained and may not function properly.
- **Alternative Solution:** Use Privacy.sexy to create a custom script for cleaning your macOS system. 
  - **Steps:**
    1. Visit [Privacy.sexy](https://privacy.sexy).
    2. Select the "macOS" option.
    3. Navigate through the privacy and security categories to choose the cleaning options.
    4. The script commands will populate on the right side.
    5. Click "Download" to generate and download the script.
    6. Follow the instructions to execute the script.
  - **Note:** Start with minimal modifications and research any unfamiliar options. The options may change frequently, so updates to the script are not guaranteed.

## Virtual Private Network (VPN)

- **VPN Application:** Similar to Windows, use a VPN application on your macOS OSINT host machine.
  - **Recommended VPNs:**
    - **Proton VPN:** Provides protection for your home network and macOS host.
    - **PIA Dedicated IP VPN:** Use when accessing blocked websites and return to Proton VPN as needed.
  - For more details, visit [Intel Techniques VPN page](https://inteltechniques.com/vpn.html).

## Password Manager

- **KeePassXC:** Recommended for macOS machines, KeePassXC functions similarly across all operating systems and allows sharing of password databases across platforms.
- **Note:** Ensure your macOS machine is prepared for OSINT investigations.
  - **Example Result:** Figure 1.01 displays the result after a KnockKnock scan.


#

# Linux Host Recommendations

## Complete System Wipe

For a fresh installation of Linux:

1. **Avoid Embedded Reset Functions:**
   - Most Linux systems have a built-in reset function, but it is not recommended for a complete reinstall.

2. **Use Ventoy:**
   - **Ventoy** is a tool that allows you to create a bootable USB drive with multiple Linux ISO files.
   - **How to Use:**
     - Place various Linux ISO files at the root of the USB drive.
     - Boot from the USB drive and select the OS you wish to install.
   - For a full explanation of Ventoy, refer to issue 004 of UNREDCATED magazine: [UNREDCATED Issue 004](https://unredactedmagazine.com/issues/004.pdf).

3. **Recommended OS:**
   - **Ubuntu 22.04** is suggested for installation.

4. **Reinstalling the OS:**
   - Follow the tutorial in the next chapter to reinstall a fresh copy of Ubuntu 22.04.

## Antivirus & Antimalware

1. **ClamAV Installation:**
   - **Purpose:** ClamAV helps in "checking the boxes" for a secure machine and detecting viruses that may target Windows systems.
   - **Installation Commands:**
     ```bash
     sudo apt update
     sudo apt install -y clamav clamav-daemon
     ```

2. **Updating Antivirus Database and Scanning:**
   - **Update Commands:**
     ```bash
     sudo systemctl stop clamav-freshclam
     sudo freshclam
     sudo systemctl start clamav-freshclam
     ```
   - **Scanning Commands:**
     - Scan without removing files:
       ```bash
       clamscan -r -i /
       ```
     - Scan and remove infected files:
       ```bash
       clamscan -r -i --remove=yes /
       ```

3. **Handling False Positives:**
   - ClamAV may report false positives.
   - **Action:** Research any reported files online and delete any malicious files found in email.

By following these steps, you can ensure your Linux host is clean and secure for OSINT investigations.

#

# Linux System Maintenance and Security

## Telemetry

- **Ubuntu 22.04 Telemetry:**
  - Ubuntu collects minimal telemetry data and allows easy prevention of data transmission.
  - To disable telemetry (if not already done during installation), use the following commands:

    ```bash
    sudo apt purge -y apport apport-symptoms popularity-contest ubuntu-report whoopsie
    sudo apt autoremove -y
    ```

## System Cleaner

- **BleachBit:**
  - Recommended for weekly system cleaning.
  - Install BleachBit with:

    ```bash
    sudo apt install bleachbit
    ```

  - Launch BleachBit with administrative privileges.
  - Upon first launch, click "Close" to accept default settings.
  - Select all options except "Free disk space."
  - Click "Preview" to review cleaning recommendations and "Clean" to execute.

## Virtual Private Network (VPN)

- **VPN Usage:**
  - Install a VPN application on your Linux OSINT host machine.
  - **Proton VPN** is recommended for home network protection.
  - **PIA dedicated IP VPN** can be used if Proton VPN is blocked or unavailable.
  - More details can be found at [IntelTechniques VPN](https://inteltechniques.com/vpn.html).

## Password Manager

- **KeePassXC:**
  - Recommended for managing passwords on Linux.
  - Functions consistently across all operating systems and supports database sharing across platforms.


