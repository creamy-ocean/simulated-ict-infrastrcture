# ITransformer ICT Infrastructure
> CS (Computer Systems) Final Assignment
>
> Simulated ICT Infrastructure Planning
> 
**Authors:** Hyeyoung Yun, May Panchi Khant

# Introduction
This project is the final assignment for the CS (Computer Systems) unit. The report outlines the ICT infrastructure requirements for a simulated digital transformation agency, 'ITransformer Pty. Ltd.'. It includes software/hardware requirements, server infrastructure decisions, overall topology, and recovery/backup operations for the company.

# EXECUTIVE SUMMARY

This report outlines the ICT infrastructure requirements for ITransformer Pty. Ltd., a simulated digital transformation agency with offices in Sydney and Perth. The objective is to ensure that every department has the appropriate combination of hardware, software, and systems to perform their tasks effectively. By carefully matching tools to roles, the company can operate more efficiently, connect its teams across both offices, and continue delivering strong digital transformation services to clients.

The report begins by describing the different roles and their software requirements. For example, legal consultants require legal research tools to provide accurate advice to their clients, and digital transformation analysts need data analytics tools to analyse their clients’ business strategies (Teal Labs, n.d.-a; Teal Labs, n.d.-b). This helps determine which business software and operating systems are required for their specific functions.

The report then addresses hardware requirements for different departments. For instance, the marketing team performs best with iMac desktops because of their strong multimedia capabilities, while consultants prefer lightweight 2-in-1 laptops that allow them to move easily between client meetings and offices. These choices reflect the daily tasks of staff members and ensure they have access to appropriate tools.

Subsequently, the report explains the company’s scanning and printing requirements. Multifunction colour laser printers are used as they allow staff members to quickly print different types of documents such as reports and contracts (Pavlovic, 2024). A cloud printing solution is chosen since it offers centralised management and allows staff to print easily from any device (Microsoft, 2024b).

Following this, the report describes server infrastructure decisions. A hybrid system is recommended—combining in-house resources for enhanced control and security with cloud solutions for improved flexibility and data redundancy. Active directory, FTP server, and local NAS backup server are managed in-house, while the mail server and AWS backup server are managed through cloud services.

The report then focuses on the overall topology. It illustrates the company’s entire system architecture, including how the two offices are interconnected and how each PC and laptop connects to different switch and access point devices.

Finally, the report outlines a practical approach to disaster recovery and backup operations. The combination of weekly full backups on Sundays and daily incremental backups provides a good balance between data protection, space usage, and cost effectiveness (Amazon Web Services, n.d.; Pronet Technology, 2023). Local NAS server combined with AWS S3 cloud storage ensures that critical information is protected through redundant layers, and files can be restored quickly if a disaster happens.

# 1.0 Company Overview

ITransformer is a Sydney-based Australian digital transformation agency that helps small businesses transform their operations into digital-friendly businesses. The company currently operates two offices: the main office in Sydney, which has a full-sized team, and a smaller branch office in Perth. Its main goal is to help small businesses improve efficiency and competitiveness through adopting digital systems. The company employs 60 staff members across both locations.

The headquarters office is located in Sydney, where most digital transformation experts are based, along with executive administrators and HR and accounting departments. This office serves as the centre for high-level project design and strategic decision-making. It is the company's main operating location and is equipped with modern technology infrastructure, including internal servers.

The Perth branch is a smaller and more flexible branch, committed to helping local clients in Western Australia. It has a mix of consultants, marketing representatives, salespeople, and a small IT support team. By using secure networking infrastructure and cloud platforms, the Perth branch maintains excellent connectivity to the Sydney office, allowing employees at both locations to collaborate effectively without any issues.

# 2.0 Staff levels and ICT requirements

