<a name="readme-top"></a>

# Capstone Project

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://www.4guyscoffee.co/" target=”_blank”>
    <img src="HTDOCS/img/logo2.png" alt="logo" style="width: 40%; height: auto;">
  </a>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#disclaimer">Disclaimer</a></li>
    <li><a href="#executive-summary">Executive Summary</a></li>
    <li><a href="#background">Background</a></li>
    <!-- <li><a href="#progress">Progress</a></li> -->
    <li><a href="#networking--it-infrastructure">Networking & IT Infrastructure</a></li>
    <!-- continue from here for TOC -->
    <li><a href="#windows-server-administration">Windows Server Administration</a></li>
    <li><a href="#secure-cloud-environment">Secure Cloud Environment</a></li>
    <li><a href="#cybersecurity-fundamentals">Cybersecurity Fundamentals</a></li>
    <li><a href="#ethical-hacking-&-pentesting">Ethical Hacking & Pentesting</a></li>
    <li><a href="#cybersecurity-operations">Cybersecurity Operations</a></li>
    <li><a href="#cybersecurity-forensics">Cybersecurity Forensics</a></li>
    <li><a href="#cybersecurity-grc">Cybersecurity GRC</a></li>
    <li><a href="#conclusion">Conclusion</a></li>
    <li><a href="#team-members">Team Members</a></li>
    <li><a href="#built-with">Built With</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
    <li><a href="#references">References</a></li>
  </ol>
</details>


## Disclaimer

The company mentioned in this document, "4GuysCoffee," is entirely fictitious and has been created for the purpose of this project. Any resemblance to real entities, living or dead, is purely coincidental.

This project serves as a demonstration of our capabilities in utilising the tools, frameworks, and methodologies learnt during our course of study. While the company and its operations are fictional, the techniques and practices showcased herein reflect our proficiency in applying theoretical knowledge to practical scenarios.

The solutions presented in this project are intended for educational and illustrative purposes, showcasing our skills and understanding of industry-standard tools. The applicability of these techniques in real-world scenarios is subject to specific business requirements, security considerations, and best practices relevant to actual organisational settings.

This project should not be misconstrued as representing the operations, strategies, or policies of any existing or potential real-world entities. The goal is to highlight our ability to implement and integrate various technologies in a manner that could be replicated and adapted in professional environments.

Readers are encouraged to consider the context of this project as a simulated exercise, aimed at demonstrating our commitment to continuous learning and the practical application of knowledge in the field of IT.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Executive Summary

4GuysCoffee, a Singapore-based small and medium enterprise, is a premier destination for exceptional coffee experiences. Operating exclusively within the dynamic city-state of Singapore, we curate an exquisite selection of premium coffee beans sourced from diverse countries, ensuring a rich and high-quality offering. Our local facility in Singapore meticulously roasts and processes these beans, packaging them for sale and use in our six cafes spread across the city-state.

This detailed report navigates through the intricacies of our network infrastructure, which was strategically designed at our Singapore headquarters and empowered by cutting-edge tools from Cisco. Our deployment encompasses advanced configurations of switches, routers, and access points, ensuring impeccable connectivity and performance. To elevate organisational efficiency, we have implemented a sophisticated network design, utilising subnets and Virtual Local Area Networks (VLANs) to segregate departments within our headquarters. This fortifies network security and streamlines data traffic, optimising overall network management.

Embracing the cloud for scalability and adaptability, we have established a robust web server through an Elastic Compute Cloud (EC2) instance on Amazon Web Services (AWS). This cloud-centric approach guarantees reliable web hosting capabilities. Our identity management system revolves around Windows Active Directory at our Singapore headquarters, providing a centralised and secure means of user authentication and authorisation. Concurrently, an on-premise local file server facilitates seamless collaboration among our internal teams. We have incorporated an AWS file server to expand our data storage capabilities, exploring diverse storage solutions like Amazon S3 for off-site backup, enhanced data redundancy, and accessibility.

