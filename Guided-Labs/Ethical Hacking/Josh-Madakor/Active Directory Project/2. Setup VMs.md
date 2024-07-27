# Setup Virtual Machines 

## Following Josh Madakor's Network Topology with Oracle VM VirtualBox

![image](https://github.com/user-attachments/assets/f11db633-36be-4676-9f46-6875122388c7)

#

## Creating Domain Controller: Thor

![image](https://github.com/user-attachments/assets/09216a56-90ff-4f9c-b01f-d6e537b817cd)

1. Click on New on Virtualbox to create a New Virtual machine.

![image](https://github.com/user-attachments/assets/1fd5944e-7f23-41a6-9e47-970c6a560f05)


2. For `Name` on the first VM to be DC - Thor - 10.0.0.101
  - DC = Domain Controller
  - Thor = Name
  - 10.0.0.101 = IP Address

3. For `Type`, select "Microsoft Windows"; `Version`, select "Other Windows (64-bit)"

![image](https://github.com/user-attachments/assets/40321964-f2f7-4f80-b644-0db9d5010fcb)

4. Click on `Hardware`:
  - Make the `Base Memory` to "2 GB" or "2048 MB".
  - Make the `Processors` to "4 CPU"

![image](https://github.com/user-attachments/assets/78676b40-7d04-4df9-ae11-a17bc2d1beeb)

5. Click on `Hard Disk`:
  - Make sure it's 20 GB and click on Finish.


#

## Creating DHCP Server: Atlas

![image](https://github.com/user-attachments/assets/593e377a-3a3b-44cc-bf16-8c13153f1ddc)

1. Click on New on Virtualbox to create a New Virtual machine.

![image](https://github.com/user-attachments/assets/e78ef3dc-021b-4b9b-9f7b-eaa20e9404c2)

2. For `Name` on the second VM to be DHCP - Atlas - 10.0.0.102
  - DHCP = Dynamic Host Configuration Protocol
  - Atlas = Name
  - 10.0.0.102 = IP Address

3. For `Type`, select "Microsoft Windows"; `Version`, select "Other Windows (64-bit)"

![image](https://github.com/user-attachments/assets/3b984580-473b-4fc3-97fa-cead9944af51)

4. Click on `Hardware`:
  - Make the `Base Memory` to "2 GB" or "2048 MB".
  - Make the `Processors` to "4 CPU"

![image](https://github.com/user-attachments/assets/aa7f6123-8011-4883-9d1e-835b25ffaa68)

5. Click on `Hard Disk`:
  - Make sure it's 20 GB and click on Finish.

![image](https://github.com/user-attachments/assets/4aa7f42e-5b53-4534-9bfc-7bca52f4bc21)

#

## Creating File Server: Zeus

![image](https://github.com/user-attachments/assets/eed2b8e9-5a7f-4093-8fd0-04d4f95e382e)

1. Click on New on Virtualbox to create a New Virtual machine.

![image](https://github.com/user-attachments/assets/eea599f0-3b41-43e9-862d-74394712ca6e)

2. For `Name` on the third VM to be FileServer - Zeus - 10.0.0.103
  - FileServer = File Server
  - Zeus = Name
  - 10.0.0.103 = IP Address

3. For `Type`, select "Microsoft Windows"; `Version`, select "Other Windows (64-bit)"

![image](https://github.com/user-attachments/assets/2ded0203-106e-4cbf-8a8a-04907700b74c)

4. Click on `Hardware`:
  - Make the `Base Memory` to "2 GB" or "2048 MB".
  - Make the `Processors` to "4 CPU"

![image](https://github.com/user-attachments/assets/0f5d6f03-48f8-471b-a5ac-c4e4ca9819a7)

5. Click on `Hard Disk`:
  - Make sure it's 20 GB and click on Finish.

![image](https://github.com/user-attachments/assets/2cca65c4-b3a0-4d9a-8a3b-d30ed1911cd1)

#

## Creating Client # 1 - ALD101-01

![image](https://github.com/user-attachments/assets/6d0f1efd-42f7-4af1-989e-4009d6436c04)

1. Click on New on Virtualbox to create a New Virtual machine.

2. For `Name` on the forth VM to be Client - ALD101-01

3. For `Type`, select "Microsoft Windows"; `Version`, select "Windows 10 (64-bit)"

4. Click on `Hardware`:
  - Make the `Base Memory` to "2 GB" or "2048 MB".
  - Make the `Processors` to "4 CPU"

5. Click on `Hard Disk`:
  - Make sure it's 25 GB and click on Finish.
