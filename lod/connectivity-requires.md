# Connectivity Requirements

To launch and use a lab, the following requirements must be met:

1. Use a supported operating system:
    1. Windows 7 or later
    2. Ubuntu 14.04 or later (or comparable distribution)
    3. macOS 10.12 or later
2. Have a supported browser. IE, Edge, Chrome, Firefox, Safari.
    1. Latest version is preferred, but full support details can be found below
    2. Chromium based browsers such as Opera or Vivaldi can connect, but default hotkeys they set may interfere with lab inputs
3. Be connected to a network that allows at least one of the following:
    1. Secure Web sockets on HTTPS port 443 and 43443
    2. Web sockets over HTTP port 80 and HTTP over Port 843 (Flash control) (Hyper-V only)
    3. RDP over port 21xxx or 443 (Enhanced control)
    4. VMware custom protocol over port 902 (VMware Remote Console Plug-in – vSphere only)
    5. For more information see Browser/Controller Support below
4. Have administrative rights on the local machine if installing the Enhanced control (Hyper-V w/RDP only).
5. Have administrative rights on the local machine if installing the VMware Remote Console Plug-In (vSphere only).

## Bandwidth Requirements

In addition to the software requirements above we recommend the following:

1. Minimum 200kbps consistent bandwidth with 1mbps burst per student  
    1. Machine controller bandwidth consumption is based on the rate onscreen content changes, some scenarios (i.e. web browsing inside the lab) may require more
    1. For optimal experience, we recommend at least 1mbps per student
1. When utilizing the instructions interface, bandwidth needs may increase based on what features are utilized, examples include:
    1. Embedded audio
    1. Embedded video
    1. Large numbers of embedded images
    1. Bandwidth usage is highly dependent on the media being used. An embedded MP3 may fit into 1mbps burst capacity, while a 1080P video can require up to 10mbps for its duration
1. When using Cloud Slice labs where the target environment is a website additional bandwidth may be required
    1. For the Azure and AWS management portals, we recommend at least 512kbps per student

## Firewall Exception Rule Information