**Sydney Office**

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| Position | Requirements | Number | Hardware | OS |
| CEO | Office, email, full system access, video conferencing tools | 1 | HP 15.6” Laptop | Windows 11 Pro |
| CFO | Office, email, full system access, video conferencing tools | 1 | HP 15.6” Laptop | Windows 11 Pro |
| CTO | Office, email, full system access, video conferencing tools | 1 | HP 15.6” Laptop | Windows 11 Pro |
| COO | Office, email, full system access, video conferencing tools | 1 | HP 15.6” Laptop | Windows 11 Pro |
| Human Resources | Office, email, human resource management system, HR shared directory | 2 | HP 24-cr0009 All-in-one PC | Windows 11 Pro |
| Accounting/Finance | Office, email, accounting system, payroll system, accounting shared directory | 2 | HP 24-cr0009 All-in-one PC | Windows 11 Pro |
| Marketing | Email, Adobe Creative Cloud, content management system | 3 | iMac (M4) 24” | macOS 15 |
| Local Sales | Office, email, customer relationship management tools, sales shared directory | 3 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| Legal Consultant | Office, email, customer relationship management tools, legal research tools, legal shared directory | 2 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| Digital Transformation Consultant | Office, email, customer relationship management tools, project management tools, digital transformation shared directory | 5 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| Digital Transformation Analyst | Office, email, data analytics tools, project management tools, video conferencing tools, digital transformation shared directory | 8 | HP 24-cr0009 All-in-one PC | Windows 11 Pro |
| Digital Transformation Architect | Office, email, enterprise resource planning tools, project management tools, video conferencing tools, digital transformation shared directory | 5 | HP 24-cr0009 All-in-one PC | Windows 11 Pro |
| Digital Transformation Change Manager | Office, email, project management tools, change management & adoption tools, digital transformation shared directory | 5 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| IT Administrator | Office, email, full system access, active directory management tools, FTP server management tools, network monitoring tools | 2 | HP 24-cr0009 All-in-one PC | Windows 11 Pro, Windows Server 2025 |
| Customer Support | Office, email, customer service software | 2 | HP 24-cr0009 All-in-one PC | Windows 11 Pro |

**Perth Office**

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| Position | Requirements | Number | Hardware | OS |
| Branch Manager | Office, email, full system access, video conferencing tools | 1 | HP 15.6” Laptop | Windows 11 Pro |
| Technical Lead | Office, email, full system access, video conferencing tools | 1 | HP 15.6” Laptop | Windows 11 Pro |
| Marketing | Office, email, content management system | 2 | iMac (M4)  24” | macOS 15 |
| Local Sales | Office, email, customer relationship management tools, sales shared directory | 3 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| Legal Consultant | Office, email, customer relationship management tools, legal research tools, legal shared directory | 2 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| Digital Transformation Consultant | Office, email, customer relationship management tools, project management tools, video conferencing tools, digital transformation shared directory | 3 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| Digital Transformation Change Manager | Office, email, project management tools, change management & adoption tools, video conferencing tools, digital transformation shared directory | 3 | HP 14” Pavilion x360 2 in 1 Laptop | Windows 11 Pro |
| IT Administrator | Office, email, full system access, network monitoring tools | 1 | HP 24-cr0009 All-in-one PC | Windows 11 Pro |
| Customer Support | Office, email, customer service software | 1 | HP 24-cr0009 All-in-one PC | Windows 11 Pro |

## 2.1 Software Requirements

Based on departmental roles, ITransformer agency's software requirements can be divided into six sections. These configurations are designed for software compatibility and to meet the specific needs of each department.

### 1. Administrative Roles

Executive administrators (CEO, CFO, CTO, COO, Branch Manager, and Technical Lead) will use Windows 11 Pro as it is compatible with documenting and email software. They require full system access to manage and integrate all sectors of the company. Additionally, they need video conferencing tools to communicate effectively with staff members in the Perth office.

### 2. Clerical Roles

Windows 11 Pro will be used by staff members in the following departments: Human Resources, Accounting/Finance, and Customer Support. This configuration was selected because it supports a wide range of general business software and applications, such as payroll system and human resource management system, as well as office and email software.

### 3. Marketing Department

Marketing department staff will have access to the Adobe Creative Cloud suite. As macOS provides excellent design tools and superior support for multimedia applications, these users will use the latest version of macOS. Additionally, macOS ensures reliability and exceptional performance for creative content development. The marketing team also utilises a content management system to manage content on the company’s website pages (Carnegie, 2023). They post new content and update existing content with the system (Carnegie, 2023).

### 4. Customer Interactive Roles

