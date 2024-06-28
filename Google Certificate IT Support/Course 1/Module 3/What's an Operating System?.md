# Components of an Operating System

- An operating system (OS) manages computer resources and user interaction.
- It consists of the kernel (core, manages hardware and resources) and user space (everything outside the kernel).
- Major OSs include Windows (Microsoft), macOS (Apple), and Linux (open source).
- Linux kernel developed by Linus Torvalds, with various distributions like Ubuntu, Debian, and Red Hat.
- Chrome OS and Android OS run on the Linux kernel.
- OSs handle file storage, managed by file systems (folders, directories).
- Kernel manages processes (task scheduling, resource allocation), memory, and IO (device communication).
- User space includes programs (text editors, music players) and interfaces users interact with directly.

#

# Files and File Systems

- **File Management Overview:**
  - **File Storage Challenge:**
    - Computers can store hundreds of thousands of files.
    - Keeping track of these files is crucial.

- **Kernel's Role:**
  - Handles file storage and file systems.

- **Components of File Handling:**
  - **File Data**
  - **Metadata**
  - **File System**

- **File System:**
  - **New Hard Disks:**
    - Must be erased and configured for the operating system to read and write data.
  - **Types of File Systems:**
    - Different file systems have different capabilities (storage size, speed, resiliency).
    - Major OS file systems:
      - **Windows:**
        - **NTFS**: Features encryption, faster access, security.
        - **ReFS**: In development.
      - **Linux:**
        - **EXT4**: Standard, compatible with older EXT systems.
  - **File System Compatibility:**
    - Different file systems may not be compatible with each other.
    - Use the recommended file system for your operating system.

- **Storage of Actual File Data:**
  - **Data Blocks:**
    - Data is written in blocks, not always in one piece.
    - Improves handling speed and storage space utilization.

- **Metadata:**
  - **Information Stored:**
    - Creator, last modified date, access permissions, file type.
  - **File Extensions:**
    - Appended to filenames to indicate file type (e.g., `.jpg` for images).

- **Practical Application:**
  - Knowledge of file systems is valuable for IT support:
    - Data recovery from damaged disks.
    - Booting multiple operating systems on the same computer.

#

# Process Management

- **Process Management**: A key task of the kernel.
- **Process vs. Program**:
  - A process is a running instance of a program (e.g., multiple Chrome windows).
  - A program is an application that can be executed (e.g., Chrome).
- **Resource Allocation**:
  - Processes require resources like RAM and CPU.
  - The kernel manages these finite resources efficiently to run multiple programs simultaneously.
- **Time Slicing**:
  - The CPU uses time slices (short intervals) to execute processes sequentially, giving the illusion of simultaneous execution.
- **Performance Issues**:
  - High CPU usage can result from one process taking too many time slices or too many processes demanding CPU time.
- **Process Scheduling and Termination**:
  - The kernel schedules processes and reallocates resources after processes terminate to ensure efficient system performance.

#

# Memory Management and Virtual Memory

- **Memory Needs for Processes**:
  - Processes require CPU time and memory (RAM) to run.
  - Memory is limited compared to hard disk drives.

- **Virtual Memory**:
  - Combines hard drive space and RAM to act as memory for processes.
  - Data from programs is divided into chunks called pages, stored in virtual memory.
  - Pages are moved to RAM for execution when needed.

- **Efficient Memory Use**:
  - Entire programs aren't stored in RAM to avoid waste.
  - Only necessary parts of programs are loaded into RAM, improving efficiency.
  - Example: A word processor may slow down when accessing a rarely used menu because it needs to load the relevant page from virtual memory.

- **Swap Space**:
  - Allocated hard drive space for virtual memory storage.
 
#

#  I/O Management

- **Kernel Responsibilities**:
  - Manages files, file storage, processes, memory, and input/output (I/O).

- **I/O Devices**:
  - Include monitors, keyboards, mice, hard drives, speakers, Bluetooth headsets, webcams, and network adapters.
  - Managed by the kernel through device drivers.

- **I/O Management**:
  - Kernel loads drivers to communicate with hardware.
  - Manages data transfer between devices and ensures efficient, error-free communication.

- **Troubleshooting Performance Issues**:
  - Common problems include insufficient RAM, CPU, or I/O bottlenecks.
  - Identifying the source of slowness helps resolve latency issues.
  - Troubleshooting is crucial in IT support roles, impacting both desktop and server performance.

#

# Interacting With the OS: User Space

- **User Interaction with OS**:
  - Users interact with the OS through the userspace.
  - Common actions: creating files/folders, opening applications, deleting items.

- **Interaction Methods**:
  - **Shell**:
    - Command Line Interface (CLI) shell uses text commands.
    - Shell interprets commands and sends them to the OS for execution.
    - Essential for Linux and IT support, especially for remote access.
    - Common shell: Bash (Bourne Again Shell).

  - **Graphical User Interface (GUI)**:
    - Visual interaction using mouse clicks and drag actions.
    - Examples: opening folders, navigating menus.
    - Commonly used in everyday tasks (e.g., opening a web browser).
    - Recognizable in various devices like computers, mobile phones, ATMs, and kiosks.

- **Importance of Shell**:
  - Vital for IT support roles and advanced tasks.
  - Necessary for managing multiple machines efficiently.
  - Some tasks can only be completed through CLI commands.

#

# Logs

- **Scenario**: Imagine a video game console shutting off repeatedly at a crucial moment.
- **Logs**: 
  - Computers record system events like a diary, known as logs.
  - Logs capture events like system startups, driver loads, and errors.
- **Importance**: 
  - Logs help diagnose and troubleshoot issues by providing detailed records.
  - Navigating logs can be challenging but essential for problem-solving.

#

# Boot Process

- **Purpose**: Understanding the steps of starting an operating system (OS) is crucial for diagnosing startup issues.
- **Steps in Booting a Computer**:
  1. **Power On**: The computer is powered on.
  2. **BIOS/UEFI Initialization**: Low-level software initializes hardware.
  3. **POST**: Power-On Self-Test performs diagnostic tests.
  4. **Boot Device Selection**: BIOS/UEFI selects a boot device based on the configured order.
  5. **Bootloader Execution**: A small program called the bootloader loads the OS.
  6. **Kernel Loading**: The kernel is loaded, controlling resource access and loading drivers.
  7. **System Processes and User Space**: Essential processes and user space items are launched, enabling user interaction.

- **Outcome**: After these steps, the computer is ready for use.
