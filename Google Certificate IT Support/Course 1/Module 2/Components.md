# CPU

- **Calculating and CPU**
  - Calculating complex math or binary by hand is tedious; we use calculators.
  - The CPU (central processing unit) in computers processes binary calculations.
  - The CPU uses an instruction set to perform functions on data.

- **Instruction Set**
  - An instruction set is a list of instructions the CPU can execute (e.g., add, subtract, copy data).
  - Programs are broken down into simple instructions found in the instruction set.
  - Instruction sets are hard-coded into CPUs and may vary between manufacturers but generally perform the same functions.

- **CPU Manufacturers and Models**
  - Popular CPU manufacturers include Intel, AMD, Qualcomm, and Apple.
  - Examples of CPU models: Intel Core i7, AMD Athlon, Snapdragon 810, Apple A8.
  - Each manufacturer has strengths and weaknesses.

- **CPU and Motherboard Compatibility**
  - CPUs must be compatible with the motherboard.
  - Different CPUs fit into motherboards using different sockets (e.g., Land Grid Array (LGA) and Pin Grid Array (PGA)).
  - Ensure CPU and motherboard sockets match by checking the box or the manufacturer's website.

- **Installing a CPU**
  - CPUs need cooling mechanisms to prevent overheating.
  - A heat sink is used to dissipate heat from the CPU through a fan or another medium.

- **32-bit and 64-bit Architecture**
  - CPUs are specified as 32-bit or 64-bit, indicating how much data they can efficiently handle.
  - 32-bit and 64-bit refer to the number of bits the CPU can process.
  - Compatibility and performance with other components are crucial for optimal CPU function.

#

# RAM

- **RAM Overview**
  - RAM (Random Access Memory) is the computer's short-term memory.
  - Used to store data for quick access, but data is not permanent.
  - Most RAM is volatile, meaning data is cleared when power is off.

- **Function and Importance**
  - Programs are copied into RAM for the CPU to process.
  - More RAM allows running multiple programs simultaneously.
  - Loss of power results in loss of unsaved work stored in RAM.

- **Types of RAM**
  - **DRAM (Dynamic Random Access Memory)**
    - Stores bits in microscopic capacitors, represented by charged or discharged states.
    - Commonly used in computers.
  - **DIMM (Dual Inline Memory Module)**
    - Modern memory sticks with different sizes of pins.
  - **SDRAM (Synchronous DRAM)**
    - Synchronized to the system's clock speed for quicker data processing.
  - **DDR SDRAM (Double Data Rate SDRAM)**
    - Faster, uses less power, and has a larger capacity.
    - Iterations: DDR1, DDR2, DDR3, DDR4.
    - DDR4 is the fastest type of short-term memory currently available.

- **Compatibility**
  - Ensure RAM sticks are compatible with the motherboard.
  - Different types and iterations of RAM have different pin configurations.

- **Key Points**
  - More RAM enables faster program execution and multitasking.
  - RAM compatibility with the motherboard is essential for proper function.

#

# Motherboard

- **Motherboard Overview**
  - Foundation that holds the computer together.
  - Allows expansion of functionality through expansion cards.
  - Routes power from the power supply.
  - Facilitates communication between different computer parts.

- **Key Characteristics**
  - **Chipset**
    - Determines how components communicate.
    - Made up of two chips: Northbridge and Southbridge.
      - **Northbridge:** Interconnects RAM and video cards.
      - **Southbridge:** Manages input-output controllers like hard drives and USB devices.
    - In some modern CPUs, the Northbridge is integrated into the CPU.
  - **Expansion Slots**
    - Allow the addition of expansion cards to increase functionality.
    - **PCI Express (PCIe):** Standard for expansion buses, looks like a slot on the motherboard, and the expansion card looks like a small circuit board.
  - **Form Factor**
    - Determines the size and capacity of the motherboard.
    - Most common form factor: **ATX (Advanced Technology Extended)**
      - Available in different sizes, commonly full-sized ATX in desktops.
    - Smaller alternative: **ITX (Information Technology Extended)**
      - Includes sizes like mini ITX, nano ITX, and pico ITX.
      - Example: Intel NUC uses variations of the ITX board.
    - Choice of form factor affects workload capacity and expansion slot availability.

- **Considerations for Building a Computer**
  - Decide on the form factor based on desired workload capacity and functionality.
  - Ensure compatibility with components like RAM modules and processor sockets.

- **Practical Application**
  - Understanding motherboards helps in fixing hardware issues.
  - Compatibility checks are essential when replacing components like graphics cards to avoid mismatches.

#

# Physical Storage: Hard Drives

- **Understanding Data Sizes**
  - **Bit**: Smallest unit of data storage, can store a 1 or 0.
  - **Byte**: Comprised of 8 bits, can hold a letter, number, or symbol.
  - **Kilobyte (KB)**: 1,024 bytes.
  - **Example**: 500 gigabytes can store approximately 165,000 music files (average music file is 3 MB).

- **Computer Storage**
  - Stores data on hard drives (programs, music, pictures, etc.).
  - **Data Backup**: Essential to avoid data loss in case of hard drive failure.

- **Hard Drive Types**
  - **Hard Disk Drives (HDDs)**
    - Uses a spinning platter and mechanical arm to read/write data.
    - **RPM (Revolutions Per Minute)**: Higher RPM means faster read/write speed.
    - Prone to damage due to moving parts.
  - **Solid State Drives (SSDs)**
    - No moving parts, stores data on microchips.
    - Faster data transfer than HDDs.
    - Slimmer form factor.
    - More expensive than HDDs but less prone to data loss.
  - **Hybrid Drives**
    - Combine SSD performance for system tasks with HDD for basic file storage.

