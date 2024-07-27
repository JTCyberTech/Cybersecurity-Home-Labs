# Network Topology Editing

![image](https://github.com/user-attachments/assets/6bd035e0-1ee9-422c-9fac-15285ef81348)

Since the Domain Controller (NAT) is connected to `two` Switches. We will have to configurate it.

#

# Configurating Domain Controller - Thor

1. Right-click on DC - Thor - 10.0.0.101 > Select Setting

![image](https://github.com/user-attachments/assets/750131ec-755c-4e12-a5bf-65a244f7632e)


2. Go to Network tab

  - For Adapter 1: Change `Attached to:` into `Bridge Adapter`.
  - For Adapter 2: Check "Enable Network Adapter" > Change `Attached to:` into `Internal Network` > Rename into `Internal`.

![image](https://github.com/user-attachments/assets/0292b898-597b-496f-a46e-696fcfc78031)

3. It will look like this in the menu:

![image](https://github.com/user-attachments/assets/55a9e541-f77f-4919-a9f9-789e16f39f7e)

#

# Configurating DHCP - Atlas

Go to Network tab: 

 - For Adapter 1: Change `Attached to:` into `Internal Network`.
 - For Adapter 1: Change `Name:` into `Internal`.

![image](https://github.com/user-attachments/assets/1fce2e0b-2150-4fb4-a4f9-cff5fc4f0b8d)

# 

# Repeat the same thing for FileServer - Zeus

Go to Network tab: 

 - For Adapter 1: Change `Attached to:` into `Internal Network`.
 - For Adapter 1: Change `Name:` into `Internal`.

![image](https://github.com/user-attachments/assets/661a1e4f-daa4-4123-b27b-a9a8e161055b)

#

# Repeat the same thing for Client # 1 ALD101-01

Go to Network tab: 

 - For Adapter 1: Change `Attached to:` into `Internal Network`.
 - For Adapter 1: Change `Name:` into `Internal`.

![image](https://github.com/user-attachments/assets/c9a33381-1346-4a8e-a647-1a1e1c409495)
