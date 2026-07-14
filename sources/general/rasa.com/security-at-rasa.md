# Source: https://rasa.com/security-at-rasa

# Security at Rasa

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ef7d58530b1791a344b245_general%20header.avif)

## Introduction

We are a mid-sized company serving some of the world's largest brands. This means that every single one of us takes our security responsibilities seriously.

When it comes to information security, we combine the approach of defence in depth as well as Kerckhoff’s Principle (which states that a cryptosystem should be secure, even if everything about the system, except the key, is public knowledge). That is to say that, we believe information security is a broad domain that requires multiple approaches but it should be transparent and straightforward.

We have put together this page to provide information on the security controls we put in place in an effort to achieve confidentiality, integrity and availability of our information assets. Should you require further information, please don’t hesitate to reach out to us at [security@rasa.com](mailto:security@rasa.com)

Although our controls are aligned with the requirements of ISO 27002, we have broken down the sections below to align with the ISO 27001 domains to allow for our customers and prospects to easily cross reference with their requirements as well as demonstrate our commitment to implementing industry best practices across our organization.

## Information Security Policies

**Objective:** To ensure that our information security policies align with the needs of our organization.

**Controls:** We have implemented certain information security policies here at Rasa. These information security policies help us define our usage of systems/applications and are regularly reviewed and updated with a frequency no less than once a year. The policies include:

- Access Control and IAM Policy
- Acceptable Use Policy
- Application Security Policy
- Asset Management Policy
- Physical Security Policy
- Secure Configuration Policy
- Threat and Vulnerability Management Policy
- Use of Cryptography Policy
- Security Incident Management Policy
- Information Transfer and Data Handling Policy
- Vendor Management Information Security Policy
- Change Management Policy
- Log Retention Policy
- Cloud Services Policy

## Organization of Information Security

**Objective:** To ensure the management and implementation of our information security controls aligns the needs of the organization.

**Controls:** Information security roles and responsibilities are defined, documented and have been communicated across the organization. Everyone at Rasa is fully committed to their role and embraces honest and transparent conversations when it comes to security.

## Human Resources Security

**Objective:** To ensure that all employees (full-time, part-time and contract) understand their requirements before, during and after their term of employment. This includes conducting background checks, adhering to information security policies and attending necessary training.

**Controls:** All employee contracts include:

- Non-disclosure agreements
- Terms and conditions of employment
- Responsibilities after termination or change of employment.

Furthermore, employee screening such background checks and other checks are done for employees that meet the required criteria in accordance with the law.

We have also implemented a Security Awareness Program to provide regular security training in the form of digests, lunch and learns, technical training, etc.

## Asset Management

**Objective:** To identify, classify and prevent the disclosure of Rasa’s information and assets.

**Controls:** Asset management is one of the most important and fundamental controls when it comes to information security. We understand this at Rasa and have put together an asset register with key information on the assets and their owners. This is regularly reviewed and updated.

Some key things to note:

- We do not have any on-premise servers. All our applications are cloud based/managed.
- We do not host any customer data, systems or applications.
- We are a fully remote company.
- Our device estate is entirely Macbooks.
 - We make use of Apple Business Manager and an MDM to manage security policies on devices.
 - Devices are updated regularly with an automatic frequency for minor and micro releases. Major releases are reviewed and tested prior to the rollout due to the complications that come with these types of releases.

## Access Control

**Objective:** To prevent the unauthorised disclosure of information and ensure non-repudiation.

**Control:**

- Multi-factor authentication is enforced throughout the company.
- Yubico’s hardware security keys are enforced as the only method of verification for our IdP service.
- SSO with our identity provider is enabled across all major applications.
- The principle of least privilege is employed for all major applications.
- The use of shared accounts is strictly prohibited.
- Elevated privileges are limited and the principle of least privilege is always applied.
- Production and staging accounts are segregated; with each squad getting their own separate accounts.

## Cryptography

**Objective:** To maintain confidentiality, integrity and authenticity of critical assets through encryption and key management.

**Controls:**

- _Cipher Selection:_ We will only use ciphers that are recommended by the National Institute of Standards and Technology (NIST). The recommended ciphers include AES, RSA, and SHA. Other trusted sources may be used for selecting ciphers for specific purposes, such as OWASP for selecting an algorithm for hashing passwords in an application.
- _Key Lengths:_ We will use key lengths that are appropriate for the selected cipher. The recommended minimum key lengths are 128-bit for AES, 2048-bit for RSA, and 256-bit for SHA.
- _Key Management:_ We will implement strong key management practices to ensure the confidentiality and integrity of our cryptographic keys. This includes using strong passwords and ensuring that cryptographic keys are stored securely.
- _Algorithm Configuration:_ We will configure our cryptographic algorithms according to best practices recommended by the Center for Internet Security (CIS) or OWASP depending on the context of the usage. This includes disabling weak cryptographic algorithms and enabling strong cryptographic protocols.
- _Cryptographic Usage:_ We will only use cryptography for the intended purpose and will not use it to circumvent security controls or engage in any illegal or unethical activities.