To meet the operational requirements of our cafe managers, we have implemented a dedicated PC setup in our 4GuysCoffee cafes. Through a secure Virtual Private Network (VPN) connection, branch managers can access the file server at the headquarters, facilitating swift retrieval of Point of Sale (POS) materials and critical information. This strategic integration of networking tools, cloud services, and on-premise solutions underscores 4GuysCoffee's commitment to establishing a resilient and efficient IT infrastructure aligned with our organisational goals. It is tailored to support seamless operations within Singapore's dynamic and thriving coffee scene.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Background

4GuysCoffee, a thriving small and medium enterprise headquartered in Singapore, has made a significant mark in the competitive and dynamic coffee industry. Our commitment to delivering exceptional coffee experiences is evident in our focus on using ethically sourced and sustainably grown beans, which are meticulously roasted and packaged in a local facility. This emphasis on sustainability aligns with the growing consumer demand for ethically sourced and environmentally friendly products in the global coffee market.

The company's cafes serve as more than just retail spaces; they are vibrant hubs that offer a diverse range of specialty coffees, providing customers with a unique and memorable coffee culture experience. Whether it is the aromatic blends, distinct brewing techniques, or the ambience of our cafes, 4GuysCoffee has carved a niche for itself in an industry where quality and innovation are paramount.
In addition to its physical presence, 4GuysCoffee has ventured into the digital realm by launching a global e-commerce store. This strategic move allows us to reach coffee enthusiasts worldwide, offering our signature roasted coffee beans for sale online. This expansion into e-commerce reflects the company's adaptability and recognition of evolving consumer preferences, especially when online shopping for speciality products has become increasingly popular.

### Ficticious SME Profile:
* Name of the SME: 4GuysCoffee
* Industry: In the dynamic coffee industry, 4GuysCoffee faces challenges such as intense competition, navigating a complex supply chain for sourcing sustainable beans, staying attuned to rapidly evolving consumer trends, and potential impacts from global economic fluctuations. However, the company is well-positioned to capitalise on promising prospects. The expanding global coffee culture, with an increasing appreciation for speciality and artisanal offerings, allows 4GuysCoffee to distinguish itself. The recent launch of our e-commerce store aligns with the rising trend of online shopping for speciality products, offering access to a broader global customer base. By maintaining a commitment to sustainability and locally sourced beans, the company aligns with the growing consumer demand for eco-friendly and socially responsible products. Moreover, opportunities for innovation in brewing techniques and flavour profiles and the cultural diversity of operating in multiple countries present avenues for growth and enhanced market appeal. Navigating these challenges while leveraging these prospects requires a strategic and adaptable approach, positioning 4GuysCoffee for continued success in the evolving global coffee landscape.


<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Networking & IT Infrastructure

### Overview

This section provides an overview of the network infrastructure implemented at 4GuysCoffee. The full report, that can be found [here](readme-docs/Networking%20%26%20IT%20Infrastructure.pdf), highlights the key features of the network design, emphasising its focus on scalability, reliability, and cost-effectiveness. We explore the hierarchical structure employed at the headquarters and the rationale behind the simpler design used in branch locations. The report delves into the specific technologies and protocols utilised within the network, including VLANs, OSPF routing, and security measures like HSRP and RADIUS server authentication. Finally, the report examines the configuration of the Wireless LAN Controller (WLC) and its role in managing the network's access points.


#### Network Design & Architecture

4GuysCoffee's network architecture leverages a best-in-class approach,
adopting a 3-tier hierarchical design for the headquarters and a simpler design for the branches. This aligns with industry best practices for creating dependable, scalable, and cost-efficient networks. The hierarchical structure facilitates clear separation of functionalities, enhancing overall network reliability and manageability.

#### Distribution & Core Layer

