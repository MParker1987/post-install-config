<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Configure Agents (workers)
- Configure Teams
- Configure Roles
- Configure Departments
- Configure Users (customers)
- Configure SLA (service-level agreement)
- Configure Help Topics

<h2>Configuration Steps</h2>

Agents
======

**Admin Panel > Agents > Agents**

<img src="https://www.techrepublic.com/wp-content/uploads/2023/01/osticketagentd-770x829.jpg"/>

Agents are given access to the help desk with the intent to respond and resolve the tickets. When adding an Agent to the help desk, they will need to be assigned to a Primary Department and given a Primary Role for the Tickets/Tasks routed to that department. Agents can be given Extended Access to additional departments of the help desk as well as assigned different Roles to those departments; this can be configured in the Access tab of the Agent’s Profile.

**Reset an agent’s password**

If necessary, administrators can manually reset an agent’s password by clicking the Set Password box in the middle of the Account page. This will produce a pop-up box with two options; the first is to send a password reset email to the agent. **Please note**, if the agent has not first set a password post-creation they can not reset said password. The second option for the admin is to uncheck the box which will populate fields to manually set a password for the agent. Once manually set, the admin will need to communicate this to the agent allowing them to log-in; the agent can be forced to reset the password upon logging in by keeping the box checked at the bottom left of the pop-up.

**Status and Settings**

  **Locked:** Agents who are Locked/Disabled are unable to log into the help desk. They will not be visible for assignment or auto assignments. Email alerts will not be sent to disabled agents as well.

  **Administrator:** Agents marked as “Administrators” simply have access to the Admin Panel are able to make global configuration changes to the help desk. All changes are effective moving forward and will not revert to previously configured settings. Agents with access to the Admin Panel can grant additional agents access to this panel for global configurations.

  **Limit ticket access to ONLY assigned tickets:** When this is checked these agents will only see tickets which are directly assigned to them as an agent or a team to which the agent belongs- regardless of department access. Once tickets are set to a status of a closed state, the assignment is released and the agent will lose access to these closed tickets; if the ticket is reopened, the agent could regain access if it is reopened assigned to them.

  **Vacation Mode:** Agents who are on vacation mode are able to log into the help desk but, like Locked/Disabled agents, they will not be visible for assignment or auto assignments and email alerts will not be sent to these agents as well. An agent can manually set themselves to Vacation Mode in their Profile or an agent with access to the Admin Panel. Vacation Mode must be manually enabled as well as disabled.

Agent Access
------------

Agents are given access to the help desk with the intent to respond and resolve the tickets. When adding an Agent to the help desk, they will need to be assigned to a Primary Department and given a Primary Role for the Tickets/Tasks routed to that department. Agents can be given Extended Access to additional departments of the help desk as well as assigned different Roles to those departments; this can be configured in the Access tab of the Agent’s Profile.

Fall back to primary role
For agents without department access which are granted access to tickets via Ticket Assignment/Ticket Referral, they will have Primary Role Permissions for tickets if this is checked. Otherwise, Agents will have a view only access to these tickets allowing them to post an internal note only.

**Agent Permissions**

  **Users**

   **Create:** Ability to add new users

   **Edit:** Ability to manage user information

   **Delete:** Ability to delete users

   **Manage Account:** Ability to manage active user accounts

   **User Directory:** Ability to access the user directory

  **Organizations**

   **Create:** Ability to create new organizations

   **Edit:** Ability to manage organizations

   **Delete:** Ability to delete organizations

  **Knowledgebase**

   **FAQ:** Ability to add/update/disable/delete knowledgebase categories and FAQs

  **Miscellaneous**

   **Banlist:** Ability to add/remove emails from banlist via ticket interface

   **Search:** See all tickets in search results, regardless of access

   **Stats:** Ability to view stats of other agents in allowed departments


Teams
=====

**Admin Panel > Agents > Teams**

<img src="https://forum.osticket.com/assets/files/migrated/FileUpload/2e/ed9a6350b2d54aa97c582b0acbebb2.png"/>

**How to Create Teams In Your Help Desk**

  Teams allow you to pull Agents from different Departments and organize them to handle a specific issue or user via a Help Topic or Ticket Filter.

  Having Agents from different Departments assigned to a Team will supersede the parameters of the Agents’ Department rules. For example, you can create a Help Topic associated with a particular product you produce, and assign it to a Team of specialist Agents from different Departments.

  To create a Team in your Admin Panel, locate the Agents tab, and click on Teams. Then click Add New Team on the right, and fill out the appropriate information. Then you will be able to add Agents to the team by clicking on their name from your list of Agents and checking the corresponding box next to the Team name you wish to add them at the bottom of the page.

  A Team can have an appointed leader who can receive Alerts & Notices separate from other team members. In order to set a Team Leader you can choose an Agent from the Team Lead dropdown when creating a Team or Editing an existing Team.



Roles
=====

**Admin Panel > Agents > Roles**

<img src="https://camo.githubusercontent.com/4085a6be24037532d7773a21c2724bb95b1b9aecc0c87e69ce5b7bfd7801d4f8/68747470733a2f2f692e696d6775722e636f6d2f4a773445624d4e2e706e67"/>

