# Intro to Cyber Threat Intel

***Threat Intelligence Classifcations***
- Strategic Intel: High-level intel that looks into the organisation’s threat landscape and maps out the risk areas based on trends, patterns and emerging threats that may impact business decisions.

- Technical Intel: Looks into evidence and artefacts of attack used by an adversary. Incident Response teams can use this intel to create a baseline attack surface to analyse and develop defence mechanisms.

- Tactical Intel: Assesses adversaries’ tactics, techniques, and procedures (TTPs). This intel can strengthen security controls and address vulnerabilities through real-time investigations.

- Operational Intel: Looks into an adversary’s specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets available in the organisation (people, processes and technologies) that may be targeted.

***CTI Lifecycle***
- Direction
  - Information assets and business processes that require defending.
  - Potential impact to be experienced on losing the assets or through process interruptions.
  - Sources of data and intel to be used towards protection.
  - Tools and resources that are required to defend the assets.
 
- Collection
  - Once objectives have been defined, security analysts will gather the required data to address them. Analysts will do this by using commercial, private and open-source resources available. Due to the volume of data analysts usually face, it is recommended to automate this phase to provide time for triaging incidents.
 
- Processing
  - Raw logs, vulnerability information, malware and network traffic usually come in different formats and may be disconnected when used to investigate an incident. This phase ensures that the data is extracted, sorted, organised, correlated with appropriate tags and presented visually in a usable and understandable format to the analysts. SIEMs are valuable tools for achieving this and allow quick parsing of data.
 
- Analysis
  - Investigating a potential threat through uncovering indicators and attack patterns.
  - Defining an action plan to avert an attack and defend the infrastructure.
  - Strengthening security controls or justifying investment for additional resources.

- Dissemination
  - Different organisational stakeholders will consume the intelligence in varying languages and formats. For example, C-suite members will require a concise report covering trends in adversary activities, financial implications and strategic recommendations. At the same time, analysts will more likely inform the technical team about the threat IOCs, adversary TTPs and tactical action plans.
 
- Feedback
  - The final phase covers the most crucial part, as analysts rely on the responses provided by stakeholders to improve the threat intelligence process and implementation of security controls. Feedback should be regular interaction between teams to keep the lifecycle working.

***CTI Standards & Frameworks***
- MITRE ATT&CK framework
- The Trusted Automated eXchange of Indicator Information (TAXII) = https://oasis-open.github.io/cti-documentation/taxii/intro
- Structured Threat Information (STIX) = https://oasis-open.github.io/cti-documentation/stix/intro
- Cyber Kill Chain
- The Diamond Model
- 


