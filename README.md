# Customer Support Ticket Priority Prediction and Automated Assignment System Using Agentforce

A Salesforce project that reads a support ticket's description, sets its priority (High, Medium or Low), and for urgent tickets creates a task and assigns a Senior Support Agent. Users interact with it through an Agentforce subagent.

**Vivekanandha College of Technology for Women [6130]**

## Team
| Name | Role |
|---|---|
| Hemavarni S | Team Leader |
| Keerthika V | Team Member |
| Monisha P | Team Member |
| Jhansirani Y | Team Member |

## Problem
Support teams receive many tickets every day, and sorting and assigning them by hand is slow. Urgent issues get delayed and customers become unhappy.

## Solution
The user gives an account name to Agentforce. An Auto-Launched Flow finds the latest ticket for that account, checks the description for keywords, and sets the priority:

| Priority | Description contains |
|---|---|
| High | urgent, not working, failure |
| Medium | issue, slow, delay |
| Low | none of the above |

For High priority tickets, the flow creates a task called "Urgent Ticket Handling" and assigns a Senior Support Agent. Agentforce then shows the priority, assigned agent, ticket Id and a message.

## Components
- **Custom object:** `Support_Ticket_Intelligence__c` (fields include Customer, Contact, Issue Type, Description, Priority Level, Status, Assigned To, SLA Breach Risk)
- **Auto-Launched Flow:** `Support_Ticket_Intelligence`
- **Agentforce subagent:** Support Ticket Priority Analysis
- **Agent action:** calls the flow, with `varAccountName` as input and five outputs

## Repository contents
| Folder / file | Contents |
|---|---|
| `Customer_Support_Ticket_Priority_Project_Document.pdf` | Full project document |
| `Screenshots/` | Screenshots of each step |
| `force-app/` | Salesforce source files (object, fields, flow) |
| `manifest/package.xml` | Metadata list used to retrieve the source |

## Demo video
<paste your video link here>

## Future scope
SLA breach-risk check, more priority rules, deeper analytics, and more assignment rules.
