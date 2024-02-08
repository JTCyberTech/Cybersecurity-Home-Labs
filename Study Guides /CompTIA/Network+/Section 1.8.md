# Cloud Models

## IaaS

Infrastructure as a Service 
- Sometimes called Hardware as a Service (HaaS)
- Outsource yout equipment
- Still responisble for the management and security of the data
- Your data is out therem but more wihin your control
- Web servers

#

## SaaS

Software as a Service
- On-demand software
- No local installation
- Why manage your own email distribution or payroll

Central management of data and applications
- Your data is out there
- Complete application offering: no development work required.
- Google Mail

#

## PaaS

Platform as a service
- no server, no software no maintence team, HVAC.
- someone lese handles the plaform, you handle the development

You don't have direct control of the data, people or infrastructue
- Trained security professionals are watching your data
- Choose carefully

Put the building blocks together
- Develop your application from what is available on the platform
- SalesForce.com

![image](https://github.com/jefftsui1/Cybersecurity-Home-Labs/assets/46698661/00edd87a-2594-4a26-a3bc-ad9009dd3396)

#

## Cloud Deployment Models

Public:
- Available to everyone over the Internet

Community:
- Several organizations share the same resouces

Private:
- You own virtualized local data center

Hybrid:
- Mix of public and private

#

## Desktop as a Service

Basic application usage
- Application actually run on a remote server
- Virtual Desktop Infrastructure (VDI), DaaS
- Local device is a keyboard, mouse, screen

Minimal OS on the client
- no huge memory or CPU needs

Network Connectivity
- Big network requirement
- Everythinh happens across the wire

#

## Designing the Cloud

Elasticity
- Scale up or down as needed

Scalability
- Access from anywhere for large implementations

Multitenancy
- Many different clients are using the same cloud infrastructure

#

## Infrastructure as Code

Describe an infrastructure
- Define servers, network and application as code

Modify the infrastructure and create versions
- Same way you version application code

Use the description code to build other application instances
- Build it the same way every time based on the code

An important concept for cloud computing
- Build a perfect version every time

#

## Orchestration

Automation is key to cloud computing
- Services appear and disappear automatically or at the push of a button.

Entire application instances can be instantly provisioned 
- All servers, networks, switches, firewalls, policies

Instance can move around the world as needed
- Follow the sun; build when people are awake, tear down when people is asleep/ not using.

The security policies should be part of the orchestration
- As application are provisioned, the proper security is automatically included

#

## Connecting to the Cloud

VPN
- Site to site virtual private network
- Encryption thru the internet

Virtual Private Cloud Gateway
- Connects users on the internet

VPC Endpoint
- Direct connection between cloud provider network

#

## VM Sprawl Avoidance

Virtual machines are sprawled everywhere
- You aren't sure which VMs are related to which applications
- becomes extremely difficult to deprovision

Should have a formal process and detailed documentation from the beginning.
- You should have information on every virtual object

#

## VM escape Protection

Virtual machine is self contained
- Once you escape VM. you have great control of the host and other guest VMs.

Would be Huge Exploit
- Full control of the virtual world.