Roles that interact directly with customers, such as Local Sales, Legal Consultants, Digital Transformation Consultants, and Change Managers, will use Windows 11 Pro. This allows them to access shared file storage using Active Directory, ensuring secure access to confidential presentation resources and contract documents. Digital Transformation Consultants and Change Managers in the Perth office require video conferencing tools to maintain regular communication with Digital Transformation Analysts and Architects based in the Sydney office. Local Sales and all consultants need customer relationship management tools to manage clients’ contacts and their requirements. Additionally, legal consultants need legal research tools to search regulations and case law to provide expert advice to clients (Teal Labs, n.d.-b). Digital transformation departments need project management tools to streamline overall transformation processes and manage schedules (Teal Labs, n.d.-a). In addition, Digital Transformation Change Managers need change management and adoption tools to guide clients through transitions and train staff members in their companies (Teal Labs, n.d.-a).

### 5. Analysis and Architectural Roles

Digital Transformation Analysts and Architectswill use Windows 11 Pro. As they need to manage working files and share them with team members, they will use Windows 11 Pro, which supports Active Directory systems. Analysts require data analytics tools for analysing client companies’ infrastructure and strategies (Teal Labs, n.d.-a). Additionally, architects need enterprise resource planning tools to streamline vital processes of client enterprises (Teal Labs, n.d.-a). Both departments need project management tools to manage overall project schedules and tasks throughout the entire digital transformation process (Teal Labs, n.d.-a).

### 6. IT administration Department

IT administrators will use Windows 11 Pro, and those based in the Sydney office will also use Windows Server 2025 on an additional desktop. Since Active Directory centralised management is supported by Windows Server, IT administrators in the Sydney office can easily set up group policies for system security and manage access permissions for other staff members to shared file directories. Additionally, they use network monitoring tools to monitor network transmission and access to prevent and detect malicious activities. This reduces the possibility of malware infections and enhances data integrity.

## 2.2 Hardware Requirements

Based on departments, the company’s hardware requirements can be divided into four types. These requirements are determined based on the performance and functionality needed for each department.

### 1. General laptop

The HP 15.6” Core i5 8GB/256GB model laptop is used by executive administrators (CEO, CFO, CTO, COO, Branch Manager, and Technical Lead), as the i5 processor and 8GB RAM provide adequate performance for document processing and video conferencing (HP, n.d.-b).

### 2. All-in-One PC

Clerical roles (HR, Accounting/Finance, Customer Support), Digital Transformation Analysts/Architects, and IT administrators will use the HP 24-cr0009a R5 16GB/512GB All-in-One PC since they work primarily in the office. The AMD Ryzen 5 processor and 16GB RAM provide sufficient performance for running business applications and document processing software together (HP, n.d.-a).

### 3. iMac PC

The marketing department will use iMac (M4) 24” model since the M4 chip enables smooth performance for applications such as Adobe Creative Suite and content management system (Apple, n.d.). Additionally, the Retina display allows high resolution and vibrant, detailed visuals, allowing the staff members to work effectively with graphic designs (Apple, n.d.).

### 4. 2-in-1 laptop

Customer interactive roles (Local Sales, Legal Consultants, Digital Transformation Consultants, and Change Managers) will use the HP 14” Pavilion x360 Core i5 8GB/256GB 2-in-1 Laptop since 2-in-1 laptops enable staff to carry their devices easily and demonstrate strategies or work progress to customers using the rotational screen (HP, n.d.-c).

## 2.3 Printing and Scanning Requirements

For the offices in Sydney and Perth, ITransformer will use a cloud print solution, Microsoft Universal Print, to manage print and scan workloads. This allows centralised monitoring, user authentication, and print queues management, while allowing staff members to print easily from any device (Microsoft, 2024b). With this centralised system, the IT administrators can easily maintain the system, monitor print queues, and enforce printing policies (Microsoft, 2024b).

Colour multifunction (all-in-one) laser printers are used for both offices. Colour printing is required in most departments, such as marketing, sales, and consulting, as they need to print graphic materials for client demonstrations. Multifunction printers offer scanning and copying as well as printing, allowing staff to perform different tasks with their contracts and communications with customers and staff from the other office (Pavlovic, 2024). Additionally, laser printers provide fast printing and handle large volumes of printing efficiently (Pavlovic, 2024).

## 2.4 Server Requirements

