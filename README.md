![Awesome Azure Virtual Desktop](/img/awesome_azure_virtual_desktop.png)
# Awesome Azure Virtual Desktop

A curated list of links and resources for **Azure Virtual Desktop** and its related technologies. Inspired by [Awesome Azure Architecture](https://aka.ms/AwesomeAzureArchitecture), which follows a similar model for Azure architecture links, this repository centralizes knowledge for professionals deploying or managing cloud-hosted virtual desktops and remote applications.

---

## Table of Contents

- [Official](#official)
  - [What's new in Azure Virtual Desktop?](#whats-new-in-azure-virtual-desktop)
  - [Azure Virtual Desktop](#azure-virtual-desktop)
  - [FSLogix](#fslogix)
  - [App Attach](#app-attach)
  - [Windows App](#windows-app)
  - [Monitoring and Insights](#monitoring-and-insights)
  - [Architecture and Best Practices](#architecture-and-best-practices)
  - [GitHub Repositories](#github-repositories)
- [Third Party](#third-party)
  - [Management Platforms](#management-platforms)
    - [Nerdio](#nerdio)
    - [ControlUp](#controlup)
    - [Hydra by Login VSI](#hydra-by-login-vsi)
    - [Citrix](#citrix)
  - [Testing and Assessment](#testing-and-assessment)
    - [Login VSI](#login-vsi)
    - [Lakeside SysTrack](#lakeside-systrack)
    - [Rimo3](#rimo3)
  - [Thin Clients](#thin-clients)
    - [IGEL](#igel)
    - [10ZiG](#10zig)
- [Community](#community)
  - [Blog](#blog)
  - [LinkedIn](#linkedin)
  - [YouTube](#youtube)
  - [Github Repos and Tools](#github-repos-and-tools)
  - [Chats and Channels](#chats-and-channels)
  - [Trainings](#trainings)
  - [Events](#events)

---
<!-- AWESOMEAZUREVIRTUALDESKTOP:START -->
## Official
*Only official links published or maintained by Microsoft or Azure.*

### What's new in Azure Virtual Desktop

[What's new in Azure Virtual Desktop?](https://learn.microsoft.com/en-us/azure/virtual-desktop/whats-new)

Azure Virtual Desktop receives continuous monthly service updates. Below is a summary of key themes delivered across recent releases.

#### Autoscale and Host Pool Management
- **Autoscale for personal host pools** *(Preview: July 2023; GA: November 2023)* - enabling power-off policies and scheduled scaling for assigned desktops to reduce idle compute costs.
- **Session host configuration and update** *(Preview: November 2024)* - providing centralized control over OS image, agent version and extension settings across host pools, removing the need for manual session host redeployment.
- **Scheduled agent updates** *(GA: July 2022)* - allowing administrators to define maintenance windows and reduce the risk of unexpected restarts during business hours.

#### App Delivery and Profile Management
- **App Attach** *(new features preview: December 2023; portal management available: June 2024; MSIX App Attach deprecated: June 2025)* - supports additional package formats and simplifies the staging and assignment workflow through the Azure portal.
- **FSLogix profile container with Microsoft Entra-joined VMs on Azure Files** *(GA: November 2022)* - enabling profile persistence for cloud-only identities using Azure Files as SMB storage, removing the dependency on on-premises Active Directory.
- **Cloud Cache** *(performance improvements in FSLogix 2201: May 2022; PowerShell troubleshooting module and FSLogix v3 Early Access: December 2024)* - increases resiliency for profile replication across multiple storage endpoints and supports business continuity scenarios with geographically separated backends.

#### Security and Compliance
- **Watermarking** *(Preview: January 2023; GA: July 2023)* - adding QR-code-based overlays to RDP sessions to deter and trace unauthorized screen captures.
- **Screen capture protection** *(GA: August 2021)* - preventing client-side tools from capturing session content, with support extended to additional client platforms in subsequent releases.
- **Private Link for Azure Virtual Desktop** *(Preview: November 2022; GA: July 2023)* - routing AVD control plane and session traffic over private networks and removing the need for public internet exposure.
- **Clipboard transfer redirection policies** *(Preview: March 2024; GA: August 2024)* - providing fine-grained control over which directions (client to host or host to client) clipboard content can flow inside a session.

#### Client Experience
- **Windows App** *(Preview: November 2023; GA: September 2024)* - replacing the legacy Remote Desktop clients across Windows, macOS, iOS, Android and web, providing a unified access experience for Azure Virtual Desktop, Windows 365 and Remote Desktop Services.
- **Teams media optimization** *(Multimedia redirection GA: February 2023; New Teams SlimCore preview: June 2024; WebRTC-based Teams GA: March 2026)* - reducing latency and improving call quality for meetings running inside AVD sessions through progressively newer optimization architectures.

### Azure Virtual Desktop

- [Azure Virtual Desktop Documentation (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/)  
  Complete documentation for deploying and managing Azure Virtual Desktop.
- [Azure Virtual Desktop Product Page](https://azure.microsoft.com/en-us/products/virtual-desktop/)  
  Official product page for Azure Virtual Desktop on the Azure website.
- [What's new in Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/whats-new)  
  Monthly updates listing the latest features and improvements in Azure Virtual Desktop.
- [Azure Virtual Desktop Pricing](https://azure.microsoft.com/en-us/pricing/details/virtual-desktop/)  
  Overview of the per-user access pricing model and session host virtual machine costs.
- [Prerequisites for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/prerequisites)  
  Network, identity and subscription requirements before deploying Azure Virtual Desktop.
- [Create a host pool (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-host-pool)  
  Step-by-step guide to creating pooled or personal host pools in Azure Virtual Desktop.
- [Autoscale for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/autoscale-scaling-plan)  
  How to configure scaling plans to automatically start and stop session hosts based on demand, reducing compute costs.
- [Personal host pools (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-personal-host-pool)  
  How to create personal (dedicated) host pools for scenarios that require persistent desktops assigned to individual users.
- [RemoteApp streaming (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/publish-applications-stream-remoteapp)  
  How to publish individual applications instead of full desktops using RemoteApp, reducing bandwidth and simplifying the user experience.
- [Watermarking in Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/watermarking)  
  How to enable QR-code watermarks in RDP sessions to deter and trace unauthorized screen captures.
- [Screen capture protection (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/screen-capture-protection)  
  Policy that prevents client-side tools from capturing session content, relevant for regulated industries.
- [Private Link for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/private-link-overview)  
  Overview of using Azure Private Link to route AVD control plane and session traffic over private networks, removing the need for public internet exposure.
- [Azure Hybrid Benefit for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/azure-hybrid-benefit)  
  How to apply existing Windows Server and Windows 10/11 licenses to reduce session host costs through the Azure Hybrid Benefit program.
- [Azure Virtual Desktop Security Guide (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/security-guide)  
  Security recommendations and best practices for AVD deployments covering identity, networking, session security and data protection.
- [Azure Virtual Desktop for Azure Local (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/azure-stack-hci-overview)  
  Running Azure Virtual Desktop session hosts on Azure Local for data residency and latency requirements in regulated or edge scenarios.
- [Optimize Azure Virtual Desktop using insights from a Well-Architected Review Assessment (Tech Community)](https://techcommunity.microsoft.com/blog/AzureArchitectureBlog/optimize-azure-virtual-desktop-using-insights-from-a-well-architected-review-assessment/4375459)  
  Guidance on evaluating AVD environments with the Well-Architected Framework assessment to identify risks, measure maturity and improve architecture quality.

### FSLogix

- [FSLogix Documentation (Microsoft Docs)](https://learn.microsoft.com/en-us/fslogix/)  
  Complete documentation for FSLogix profile and Office container solutions, now part of Microsoft 365.
- [FSLogix Profile Container overview (Microsoft Docs)](https://learn.microsoft.com/en-us/fslogix/concepts-fslogix-profiles)  
  How FSLogix profile containers redirect and persist user profiles in non-persistent virtual environments, replacing roaming profiles and folder redirection.
- [Configure FSLogix profile containers with Azure Files (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-profile-container-azure-files)  
  How to use Azure Files (SMB) as a storage backend for FSLogix profile containers, suitable for most small and medium deployments.
- [Configure FSLogix profile containers with Azure NetApp Files (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-profile-container-netapp)  
  How to use Azure NetApp Files for high-performance FSLogix profile storage, recommended for large deployments or latency-sensitive workloads.
- [FSLogix Cloud Cache (Microsoft Docs)](https://learn.microsoft.com/en-us/fslogix/concepts-cloud-cache)  
  How to use FSLogix Cloud Cache to replicate profile containers across multiple storage locations for resilience and business continuity.
- [What's new in FSLogix (Microsoft Docs)](https://learn.microsoft.com/en-us/fslogix/whats-new)  
  Release notes and update history for FSLogix versions.

### App Attach

- [App Attach overview (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/app-attach-overview)  
  Introduction to App Attach, which allows MSIX-packaged applications to be staged and delivered dynamically to AVD session hosts without installation.
- [Set up App Attach (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/app-attach-setup)  
  Step-by-step guide to configuring App Attach in the Azure portal, including image storage in Azure Files and assignment to host pools.
- [MSIX Packaging Tool (Microsoft Docs)](https://learn.microsoft.com/en-us/windows/msix/packaging-tool/tool-overview)  
  Documentation for the MSIX Packaging Tool used to convert existing application installers to MSIX format for use with App Attach.
- [Test MSIX App Attach packages (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/app-attach-test-msix-packages)  
  How to validate MSIX packages before deploying them through App Attach to avoid session host issues.

### Windows App

- [Windows App Documentation (Microsoft Docs)](https://learn.microsoft.com/en-us/windows-app/)  
  Documentation for Windows App, the unified Microsoft client for Azure Virtual Desktop, Windows 365 and Remote Desktop Services.
- [Get started with Windows App on Windows (Microsoft Docs)](https://learn.microsoft.com/en-us/windows-app/get-started-connect-devices-desktops-apps)  
  How to install and connect to Azure Virtual Desktop resources using Windows App on Windows.
- [Windows App on macOS (Microsoft Docs)](https://learn.microsoft.com/en-us/windows-app/get-started-connect-devices-desktops-apps?pivots=macos)  
  How to use Windows App to access AVD on macOS devices.
- [What's new in Windows App (Microsoft Docs)](https://learn.microsoft.com/en-us/windows-app/whats-new)  
  Release notes and changelogs for the Windows App client across all supported platforms.

### Monitoring and Insights

- [Azure Virtual Desktop Insights (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/insights)  
  How to use AVD Insights, an Azure Monitor workbook, to monitor session host health, user connections and resource consumption from a single view.
- [Use Azure Monitor for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/azure-monitor)  
  Guide to collecting and analyzing AVD diagnostics data in Azure Monitor and Log Analytics for alerting and custom queries.
- [Diagnostic settings in Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/diagnostics-log-analytics)  
  How to enable and route AVD diagnostic logs to Log Analytics for custom querying and long-term retention.
- [Monitor session host performance (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/performance-counters)  
  Recommended Windows performance counters to capture on AVD session hosts for capacity planning and user experience monitoring.
- [Set up alerts for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-alerts)  
  How to create Azure Monitor alert rules that trigger on AVD-specific conditions such as connection failures and session host health changes.

### Architecture and Best Practices

- [Azure Virtual Desktop Landing Zone Accelerator (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/scenarios/azure-virtual-desktop/enterprise-scale-landing-zone)  
  Enterprise-scale reference implementation for Azure Virtual Desktop following the Cloud Adoption Framework landing zone model, with Bicep and Terraform modules.
- [Cloud Adoption Framework for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/scenarios/azure-virtual-desktop/)  
  Strategic and technical guidance for adopting AVD across strategy, planning, readiness, migration and governance phases.
- [Azure Well-Architected Framework for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/well-architected/azure-virtual-desktop/)  
  Guidance aligned with the five pillars of the Well-Architected Framework applied specifically to AVD deployments.
- [Azure Virtual Desktop reference architecture (Azure Architecture Center)](https://learn.microsoft.com/en-us/azure/architecture/example-scenario/wvd/windows-virtual-desktop)  
  Reference architecture for a standard multi-session AVD deployment including networking, identity and storage components.
- [Multi-region BCDR for Azure Virtual Desktop (Azure Architecture Center)](https://learn.microsoft.com/en-us/azure/architecture/example-scenario/wvd/azure-virtual-desktop-multi-region-bcdr)  
  Architecture for deploying AVD across multiple Azure regions to meet business continuity and disaster recovery requirements.
- [Image lifecycle management for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-golden-image)  
  Guidance on building and maintaining golden images (session host templates) using Azure Compute Gallery and Azure Image Builder.
- [Azure Image Builder overview (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-machines/image-builder-overview)  
  Overview of the Azure Image Builder service used to automate the creation and distribution of custom AVD session host images.
- [RBAC for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/rbac)  
  Overview of built-in roles and how to delegate management tasks across operations, helpdesk and infrastructure teams in AVD.
- [Network connectivity in Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/network-connectivity)  
  Explains how RDP Shortpath, reverse connect transport and the AVD Gateway work together, with guidance for optimizing network paths.
- [RDP Shortpath for Azure Virtual Desktop (Microsoft Docs)](https://learn.microsoft.com/en-us/azure/virtual-desktop/rdp-shortpath)  
  How to enable direct UDP-based connectivity between clients and session hosts to reduce latency and improve session quality.

### GitHub Repositories

- [AVD Accelerator (GitHub)](https://github.com/Azure/avdaccelerator)  
  Official Microsoft repository with Bicep and Terraform reference implementations for deploying AVD following the enterprise-scale landing zone pattern.
- [RDS-Templates (GitHub)](https://github.com/Azure/RDS-Templates)  
  Official Microsoft repository containing ARM templates and PowerShell scripts for host pool creation, session host provisioning and application group management.
- [Azure Virtual Desktop - Sizing Guides (GitHub)](https://github.com/jonathan-vella/azure-local-sizing-guides)  
  Sizing guidance maintained by Jonathan Vella (Microsoft Senior CSA) covering AVD, AKS and Arc-enabled SQL MI on Azure Local.

---

## Third Party

*Independent vendors offering management, testing, assessment and access solutions for Azure Virtual Desktop environments.*

### Management Platforms

*Software commonly used to manage, automate and optimize Azure Virtual Desktop infrastructure.*

#### Nerdio

- [Nerdio Manager for Enterprise](https://getnerdio.com/nerdio-manager-for-enterprise/)  
  Enterprise AVD management platform for automating host pool sizing, image management, cost optimization and session lifecycle from a single console.
- [Nerdio Manager for Enterprise Documentation](https://nmehelp.getnerdio.com/hc/en-us/categories/360003434991-Nerdio-Manager-for-Enterprise)  
  Official Nerdio documentation covering installation, configuration and day-to-day operations.
- [Nerdio Cost Estimator](https://getnerdio.com/cost-estimator/)  
  Tool to estimate compute cost savings achieved by adopting Nerdio Manager's autoscale and scheduling features versus managing AVD manually.
- [Nerdio - AVD for Azure Local](https://nmehelp.getnerdio.com/hc/en-us/articles/25499377328909-AVD-for-Azure-Local-and-Nerdio-Manager)  
  How to configure Nerdio to manage AVD session hosts running on Azure Local, including host pool provisioning and golden image management.
- [Nerdio - Integrate existing AVD resources with Nerdio Manager](https://nmehelp.getnerdio.com/hc/en-us/articles/34054417281165-How-can-I-integrate-AVD-resources-provisioned-to-Azure-Local-Stack-HCI-with-Nerdio-Manager)  
  Guide to onboard an existing AVD environment (including resources on Azure Local) into Nerdio Manager without redeploying.

#### ControlUp

- [ControlUp - Azure Virtual Desktop](https://www.controlup.com/solutions/azure-virtual-desktop/)  
  ControlUp landing page for AVD, covering real-time session analytics, automated remediation and user experience monitoring.
- [ControlUp - Platform Overview](https://www.controlup.com/platform/)  
  Overview of ControlUp's agent-based telemetry, script-based automation and multi-tenant management capabilities for AVD and hybrid EUC environments.

#### Hydra by Login VSI

- [Hydra - Landing Page](https://euc.loginvsi.com/hydra-by-login-vsi)  
  Hydra product overview from Login VSI, covering image lifecycle management and AVD host pool automation.
- [Hydra - Imaging, Rollout and Management for Azure Virtual Desktop](https://blog.itprocloud.de/AVD-Hydra-For-Azure-Stack-HCI-Deplyoment-Management/)  
  Article by Marcel Meurer on configuring Hydra for automated image management and rollout in AVD and Azure Local environments.

#### Citrix

- [Citrix DaaS for Azure](https://www.citrix.com/products/citrix-daas/azure.html)  
  Citrix Desktop as a Service offering on Azure, providing Citrix application delivery and management capabilities on top of Azure compute infrastructure.
- [Citrix DaaS Documentation](https://docs.citrix.com/en-us/citrix-daas)  
  Complete Citrix DaaS documentation covering site configuration, machine catalog creation and Citrix policy management.
- [Citrix Virtual Apps and Desktops - Connecting Azure Local (Docs)](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/2507-ltsr/install-configure/connections/connection-azure-local)  
  Guide on using Citrix Virtual Apps and Desktops with Azure Local infrastructure as the hosting layer.

### Testing and Assessment

*Tools used to test application compatibility, simulate user load and measure session host performance.*

#### Login VSI

- [Login VSI - Load Testing for Virtual Desktops](https://www.loginvsi.com/solutions/azure-virtual-desktop/)  
  Login VSI landing page for AVD, covering how to benchmark session host capacity and validate user density before production rollout.
- [Login VSI - Knowledge Base](https://www.loginvsi.com/knowledge-base/)  
  Documentation hub for Login VSI products including Load Generator and VDI Benchmark.

#### Lakeside SysTrack

- [Lakeside SysTrack - Azure Virtual Desktop](https://www.lakesidesoftware.com/solutions/microsoft-azure-virtual-desktop/)  
  SysTrack landing page for AVD, covering digital experience monitoring, right-sizing and migration readiness assessments for moving workloads to AVD.
- [Lakeside SysTrack - Digital Experience Monitoring](https://www.lakesidesoftware.com/platform/digital-experience-monitoring/)  
  How Lakeside collects continuous endpoint telemetry to measure user experience quality inside AVD sessions and identify degradation before it affects users.

#### Rimo3

- [Rimo3 - Application Compatibility Testing for AVD](https://www.rimo3.com/solutions/avd/)  
  Rimo3 landing page for automated application compatibility and regression testing in AVD and Windows 365 migration projects.
- [Rimo3 - Platform Overview](https://www.rimo3.com/platform/)  
  How Rimo3 automates application testing at scale, reducing manual effort and risk for large application portfolios migrating to AVD.

### Thin Clients

*Hardware and software vendors offering purpose-built thin client endpoints for accessing Azure Virtual Desktop.*

#### IGEL

- [IGEL - Azure Virtual Desktop](https://www.igel.com/azure-virtual-desktop/)  
  IGEL landing page for AVD, covering how IGEL OS provides a secure and managed thin client endpoint for accessing AVD sessions with minimal local attack surface.
- [IGEL Community](https://community.igel.com/)  
  Community hub for IGEL users and administrators with AVD-specific discussions, how-to guides and troubleshooting resources.
- [IGEL Ready Program](https://www.igel.com/igel-ready/)  
  Partner ecosystem listing hardware and peripherals certified to work with IGEL OS in AVD environments.

#### 10ZiG

- [10ZiG - Azure Virtual Desktop](https://www.10zig.com/solutions/azure-virtual-desktop)  
  10ZiG landing page for AVD, covering thin client hardware and 10ZiG NOS purpose-built for accessing Azure Virtual Desktop environments.
- [10ZiG Manager - Central Management](https://www.10zig.com/products/manager)  
  Overview of 10ZiG's endpoint management platform for deploying and maintaining 10ZiG thin clients at scale in AVD deployments.

---

## Community

*Resources that do not come from Microsoft or the vendors listed in the Third Party section.*

### Blog

*To avoid an excessive list, only entire blogs are referenced, not individual posts.*

- [schmitt-nieto.com](https://schmitt-nieto.com/tags/#azure-virtual-desktop)  
  Yes, naming my own blog first is bad form, but here I share hands-on content about AVD implementation and management.
- [ryanmangansitblog.com](https://ryanmangansitblog.com/)  
  Blog by MVP [Ryan Mangan](https://www.linkedin.com/in/ryanmangan/) covering Azure Virtual Desktop in depth, including troubleshooting, optimization and new feature walkthroughs.
- [gettothe.cloud](https://www.gettothe.cloud/)  
  Blog by [Alex ter Neuzen](https://www.linkedin.com/in/aterneuzen) focused mainly on AVD, Azure Local and IaC. Highly recommended reading.
- [christiaanbrinkhoff.com](https://www.christiaanbrinkhoff.com/)  
  Blog by [Christiaan Brinkhoff](https://www.linkedin.com/in/christiaanbrinkhoff/) (Microsoft Principal PM Manager for Azure Virtual Desktop) featuring the latest AVD announcements, deep dives and public roadmap previews.
- [blog.itprocloud.de](https://blog.itprocloud.de/)  
  Blog by [Marcel Meurer](https://www.linkedin.com/in/marcelmeurer/) featuring AVD automation tools, Hydra technical deep dives and host pool management patterns.
- [avdpunks.com](https://avdpunks.com/)  
  Community blog by a group of AVD specialists covering a wide range of topics from initial deployment to advanced optimization and security.
- [rozemuller.com](https://rozemuller.com/)  
  Blog by MVP [Sander Rozemuller](https://www.linkedin.com/in/sanderrozemuller/) focused on Azure Virtual Desktop automation using the REST API, PowerShell and infrastructure-as-code.
- [imab.dk](https://imab.dk/)  
  Blog by [Nicolaj Andersen](https://www.linkedin.com/in/nicolajandersen/) with practical AVD and Intune content focused on implementation and scripted automation.
- [andrewstaylor.me](https://andrewstaylor.me/)  
  Blog by [Andrew Taylor](https://www.linkedin.com/in/andrew-taylor-it/) covering AVD, Intune and Microsoft 365 with a focus on automation and community tooling.
- [mikemdm.de](https://mikemdm.de/)  
  Blog by MVP [Michael Meier](https://www.linkedin.com/in/michael-meier-ba3b72210/) covering AVD and Azure Local labs and real-world implementations.
- [jacquestheron.com](https://www.jacquestheron.com/)  
  Blog by MVP [Jacques Theron](https://www.linkedin.com/in/jacquestheron/) with AVD and Microsoft 365 content covering deployment and management scenarios.
- [joeyverlinden.com](https://joeyverlinden.com/)  
  Blog by [Joey Verlinden](https://www.linkedin.com/in/joeyverlinden/) featuring AVD implementation guides, FSLogix tips and automation scripts.
- [msendpointmgr.com](https://msendpointmgr.com/)  
  Multi-author blog covering endpoint management including AVD image management, Intune integration and application packaging for virtual environments.

### LinkedIn

*Most day-to-day news on Azure Virtual Desktop arrives first on LinkedIn. Here are profiles worth following.*

- [Christiaan Brinkhoff](https://www.linkedin.com/in/christiaanbrinkhoff/)  
  Microsoft Principal PM Manager for Azure Virtual Desktop who regularly publishes feature announcements, deep dives and roadmap previews directly from the product group.
- [Ryan Mangan](https://www.linkedin.com/in/ryanmangan/)  
  UK-based MVP who publishes detailed AVD content covering new features, optimization techniques and real-world troubleshooting cases.
- [Marcel Meurer](https://www.linkedin.com/in/marcelmeurer/)  
  Creator of WVD Admin and Hydra who shares AVD tooling updates, automation patterns and community resources.
- [Sander Rozemuller](https://www.linkedin.com/in/sanderrozemuller/)  
  Dutch MVP publishing AVD automation content focused on REST API usage, Bicep and infrastructure-as-code approaches.
- [Stefan Dingemanse](https://www.linkedin.com/in/stefandingemanse/)  
  Netherlands-based MVP and AVD specialist who publishes practical content covering networking, identity and deployment automation.
- [Tom Hickling](https://www.linkedin.com/in/tomhickling/)  
  UK-based MVP covering Azure Virtual Desktop with a focus on enterprise deployments, governance and best practices.
- [Alex ter Neuzen](https://www.linkedin.com/in/aterneuzen)  
  Focused on AVD and Azure Local content including IaC, hybrid scenarios and real-world implementation patterns.
- [Bas van Kaam](https://www.linkedin.com/in/basvankaamnl/)  
  AVD specialist and author of *Mastering Microsoft Azure Virtual Desktop* who regularly shares community updates, book insights and technical deep dives.

### YouTube

*Channels that focus primarily on Azure Virtual Desktop rather than hosting only an occasional video.*

- [Microsoft Cloud Workshop](https://www.youtube.com/@MicrosoftCloudWorkshop)  
  Channel by Dean Cefola (Microsoft CSA) featuring in-depth AVD technical sessions, architecture reviews and hands-on labs.
- [Ryan Mangan](https://www.youtube.com/@RyanManganMVP)  
  Channel by MVP Ryan Mangan covering Azure Virtual Desktop features, labs and step-by-step walkthroughs.
- [Marcel Meurer](https://www.youtube.com/@MarcelMeurer)  
  Channel by Marcel Meurer focusing on Hydra, WVD Admin tooling and AVD automation demonstrations.
- [Carsten Rachfall](https://www.youtube.com/@CarstenRachfahl)  
  German-language channel by MVP Carsten Rachfall streaming Azure Virtual Desktop and Azure Local implementations.

### Github Repos and Tools

- [AVD Accelerator (GitHub)](https://github.com/Azure/avdaccelerator)  
  Official Microsoft repository with Bicep and Terraform code for deploying AVD following the enterprise-scale landing zone pattern. The most complete IaC starting point for new AVD deployments.
- [RDS-Templates (GitHub)](https://github.com/Azure/RDS-Templates)  
  Official Microsoft repository with ARM templates and PowerShell scripts for host pool creation, session host registration and application group management.
- [GetToThe-Cloud - Website (GitHub)](https://github.com/GetToThe-Cloud/Website)  
  Source repository for the GetToThe.Cloud website, including AVD-related Terraform and deployment scripts used across the site.
- [Sander Rozemuller - GitHub](https://github.com/srozemuller)  
  GitHub profile of Sander Rozemuller (MVP) with scripts and modules for managing Azure Virtual Desktop through the REST API and PowerShell, covering host pools, session hosts and application groups.
- [Marcel Meurer - WVD-Hydra (GitHub)](https://github.com/MarcelMeurer/WVD-Hydra)  
  Open-source AVD management tool by Marcel Meurer covering host pool automation, image management and session control, predecessor to the commercial Hydra product.
- [AVD - FSLogix Profile Status (Tool)](https://www.linkedin.com/posts/drazen-nikolic-816906142_avd-microsoft-azurevirtualdesktop-ugcPost-7364022385827557376-NEle)  
  After the deprecation of FXTray, it became difficult to check the status of FSLogix profiles. With this PowerShell script, it is once again possible to verify profile status in a simple and centralized way.
- [AVD Sizing Guides (GitHub)](https://github.com/jonathan-vella/azure-local-sizing-guides)  
  Sizing guides for AVD and related services on Azure Local, maintained by Jonathan Vella (Microsoft Senior CSA).

### Chats and Channels

- [Azure Virtual Desktop Tech Community (Microsoft)](https://techcommunity.microsoft.com/category/AzureVirtualDesktop)  
  Official Microsoft Tech Community space for Azure Virtual Desktop announcements, Q&A and community discussions moderated by the product team.

### Trainings

- [AZ-140: Configuring and Operating Azure Virtual Desktop (Microsoft Learn)](https://learn.microsoft.com/en-us/credentials/certifications/azure-virtual-desktop-specialty/)  
  Official Microsoft certification exam covering AVD deployment, configuration, access management, monitoring and performance optimization.
- [Deliver remote desktops and apps from Azure with Azure Virtual Desktop (Microsoft Learn)](https://learn.microsoft.com/en-us/training/paths/m365-wvd/)  
  Free official Microsoft Learn path covering the core concepts and deployment tasks for Azure Virtual Desktop.
- [Introduction to Azure Virtual Desktop (Microsoft Learn)](https://learn.microsoft.com/en-us/training/modules/m365-wvd-intro/)  
  Introductory module explaining the AVD service model, key components and use cases for organizations considering adoption.
- [Deploy Azure Virtual Desktop (Microsoft Learn)](https://learn.microsoft.com/en-us/training/modules/deploy-azure-virtual-desktop/)  
  Hands-on module walking through the steps to create a host pool, configure application groups and connect users to AVD.

### Events

| Name | Description | Price | Remote | Date |
|------|-------------|-------|--------|------|
| ~~[AVD Tech Fest - Berlin (Germany)](https://www.controlup.com/avd-techfest-2025/)~~ | Community-driven event focused exclusively on Azure Virtual Desktop organized by the AVD community. | ~~99 €~~ | ~~No~~ | ~~September 10-11, 2025~~ |
| ~~[Microsoft Ignite - San Francisco (USA)](https://register.ignite.microsoft.com/)~~ | Flagship Microsoft conference featuring Azure Virtual Desktop sessions, roadmap previews and hands-on labs. | ~~2325 $~~ | ~~Yes (Digital pass are **Free**)~~ | ~~November 17-21, 2025~~ |
| [CDC Germany 2026 - Hanau (Germany)](https://www.cdc-germany.de/) | Two-day Cloud and Datacenter Conference with sessions on AVD, Windows 365, Intune and hybrid identity alongside Azure Local and Windows Server content. | €499-€999 (net, depending on ticket type) | No | September 30 - October 1, 2026 |

<!-- AWESOMEAZUREVIRTUALDESKTOP:END -->
---

> Contributions are welcome. Please submit a pull request or an issue with verified links or improvements.