For those that need to create a firewall exception rule to allow connectivity to the Lab on Demand servers (this isn&#39;t common), the following information can be used to create a limited destination rule to only allow the above protocols and ports from your network to the Lab on Demand cloud.

- Domain Names:
  - *.labondemand.com
  - *.learnondemandsystems.com
  - *.learnondemand.net
  - *.holsystems.com
  - *.eu.learnondemandsystems.com
  - *.au.learnondemandsystems.com

- IP Range:
  - 104.214.106.31/25, 206.196.30.001 - 206.196.30.056
  - 67.214.104.0/24
  - 185.254.59.0/24
  - 103.18.85.0/24
  - 163.47.101.0/25


The Lab on Demand system is a cloud platform that automatically provisions and connects the learner with private sandboxed resources. There is no way to predict which IP address in the cloud the learner will connect to for the provisioning of their virtual machines. Therefore, we provide a range of IP addresses and only a second level domain name.

For Hyper-V and Hyper-V w/RDP only labs, the domains and IP addresses in the table below may also be required as firewall exceptions. We strongly encourage using names, and not IP addresses, for firewall and proxy configuration if possible, as the IP addresses may change without warning (and without documentation update). This allows access even in network failover and future geographic targeting scenarios.

If specific IP addresses are required, use the following table as a guide for IP addresses:

| **DNS name** | **IP Address 1** | **IP Address 2** |
| --- | --- | --- |
| labondemand.com | 104.214.106.31 |   |
| lms.learnondemand.net | 104.215.95.25 |   |
| tampa1.holsystems.com | 206.196.30.5 |   |
| tpalabgateway.learnondemandsystems.com | 206.196.30.15 | 206.196.30.24 |
| tullabgateway.learnondemandsystems.com | 67.214.104.229 | 67.214.104.228 |
| tulsa1.learnondemandsystems.com | 67.214.104.242 |   |
| au-rds.au.learnondemandsystems.com | 103.18.85.2 |   |
| console.au.learnondemandsystems.com | 103.18.85.8 |   |
| rds01.eu.learnondemandsystems.com | 185.254.59.3 |   |
| console.eu.learnondemandsystems.com | 185.254.59.8 |   |
| sea-rds.labondemand.com | 163.47.101.8 | 163.47.101.9 |
| sea-console.labondemand.com | 163.47.101.13 |

## Launch a Demo Lab

Click the following link to launch a demo lab: [Launch a LODS Demo Lab](https://www.learnondemandsystems.com/demo-labs/). This will allow you to see if you are able to connect and function within the lab environment.

## Connection Assessment Test

If you are experiencing frequent disconnects or lag when controlling your machines, you may run a [connection assessment test](http://www.learnondemandsystems.com/cat/). This page allows you to run a connection assessment test. A connection assessment test is a very deep and thorough test that measures throughput speed, capacity, and packet quality to assess the user experience of a connection to their respective data center. This includes efficiency, data loss, recovery, duplication of data, retransmissions and even corruption.

For help with analyzing the results of your test, please review the [Interpreting Your Connection Assessment Results](connection-results.md) article.

## When Connections Traverse a Proxy

When connecting to a lab instance via a proxy, certain configuration requirements must be met for each remote controller. For more information, please review the [Proxy Requirements](proxy-requires.md) article.

## When Using Windows Server Operating Systems

When connecting to Learn on Demand Systems Training Management Systems (TMS) portals with a computer having Windows Server operating systems on it, you may experience difficulty in connecting to the sign-in page or clicking on some buttons. Steps to remediate can be found [here.](/end-user-student-faqs/class-self-paced/important-note-when-using-windows-server-operating-systems.md)

## In-Lab Software Whitelisting Information for Lab Developers

Software that communicates with remote servers outside of the lab environment may need addresses whitelisted with the vendor to work. The below address ranges are used by NAT internet access labs.

- IP addresses/scopes: 185.254.56.125 185.254.59.0/24
- IP Ranges: 199.101.110.5 - 199.101.110.25, 67.214.104.176 – 67.214.104.180, 67.214.104.254, 206.196.30.25, 103.245.221.106, 163.47.101.124 - 163.47.101.126

The below ranges are used by Public IP internet access labs.

185.254.59.0/24 185.254.58.0/24 185.254.57.0/24 168.245.202.0/23 128.136.160.9 - 128.136.160.254 103.18.85.21 - 103.18.85.254 199.101.110.31 - 199.101.110.254 199.101.111.05 - 199.101.111.254, 199.101.108.5 - 199.101.109.254

## Browser/Control Support

Machines in your lab can be accessed using any one of six virtual machine controls depending on the type of lab you are running. You can freely change between controls on those virtual machines not using SSH to find the one that works best for you.

| Virtual Machine Control           |             | Chrome  |                |            | Firefox |                   |               | Internet Explorer |                |               | Microsoft Edge |                |
|-----------------------------------|-------------|---------|----------------|------------|---------|-------------------|---------------|-------------------|----------------|---------------|----------------|----------------|
|                                   |             | Version | Protocol       | Ports      | Version | Protocol          | Ports         | Version           | Protocol       | Ports         | Version        | Protocol       |
| **HyperV/vSphere** | **HTML5 <sup>1</sup>**     | 16+     | Websockets     | 443        | 11+     | Websockets        | 443           | 10+               | Websockets     | 443           | 1+             | Websockets     |
|                   | **SSH <sup>2</sup>**     | 16+     | Websockets     | 443        | 11+     | Websockets        | 443           | 10+               | Websockets     | 443           | 1+             | Websockets     |
| **Hyper-V**        | **Flash**       | 11+     | Websockets     | 80 & 843 <sup>3</sup> | 11+     | Websockets        | 80 & 843 <sup>4</sup>    | 11+               | Websockets     | 80 & 843 <sup>2</sup>    | 11+            | Websockets     |
|                                   | **Silverlight** | 4-34 <sup>4<sup>     | HTTP           | 80         | 4-52 <sup>4<sup>      | HTTP (RDP), HTTPS | 80 (RDP), 443 | 4+                | HTTP           | 80 (RDP), 443 | N/A            | N/A            |
|                                   | **Enhanced <sup>3</sup>**  | N/A     | N/A            | N/A        | N/A     | N/A               | N/A           | 8+                | VMRDP          | 21xxx or 443  | N/A            | N/A            |
| **vSphere** | **VMware Remote Console<sup>5</sup>** | N/A     | N/A            | N/A        | 11-56     | Custom            | 902           | 8+                | Custom         | 902           | N/A            | N/A            |


1 Preferred

2 Available only when lab is configured for SSH access

3 Port 843 is required by Flash Socket Policy to authorize the use of Web sockets

4 Requires Internet Explorer. The 21xxx value depends on which host server in the cloud the lab is running on. If connection on port 21xxx fails, the Enhanced client will rollover and attempt the connection on port 443.

4 Support for NPAPI plugins (silverlight) was removed with version 45 of Chrome and 52 of Firefox. The plugin is not supported on Linux or macOS

5 Windows and Linux only, not supported on Firefox version 57 or later