The network boasts a robust and resilient architecture featuring a centralised HQ router complemented by two multilayer switches. These switches enable efficient inter-VLAN routing and offer redundancy through HSRP configuration. Additionally, an EtherChannel optimises bandwidth and load balancing, significantly boosting network performance. The strategic implementation of subnets and VLANs establishes a multi-layered security approach, safeguarding against vulnerabilities at both Layer 2 and Layer 3.

To accommodate future growth, subnet selection adheres to Cisco's addressing guidelines, incorporating VLSM to allocate adequate space for expansion (/16 and /24 for HQ and departments). The network prioritises Layer 2 security with measures like PortFast, BPDUguard, and port security, fortifying the network against potential attacks. OSPF routing, known for its compatibility with diverse network environments, is employed instead of EIGRP.  RADIUS server authentication strengthens WLAN security by requiring users to have unique login credentials. Secure site-to-site connections are established using IPSec VPNs.

#### WLC Configuration & RADIUS Server Authentication

A scalable Wireless LAN Controller (WLC) manages the WLAN infrastructure, allowing for seamless expansion as needed. The WLC provides an additional layer of security by offering centralised AP deployment, rogue device detection, and network protection through a firewall. Furthermore, a RADIUS server necessitates login credentials for staff users accessing the office Wi-Fi network, adding another layer of access control.


<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONT FROM HERE -->

## Windows Server Administration

### Microsoft Active Directory

The section is an excerpt of our report that provides an in-depth guide to our strategic approach in implementing Microsoft Active Directory (AD), outlining the detailed procedures undertaken to establish a secure and resilient directory service within our organisation. 

The implementation of AD is crucial for building a centralised and systematically organised network, efficiently managing user accounts, facilitating resource access, and ensuring a secure and scalable operational environment. We have implemented stringent measures to proactively mitigate potential threats, safeguard sensitive information, and uphold system integrity. Our dual-server approach highlights our commitment to delivering a seamless and secure digital ecosystem.

Each cafe is equipped with a dedicated PC setup for branch managers, who can securely access the central file server at the head office via a Virtual Private Network (VPN). This infrastructure ensures swift retrieval of Point-of-Sale (POS) materials and other critical information, fostering a cohesive and responsive network environment.

### AD Installation