|  |  |
| --- | --- |
| Service | Cloud/In-house |
| Active Directory Server | In-house |
| FTP Server | In-house |
| Mail Server | Cloud (MS Outlook) |
| Backup Server | In-house (NAS) + Cloud (AWS S3) |

The Active Directory Server and FTP server are managed through Windows Server by the IT administrators in-house, as they need to be under direct control for managing resource authentication and securing shared directories and files. The mail server is managed through Microsoft Outlook as it provides OneDrive cloud storage and security options, such as sender verification using digital signatures and encryption to protect messages from unauthorized access (Microsoft, 2024a). Backup servers are maintained using both in-house (NAS) and cloud (AWS S3) solutions to provide additional protection and flexibility for disaster recovery plans.

# 3.0 TOPOLOGY

<img width="760" alt="Infrastructure Topology Diagram" src="https://github.com/user-attachments/assets/e1b7251c-7718-4d2e-aeaa-be7880f9ab79" />  

The topology shows that both Sydney and Perth offices are connected to the cloud (Internet) and are interconnected through a Site-to-Site VPN (Virtual Private Network). This VPN is used for connecting two sites securely over the Internet, ensuring that each office can access the other’s resources through the encrypted connection (PivIT Global, n.d.). Each office has a router that connects to several switches, with each switch connecting to different desktops, printers, and servers. One of the switches in each office connects to an AP (Access Point) for wireless laptop connectivity.

# 4.0 DISASTER RECOVERY AND BACKUP

## 4.1 Backup Schedule

To ensure business continuity and protection of critical data, a hybrid backup strategy is implemented. Daily backup is required as it ensures that data is updated every day, since there could be changes to critical client information and contracts. Incremental backup is chosen for the daily backup method because it is more efficient in terms of space usage and cost compared to differential backup (Amazon Web Services, n.d.). Additionally, full backup is needed every week to provide additional data protection (Pronet Technology, 2023). Both daily and weekly backups are scheduled for 12:00 AM as this ensures optimal timing for storing all work completed during the day when no staff members are working. For weekly backup, Sunday is the most suitable time to integrate all work completed during the week, since it is the last day of the working week.

- Incremental Backup:
- Only changes since the last backup is stored
- Automatically replicated to AWS S3 cloud storage
- Schedule: Daily at 12:00 AM
- Full Backup:
- All files are backed up to a local backup server in Sydney
- Automatically replicated to AWS S3 cloud storage
- Schedule: Every Sunday at 12:00 AM

## 4.2 Media for Backup

For the local backup server, a RAID/NAS server is used as the local backup solution. Since RAID allows chaining of multiple inexpensive disks, it can be set up at lower costs (Donnelly, 2023). NAS provides network access, allowing remote access from both offices (Donnelly, 2023). AWS S3 cloud storage is chosen for replication since it is recommended for storing data analytics, and its pricing model is based on storage size, which is suitable for backup storage that does not require frequent retrieval (Cloudlaya, 2025).

- Primary Storage: Local backup server (RAID NAS in Sydney)
- Provides flexible scalability and network accessibility
- Accessible from the Perth office and remotely via laptops
- Secondary Storage: Cloud storage (AWS S3)
- Highly reliable and secure, with data automatically replicated across multiple servers (Cloudlaya, 2025)
- Provides an additional protection layer against local disasters that may affect primary storage in the Sydney office

## 4.3 Backup Contents

The following contents are included in the backup scope:

- FTP server shared directories:
- HR directory: Internal policies, staff training materials
- Accounting directory: Financial reports, budget planning documents
- Sales directory: Sales presentation materials
- Legal directory: Legal contracts
- Digital Transformation directory: Project documentation
- Additional backup items:
- Local backups from business applications (e.g., payroll system)

## 4.4 Testing and Responsibility

IT administrators will perform recovery testing every six months. While it is recommended to do it once a year, the company handles critical client information and digital transformation projects that require more frequent evaluation (MetricStream, n.d.). However, since full recovery testing requires significant time and money, performing tests twice a year provides an appropriate balance between cost efficiency and stability. Additional testing will be conducted after any major system changes to ensure all stakeholders understand their roles and responsibilities during disaster scenarios, and to evaluate the effectiveness of recovery procedures. Any issues identified during testing will be documented and procedures will be updated accordingly.

