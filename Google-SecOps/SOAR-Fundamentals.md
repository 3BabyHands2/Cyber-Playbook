# SOAR Fundamentals

- SOAR is the collection of disparate technologies that enable businesses to gather data and security alerts from different sources.

**SOAR combines three previously different technology sectors:**
- Orchestration and automation
- Threat Intelligence
- Incident Response

**How does Siemplify address SOAR?**
- Single workbench for the entire SOC
- Alert Grouping
- Power of ontology and mapping
- Playbook flexibility
- Automated reporting

***Siemplify Terms***
- Alert: Correlated events recieved by Siemplify
- Integration: Package of actions, connectors, and jobs for a specific product of services
- Connector: Part of integration. Siemplify component responsible for alert ingestion
- Action: Part of integration. Executs an API call to an external product or service
- Case: Container that stores all important investigation information consumed by a connector including events, alerts, notes, tasks, entities, and artifacts
- Entity: Alert main object of interest (i.e. hostname, username, source IP, etc.)
- Artifact: Alert secondary object of interst (i.e. file path, file hash)
- Event: Connector consumed data that are aggregated into alerts and can be levereged within playbooks to automate workflows
- Job: Part of integration. Acts as a scheduler and allows for a health check, sync
- Playbook: Workflow of actions or blocks, executed following a trigger
- Block: Sub-playbook with input and output parameters. Nested throughout various playbooks
- Trigger: Action that starts the playbok.

***High-Level Architecture***
![image](https://github.com/user-attachments/assets/072ffc00-5b29-4dae-82e3-c5c02838b480)


***On-Premise Architecture***

**Single Node**
![image](https://github.com/user-attachments/assets/5a71d320-5877-4626-bea6-875ac09164b7)

**Multi Node**
![image](https://github.com/user-attachments/assets/038eceb7-71c2-4555-889f-ce9dc8c1a938)

