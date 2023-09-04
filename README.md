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

.. image:: ../../_static/images/admin_agents_roles.png
  :alt: Roles Tab

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