Roles are the permissions granted to Agents per Department that they have access to. Each Role has a set of permissions that can be checked/unchecked for agents given that Role in association with a Department they have access to. An unlimited number of roles can be created and assigned to Agents with access to various departments.

**Role Permissions for Tickets include:**

  **Assign:** Ability to assign tickets to agents or teams

  **Close:** Ability to close tickets

  **Create:** Ability to open tickets on behalf of users

  **Delete:** Ability to delete tickets

  **Edit:**  Ability to edit tickets

  **Edit Thread:** Ability to edit thread items of other agents

  **Link:** Ability to link tickets

  **Mark as Answered:** Ability to mark a ticket as Answered/Unanswered

  **Merge:**  Ability to merge tickets

  **Post Reply:**  Ability to post a ticket reply

  **Refer:**  Ability to manage ticket referrals

  **Release:** Ability to release ticket assignment

  **Transfer** Ability to transfer tickets between departments

**Role Permissions for Tasks include:**

  **Assign:** Ability to assign tasks to agents or teams

  **Close:** Ability to close tasks

  **Create:** Ability to create tasks

  **Delete:** Ability to delete tasks

  **Edit:** Ability to edit tasks

  **Post Reply:** Ability to post task update

  **Transfer:** Ability to transfer tasks between departments

**Role Permissions for the Knowledge Base include:**

  **Premade:** Ability to add/update/disable/delete canned responses

If granted access to the Admin Panel, that Agent will have the ability to make changes in the configurations of the help desk. From the Agent tab of the Admin Panel, the configurations of each Agent of the help desk can be modified, including the ability to Limit an Agent’s access to only tickets that are specifically assigned to them.

The Permissions tab of the Agent profile allows the Agent functionality within the help desk which are not Department specific access items. Areas such as the User Directory, Organization, and Knowledge Base can be limited per Agent. This includes the ability to search for and see the ticket metadata for tickets the Agent does not have access to, the email ban list, and other staff statistics on the dashboard.



Departments
===========

**Admin Panel > Agents > Departments**

<img src="https://docs.osticket.com/en/latest/_images/archives_dept_edit1.png"/>
Since tickets are routed through Departments in the help desk, there are many settings that can be set for each Department.

**Department Information:**

  **Parent:**  If nesting departments, this is the Parent Department to nest the department under. Please note: If an agent has access to the Parent Department, they will see the tickets of nested or child departments also, but access does not extend from child departments to Parent Departments.

  **Status:** The status of the department will determine its visibility as well as if tickets can be routed to that department.

    **Active:** The department is available when transferring tickets.

    **Archived:** The department is no longer in use and cannot be selected to transfer any ticket. Also, if tickets in that department are reopened via an End-User response it will create a new ticket referencing the original ticket number and subject line but the department will be the system default.

    **Disabled:** Tickets can no longer be transferred to this department and any tickets set up to be auto routed to this department will now be routed to the default department in the Helpdesk. Closed tickets in this department will reopen if the End-User responds.

  **Name:** Department name as it will be displayed throughout the helpdesk.

  **Type:** Select Private if you wish to mask assignments to this Department in the Client Portal. Additionally, when labeled as Private, the **Department Signature** will not be displayed in email replies. At least one department of the help desk must be Public.

  **SLA:** Service Level Agreement for tickets routed to this Department. This the expected amount of time (in hours) that a ticket is expected to be closed once opened. If the ticket is not closed in the allotted amount of time, it will then be Overdue.

  **Schedule:** Schedule is used by the Service Level Agreement when rendering tickets routed to this Department. This setting takes precedence over System and SLA schedule settings.

  **Manager:** Electively, select a Manager for the departments of the help desk. Managers can be configured to receive special alerts.

  **Ticket Assignment:** Enable this to restrict ticket assignment to include only members of this Department. Department membership can be extended to based on Agent’s Department Access, if **Alerts & Notices Recipients** includes those with department access.

  **Claim on Response:** Check this to **disable** auto-claim on response/reply for this department. Agents can still manually claim unassigned tickets.

  **Reopen Auto Assignment:** Check this to disable auto-assignment of reopened tickets for this department. Otherwise, the Ticket will be auto assigned to the last responding Agent.

**Outgoing Email Settings:**

  **Outgoing Email:** Email Address used when responses are sent to Users when Agents post Responses to Tickets.

  **Template Set:** Email **Template Set** used for Auto-Responses and Alerts & Notices for tickets routed to this Department. Template sets can be cloned and edited for department use in the Admin Panel > Emails > Templates.

**Auto Responder Settings:** This allows you to override the global Autoresponder settings for this Department.

  **New Ticket:** If checked, this will disable the New Ticket Auto-Response sent to the User
  when a new ticket is created and routed to this Department.

  **New Message:** If checked, this will disable the Auto-Response sent to the User to confirm a newly-posted message for tickets in this Department.

  **Auto-Response Email:** Select an email address from which Auto-Responses are sent for this Department; this email would send only auto-response messages, not Agent responses.
