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