## Physical and Environmental Security

**Objective:** To prevent unauthorised access to information that may cause loss or interruption to operations.

**Controls:** As we are a fully remote company, we do not have offices that are used daily. We do have an office site that can be used from time to time. The following security measures are in place:

- The physical keys 🔑 of the main entrance of the building are limited and are only with the Ops team and MD - this limits the access to the office space outside the working hours
- Access to the office is via a state of the art electronic smart lock. Its security features include
 - Allocating & Controlling the rights to enter the office by the admin
 - Remotely monitoring the entrance and exit activity
 - Remotely checking the current status of the door at any time - if its open or closed
- Visitors to the office are allowed with prior permissions only.
- Bi annual inspection of all Electric and electronics is done to ensure safety of the Macs, servers, switches and monitors from fire, electrical surges, etc
- There are certified fire fighting equipment & trained office staff to handle emergencies like Fire
- Security audits are conducted to identify and address any vulnerabilities by our external Data Protection agencies.
- Spare laptops are kept in this office. These devices:
 - are linked to our business account and are fully wiped.
 - have our MDM installed with security policies already in place.

It is important to note that this office is a small site with limited capabilities and isn’t used frequently.

## Systems Acquisition, Development and Maintenance

**Objective:** To ensure that information security requirements are established across the lifecycle of information systems and included when updating existing systems or implementing new systems.

**Controls:** We have implemented an Application Security policy that provides guidelines for

- Secure software development lifecycle (SDLC)
 - Best Practices within Rasa
- Access control and authentication
- Security testing and vulnerability management
- Incident response and recovery
- Third-party application security

Some _key_ things to note:

- All Github accounts have MFA enforced with the use of security keys enforced across our organization.
- We don’t host any customer instances and don’t host any customer data.
- Our product build pipelines are built in line with software security best practices and include multiple layers of security checks, including secret scanning, static code analysis and checks for dependency vulnerabilities.

## Supplier Relationships

**Objective:** To ensure that any valuable Rasa assets that can be accessed by suppliers remain protected, and maintain the required level of information security.

**Controls:** When onboarding new suppliers, the security team performs a vendor risk assessment. This is done by first collating relevant information from the vendors through the completion of the following:

- Vendor Information Security Risk Assessment
- Customer Cloud Access Security Requirements
- Data Processing Agreement
- External Party Cyber Security Requirements On completion of these documents, the team can assess the threat landscape and work with the vendors to identify and mitigate any high or critical risks.

## Information Security Incident Management

**Objective:** To ensure that information security incidents are managed effectively and consistently.

**Controls:** We have defined and implemented a detailed security incident management process. The process includes a detailed plan of action that includes detection and analysis steps, incident prioritisation, communication, notification, and escalation. It also includes a detailed containment strategy, direction on evidence handling and crisis management. A copy can be provided on request.

Some _key_ things to note:

- We have deployed and configured a Security Incident and Event Management (SIEM) platform. All security logs are forwarded to this platform with alerts set up as defined by use cases relevant to Rasa.
- Our Security Incident Management Process is aligned to NIST SP 800-61.

## Business Continuity Planning

**Objective:** To ensure the continuation of information security in respect to our Business Continuity/Disaster Recovery (BC/DR) plans.

**Controls:** We have implemented a Business Continuity and Disaster Recovery (BC/DR) plan. During the implementation, we performed a business impact assessment and identified key risk areas as well as key stakeholders. All relevant parties have been notified of their roles and responsibilities within the plan and a communication plan has been devised and disseminated accordingly.

Some _key_ things to note:

- All of our code is hosted by GitHub.
- We are not a SaaS application. No customer instance is hosted within our cloud environments.
- We do not host any customer data.
- We do not have any on-premise instances. All our applications are cloud based with each vendor complying to the necessary legal and/or regulatory requirements in relation to security, privacy and resilience.

## Compliance

**Objective:** To avoid information security breaches of a legal, statutory, regulatory or contractual nature and ensure that information security is carried out according to Rasa’s needs.

**Controls:** We have worked to ensure our security controls are aligned with ISO 27002 and we apply industry best practises wherever applicable. We are always happy to provide evidence to the case, on any controls relevant to us. Just reach out!

## Responsible Disclosure

Security is an ongoing process and we are always looking for ways to improve so feedback is really important to us. Although we do not have a monetary bug bounty program in place, we do have a 
[responsible disclosure policy](https://rasa.com/responsible-disclosure-policy/). Please review and feel free to reach out to us if you have any further questions.

## Questions?

Contact [security@rasa.com](https://rasa.com/security@rasa.com/) or visit [rasa.com](https://rasa.com/) for more information.

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)