- **Hard Drive Interfaces**
  - **ATA Interfaces**: Most common for connecting hard drives to systems.
  - **Serial ATA (SATA)**
    - Uses one cable for data transfer.
    - **Hot Swappable**: Can plug in without turning off the machine.
    - Efficient and fast data transfer for HDDs.
  - **NVMe (NVM Express)**
    - Designed for fast SSDs.
    - Uses an expansion slot instead of a cable for greater data throughput and efficiency.

#

# Power Supplies 

- **Powering the Computer**
  - **Power Supply**: Converts electricity from the wall to usable power for the computer.
  - **Types of Electricity**
    - **DC (Direct Current)**: Flows in one direction.
    - **AC (Alternating Current)**: Changes direction constantly.
  - Computers use DC voltage; power supply converts AC to low voltage DC.

- **Power Supply Components**
  - **Fan**: For cooling.
  - **Voltage Information**: Listed on the unit.
  - **Cables**: To power the motherboard and other components.

- **Understanding Electricity with Water Pipes Analogy**
  - **Voltage**: Pressure of electricity (like water pressure).
    - High voltage: More electricity flow.
    - Example: Plugging a 120V appliance into a 220V outlet can fry the device.
  - **Current (Amperage)**: Amount of electricity flowing, measured in amps.
    - Amps pull electricity as needed.
    - Example: A 2.1A charger charges faster than a 1A charger.
  - **Wattage**: Combination of volts and amps.
    - Determines how much power the device needs.
    - Ensure your power supply has sufficient wattage for your computer's needs.
    - Example: Basic desktops can be powered with a 500W power supply; high-demand tasks need more power.

- **Choosing the Right Power Supply**
  - Err on the side of larger power supplies to ensure adequate power.
  - Power supplies only give the amount of power your system needs.
  - Consider your computer’s usage (basic tasks vs. high-demand tasks).

- **Issues with Power Supplies**
  - Can cause the computer not to turn on.
  - Can fail due to burnouts, power surges, lightning strikes, etc.
  - Diagnosing and replacing a failed power supply is a key skill for IT support specialists.

#

# Mobile Devices

- **Introduction to Mobile Devices:**
  - Mobile devices are akin to computers with CPUs, RAM, storage, power systems, and peripherals.
  - They are distinct for their mobility, powered by batteries, and can be general-purpose (like tablets and smartphones) or task-specific (like fitness monitors and e-readers).

- **Integration and Components:**
  - Mobile devices integrate components tightly; smaller devices tend to have more integrated components.
  - CPUs, RAM, and storage are often soldered directly onto the motherboard or packed into a single System on a Chip (SoC) for efficiency and battery savings.

- **Peripheral Usage:**
  - Despite their size, mobile devices use peripherals like Bluetooth headphones or act as peripherals themselves (e.g., fitness trackers syncing with smartphones).
  - Custom ports and connectors are common to accommodate device size and use cases (e.g., waterproof connectors).

- **Connectivity and Standards:**
  - Standard ports include USB-C, Lightning, mini USB, micro-USB, micro HDMI, mini HDMI, and mini DisplayPort, each suited to different mobile device needs.

- **Operating Systems and Applications:**
  - Mobile devices run specialized OS and apps optimized for performance due to their size and power limitations.

- **Role in IT Support:**
  - IT support specialists handle mobile devices, including setup, troubleshooting, repair, and replacement, adhering to privacy policies, especially in BYOD (Bring Your Own Device) environments.

# 

# Batteries and Charging Systems

- **Mobile Device Power and Batteries:**
  - Mobile technology utilizes rechargeable batteries for portability.
  - Devices may use external chargers, cradle stands, or wireless chargers for recharging.
  - Rechargeable batteries have a limited lifespan measured in charge cycles.
  - As batteries age, they may take longer to charge and hold less charge.
  - External power sources (e.g., wall outlets, batteries, solar panels) are needed to charge batteries.
  - Charging circuits manage power transfer from external sources to rechargeable batteries.
  - Correct chargers and adapters must be used to avoid damaging batteries, devices, or chargers.
  - Temperature extremes (very cold or hot environments) can damage rechargeable batteries.
  - Damaged batteries can swell, rupture, or pose fire hazards, requiring careful handling.
  - Some devices adjust performance to prolong battery life as batteries age.
  - IT support specialists may need training to replace batteries in various devices.
  - Troubleshooting battery life and charging issues is a common task for IT support.
  - Educating end-users on optimizing battery life for iOS and Android devices is important.

#

# Peripherals and Ports 

- **Peripheral Devices and Connectors:**
  - **Peripherals Overview:**
    - Peripherals are external devices that add functionality to a computer.
    - Common peripherals include mice, keyboards, and monitors.
  - **USB (Universal Serial Bus) Devices:**
    - USB is a popular connection standard for gadgets.
    - Versions include USB 2.0, USB 3.0, and USB 3.1, each with different transfer speeds.
    - Transfer speed is measured in megabits per second (Mb/s), not megabytes (MB).
    - Compatibility: USB ports are backward compatible (older devices work with newer ports).
    - Ports Identification: USB 2.0 (black), USB 3.0 (blue), USB 3.1 (teal, may vary by manufacturer).
  - **USB Connectors:**
    - USB Type C is a modern connector replacing many peripheral connections.
    - It supports data transfer, power delivery, and is becoming a universal standard.
  - **Display Peripherals:**
    - Common interface standards include HDMI and DisplayPort.
    - HDMI supports both audio and video, widely used in TVs and computers.
    - DisplayPort also supports audio and video, gaining popularity among manufacturers.
  - **IT Support Specialist Role:**
    - IT specialists frequently work with USB and display peripherals.
    - Understanding connector types helps in troubleshooting and setup.