IT administrators are responsible for scheduling backups, monitoring backup logs, and ensuring successful replication to AWS S3. In case of disasters (e.g., cyberattack, natural disaster), IT administrators can restore data from either the NAS or AWS S3 storage systems.

# 5.0 Conclusion

This infrastructure report provides foundational strategies and planning for the digital transformation company, ITransformer Pty. Ltd. By matching hardware, software, and printing/scanning requirements to specific needs of each department, the company can improve performance across all departments. The hybrid server approach allows the company to maintain a balance between security, reliability, and flexibility, while managing costs effectively. The network structure also benefits the company by providing solid connectivity for stable communication and collaboration between the two offices. The robust backup strategy protects the company’s critical data from loss and ensures quick recovery in case of disaster. Regular testing and clear responsibilities for IT administrators help ensure that the company’s disaster recovery plan stays updated and maintains stability and security of overall systems. This infrastructure provides the company an efficient and secure ICT foundation that will support future growth and stable operations.

# Reference

Amazon Web Services. (n.d.). *Incremental vs Differential Backup - Difference Between Data Backup Strategies - AWS*. https://aws.amazon.com/compare/the-difference-between-incremental-differential-and-other-backups/

Apple. (n.d.). *iMac*. https://www.apple.com/au/imac/

Carnegie, J. (2023, January 25). *What Is a CMS and Why Every Business Needs It*. Thirtyfour Creative. https://www.thirtyfourcreative.com.au/thinking/what-is-a-cms-and-why-every-business-needs-it

Cloudlaya. (2025, July 24). *Crack the EC2 vs S3 Mystery: Make Smarter Cloud Decisions Today*. https://www.cloudlaya.com/blog/ec2-vs-s3-difference/

Donnelly, J. (2023, March 3). *NAS VS. RAID Storage. What’s The Difference?*. MASV. https://massive.io/file-transfer/nas-vs-raid/

HP. (n.d.-a). *HP 23.8 inch All-in-One Desktop PC 24-cr0009a*. https://www.hp.com/au-en/shop/hp-all-in-one-24-cr0009a-pc-94a65pa.html

HP. (n.d.-b). *HP Laptop 15.6 inch 15-fd0233TU, Black*. https://www.hp.com/au-en/shop/hp-laptop-15-fd0233tu-9t0k1pa.html?facetref=67ecd6eec5033cd4

HP. (n.d.-c). *HP Pavilion x360 14 inch 2-in-1 Laptop 14-ek1097TU, Silver*. https://www.hp.com/au-en/shop/hp-pavilion-x360-2-in-1-laptop-14-ek1097tu-942h0pa.html?facetref=01724004e96d825f

MetricStream. (n.d.). *All You Need to Know on Testing Disaster Recovery Plans*. https://www.metricstream.com/all-you-need-to-know-testing-disaster-recovery-plans.html

Microsoft. (2024a). *Learn about securing and protecting email messages in Outlook - Microsoft Support*. https://support.microsoft.com/en-au/office/learn-about-securing-and-protecting-email-messages-in-outlook-2baf3ac7-12db-40a4-8af7-1852204b4b67

Microsoft. (2024b, July 19). *Discover Universal Print*. https://learn.microsoft.com/en-au/universal-print/discover-universal-print

Pavlovic, D. (2024, August 29). *Printer Buying Guide: How to Choose the Best Printer for You*. HP. https://www.hp.com/us-en/shop/tech-takes/printer-buying-guide

PivIT Global. (n.d.). *Ultimate Guide to Site-to-Site VPN Technologies on Cisco ASA*. https://info.pivitglobal.com/resources/site-to-site-vpn-on-cisco-asa

Pronet Technology. (2023, August 29). *How often should I back up my data?.* https://www.pronet.com.au/insights/how-often-should-i-back-up-my-data

Teal Labs. (n.d.-a). *Which Tools Do Digital Transformation Specialists Use? - Software Career Guide*. Teal. https://www.tealhq.com/software/digital-transformation-specialist

Teal Labs. (n.d.-b). *Which Tools Do Legal Consultants Use? - Software Career Guide*. Teal. https://www.tealhq.com/software/legal-consultant