Active Directory Domain Services (AD DS) is essential in Windows Server environments, providing critical functionalities and benefits. An [installation video](https://www.youtube.com/watch?v=k5VWd_0uTiQ&t=0s) documents the steps to ensure proper AD DS operation.

#### Importance of Active Directory:

Our adoption of Active Directory aims to streamline and enhance our internal IT infrastructure. Active Directory simplifies user management, providing a centralized platform for authentication, authorization, and configuration management. With AD in place, we anticipate improved security, reduced administrative overhead, and enhanced productivity as employees gain simplified access to network resources.

#### Securing Active Directory:

Ensuring the security of our Active Directory environment is paramount. We have implemented several strategies, including enforcing Group Policy Objects (GPOs) for password policies and user rights assignments, configuring strict firewall rules, and regularly updating and patching systems to address vulnerabilities. Additionally, we have disabled SMB1 and LLMNR, utilized non-standard port configurations for Remote Desktop Protocol (RDP), and implemented physical security measures for servers housing domain controllers.

For the full detailed report, please refer to [this link](readme-docs/Windows%20Server%20Administration.md).

<p align="right">(<a href="#readme-top">back to top</a>)</p>




#### Linux Server Administration

Securing a Linux server involves a series of fundamental steps to fortify its defenses against potential threats and vulnerabilities. It is crucial to keep the system software and applications up-to-date by regularly applying security patches. Implementing strong password policies and ensuring that only necessary services are running help reduce the attack surface. Disabling unnecessary user accounts and employing multi-factor authentication further strengthens access controls.

Additionally, configuring firewalls, such as iptables, to control incoming and outgoing traffic enhances network security. Restricting access through the use of SSH keys rather than passwords adds an extra layer of protection. Regularly auditing and monitoring system logs provide insights into potential security incidents, enabling timely response and mitigation.

The benefits of hardening a Linux server are multifaceted. Enhanced security measures reduce the risk of unauthorized access, data breaches, and potential disruptions. By minimising unnecessary services and tightening access controls, the attack surface is diminished, making it more challenging for malicious actors to exploit vulnerabilities. Regular system audits contribute to early threat detection and allow for proactive measures to maintain the integrity and reliability of the server. In essence, the hardening process is an essential practice for safeguarding the server's overall stability and protecting sensitive information from potential cyber threats.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ROADMAP -->
## Cybersecurity

This section contains excerpts from our Annual Cybersecurity Report. To view the detailed report, click [here](HTDOCS/doc/cs-report.pdf).

### Background & Scope

In light of 4GuysCoffee's global success in the coffee industry, the company acknowledges the increasing risk of cyberattacks. The expansion into e-commerce has exposed vulnerabilities, particularly to <strong>digital skimming</strong> and related threats. To bolster defence measures, a comprehensive cybersecurity approach is embraced. This strategy, incorporating employee training, continuous security assessments, robust encryption, and expert collaboration, aims to fortify resilience against evolving digital threats. This report reflects the company's steadfast commitment to safeguarding its digital assets. It delves into common cybercrimes, presents case studies, identifies potential weaknesses, and outlines concrete steps to mitigate risks like digital skimming. By adopting these preventative measures, the company safeguards not only its digital storefront but also the trust and security of its valued customers.

### Digital Skimming

Digital Skimming, identified as a significant cybersecurity threat by Visa's Biannual Threats Report of 2022, involves cybercriminals injecting malicious code into a merchant's website. This code targets checkout pages to harvest payment account details and personally identifiable information. Such attacks exploit misconfigurations or inadequate security controls, allowing cybercriminals to deploy the skimming code successfully. Also known as Magecart attacks, digital skimming involves covertly inserting malicious code into payment processing pages to capture sensitive customer information, such as credit card details, during online transactions.

#### Impacts & Consequences

As reported by Visa, the evolution of digital skimming tactics poses severe consequences. Cybercriminals can gain control over e-commerce platforms, harvesting payment account data and compromising customers' financial information. The aftermath of a successful digital skimming attack extends beyond financial losses, eroding customer trust and tarnishing the company's reputation. Individuals face the risk of unauthorised charges, fraudulent transactions, and potential identity theft. Meanwhile, affected businesses may incur fines, legal repercussions, and operational disruptions, leading to revenue loss.

#### Trend Analysis

The digital payment market is experiencing significant growth, driven by the widespread adoption of digital payments in online shopping. This growth is propelled by factors such as smartphone ubiquity, fast internet connectivity, and consumer preference for digital payments. However, this surge also increases exposure to e-skimming threats, posing challenges for detection and mitigation. Attackers continually refine their strategies, exploiting vulnerabilities such as misconfigured access controls on cloud platforms like Amazon S3.

### Case Study 1: British Airways Magecart Attack

In 2020, British Airways fell victim to a sophisticated Magecart attack, compromising sensitive customer payment details on its website's checkout page. Despite swift action to contain the breach, customer data was compromised, leading to significant repercussions under GDPR regulations. This incident underscores the threat posed by digital skimming attacks to businesses and highlights the importance of robust cybersecurity measures.

#### How Magecart Attacks Could Affect 4GuysCoffee

The potential for a Magecart attack poses a significant threat to 4GuysCoffee's online operations. Similar to British Airways' experience, the company's login and checkout pages could be targeted, compromising customer data and damaging the company's reputation. The clandestine nature of Magecart attacks makes them difficult to detect, necessitating proactive security measures to mitigate risks effectively.

#### Suggested Controls & Mitigation

To address the growing threat of Magecart attacks, 4GuysCoffee recommends implementing proactive security measures. These include regularly inspecting code for vulnerabilities, updating login credentials, securing cloud resources, and deploying web application firewalls. Additionally, proactive measures such as penetration testing and maintaining multi-layered security systems are crucial for thwarting intrusions and protecting customer data.

### Case Study 2: Starbucks Data Breach

In September 2022, Starbucks Singapore experienced a data breach affecting approximately 330,000 customers. The breach involved the unauthorized access and theft of customer data stored in a CRM system, highlighting vulnerabilities in data management and access controls. This case study underscores the importance of robust security policies and proactive measures to mitigate the risks of data breaches.

#### Overview of the Data Breach

The Starbucks Singapore data breach occurred due to vulnerabilities in the organization's CRM system and web platform. Weak access controls, lack of encryption, and insufficient detection measures contributed to the breach, resulting in the theft of sensitive customer information. Prompt action was taken to address the breach and notify affected customers, but significant challenges remain in strengthening data security measures.

#### Attack Vectors

The data breach was facilitated by several vulnerabilities, including weak access management, lack of encryption, and inadequate detection measures. These vulnerabilities allowed malicious actors to gain unauthorized access to customer data and exploit weaknesses in the organization's security infrastructure. Strengthening access controls, implementing encryption, and enhancing detection measures are essential for mitigating future risks.

#### Solutions

To mitigate the risks of data breaches, 4GuysCoffee recommends implementing comprehensive security policies and proactive measures. These include implementing multi-factor authentication, enforcing password hygiene protocols, and enhancing access management controls. Additionally, regular security audits, encryption of sensitive data, and improved detection measures are essential for maintaining robust data security practices. By adopting these solutions, organizations can strengthen their cybersecurity posture and protect against future data breaches.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Progress

- [x] Add Background Information
- [x] Add Networking contents
- [x] Add AWS contents
- [ ] Add AWS screenshots
- [x] Add Active Directory contents
- [x] Add Linux contents
- [ ] Add Linux screenshots
- [x] Add Cybersecurity contents
- [ ] Add M5 contents
- [ ] Add M7 contents
- [ ] Add M6 contents
- [ ] Add M8 contents

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!--


## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

-->

<!-- CONTACT -->
## Team Members

<!-- * Andrew - [@x](https://twitter.com/x) - email@x.com -->
* [Brendan](https://) - email@x.com
* [Hud](https://) - email@x.com
* [Shafeeq](https://sg.linkedin.com/in/shafabdultalib) - shaf.abdul@outlook.com

<p align="right">(<a href="#readme-top">back to top</a>)</p>




## Built With

These are the frameworks, resources and languages used throughout the project.

* [![Apache][Apache]][Apache-url]
* [![AWS][Amazon-AWS]][AWS-url]
* [![Bash][Bash]][Bash-url]
* [![Canva][Canva]][Canva-url]
* [![Cisco][Cisco]][Cisco-url]
* [![CSS][CSS]][CSS-url]
* [![Github][Github]][Github-url]
* [![HTML][HTML]][HTML-url]
* [![JS][JS]][JS-url]
* [![JSON][JSON]][JSON-url]
* [![MariaDB][MariaDB]][MariaDB-url]
* [![Markdown][Markdown]][Markdown-url]
* [![NPM][NPM]][NPM-url]
* [![PHP][PHP]][PHP-url]
* [![Powershell][Powershell]][Powershell-url]
* [![Redhat][Redhat]][Redhat-url]
* [![VMWare][VMWare]][VMWare-url]
* [![VS][VS]][VS-url]
* [![Windows][Windows]][Windows-url]



<p align="right">(<a href="#readme-top">back to top</a>)</p>




<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

We would like to extend our sincere gratitude to the following organisations and its people whose invaluable support and expertise have played a pivotal role in shaping and enriching our journey throughout the development of this project. 

This project would not have been possible without the collective effort, support, and knowledge shared by these entities. Thank you for being instrumental in the successful execution of this endeavor.

* [VISA](https://www.visa.com.sg)
* [IMDA](https://www.imda.gov.sg/)
* [School of InfoComm Technology](https://www.np.edu.sg/schools-courses/academic-schools/school-of-infocomm-technology)
* [AWS](https://aws.amazon.com/)
* [Windows AD Knowledge Base](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
* [RHEL](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux)
* [GitHub Pages](https://pages.github.com)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## References

1. Lau, Deborah. “[The Big Read in Short: What’s Driving Singapore’s Coffee Craze?](https://www.todayonline.com/big-read/)” TODAY, November 4, 2023. big-read-short-whats-driving-singapores-coffee-craze-2297136 
2. “[Hierarchical Network Design](https://www.geeksforgeeks.org/hierarchical-network-design/).” GeeksforGeeks, November 17, 2022.
3. [IP addressing guide](https://www.cisco.com/c/dam/global/en_ca/solutions/strategy/docs/sbaBN_IPv4addrG.pdf) - Cisco. Accessed January 14, 2024.
4. [What is Amazon EC2?](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html) - Amazon Elastic Compute Cloud. Accessed January 14, 2024.
5. Canadian Centre for Cyber Security, Canadian Centre for Cyber Security (Cyber Centre). “[Practitioner Guidance for Securing Microsoft Active Directory Services in Your Organization](https://www.cyber.gc.ca/en/guidance/practitioner-guidance-securing-microsoft-active-directory-services-your-organization-itsp60100).” ITSP.60.100, December 12, 2023.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[Amazon-AWS]: https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white
[AWS-url]: https://www.aws.amazon.com 
[Cisco]: https://img.shields.io/badge/CISCO-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white
[Cisco-url]: https://learningnetwork.cisco.com/s/packet-tracer-alternative-lab-solutions
[Github]: https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white
[Github-url]: https://github.com/
[VMWare]: https://img.shields.io/badge/VMware-231f20?style=for-the-badge&logo=VMware&logoColor=white
[VMWare-url]: https://www.vmware.com
[Redhat]: https://img.shields.io/badge/Red%20Hat-EE0000?style=for-the-badge&logo=redhat&logoColor=white
[Redhat-url]: https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux
[Windows]: https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white
[Windows-url]: https://www.microsoft.com/en-us/windows
[JSON]: https://img.shields.io/badge/json-5E5C5C?style=for-the-badge&logo=json&logoColor=white
[JSON-url]: https://www.json.org/json-en.html
[VS]: https://img.shields.io/badge/VSCode-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white
[VS-url]: https://code.visualstudio.com/
[Markdown]: https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white
[Markdown-url]: https://www.markdownguide.org/
[Bash]: https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white
[Bash-url]: https://
[HTML]: https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white
[HTML-url]: https://
[CSS]: https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white
[CSS-url]: https://
[JS]: https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E
[JS-url]: https://
[PHP]: https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white
[PHP-url]: https://www.php.net
[PHP]: https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white
[PHP-url]: https://
[MariaDB]: https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white
[MariaDB-url]: https://mariadb.org
[Canva]: https://img.shields.io/badge/Canva-%2300C4CC.svg?&style=for-the-badge&logo=Canva&logoColor=white
[Canva-url]: https://www.canva.com
[Apache]: https://img.shields.io/badge/Apache-D22128?style=for-the-badge&logo=Apache&logoColor=white
[Apache-url]: https://www.apache.org
[NPM]: https://img.shields.io/badge/npm-CB3837?style=for-the-badge&logo=npm&logoColor=white
[NPM-url]: https://www.npmjs.com
[Powershell]: https://img.shields.io/badge/powershell-5391FE?style=for-the-badge&logo=powershell&logoColor=white
[Powershell-url]: https://www.microsoft.com
