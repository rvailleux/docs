{% hint style="info" %}
In order to send and/or receive notifications, you need first to activate them from the **Company** menu.

For multi-participants video-assistance, activate both:
- **ticket **AND - **conference **notifications
{% endhint %}

1. In the left-hand menu, click **Company** then, **Company account**.
2. Click the **Notifications** tab.
3. Click **Ticket notifications** to open the menu.
4. Click the **Switch** button to activate or deactivate the notifications. 
 
 ![](../../../.gitbook/assets/EN-Diag-portal-activate-ticket-notification.png)
5. Click **Save**.

{% hint style="success" %}
Your choices are saved.
{% endhint %}

![](../../../.gitbook/assets/Activer_notifs_tickets.gif)

| Name | Explanation | Actor triggering the notification | Notification recipient | Action triggering notification | Ticket status |
| --- | --- | --- | --- | --- | --- |
| Ticket approved | Notify the requester that a ticket has been created after an assistance request. | Agent | Requester | Prerequisite:
 
Subscribe to the **DIAG - Enterprise** offer
 -  A user fills in the assistance form.  -  The ticket is considered.  - An agent changes the ticket status into&#160;Approved.   | Open |
| Ticket assigned | Notify an agent that he has been assigned to a ticket. | Agent, administrator, or supervisor | Agent |  -  A user (administrator or supervisor) creates a ticket and assignes it to an agent. 
**or**
 A user assignes an old ticket to another agent.  -  The agent that is assigned receives a notification when the ticket is saved.   | No specific status |
| Assistance reminder invitation | Remind the agent and the requester that a video assistance is planned. | Agent | Agent/Requester | Prerequisite:
 
Create a ticket for a scheduled assistance session.
 -  The agent creates a new ticket with a date and an appointment hour. The agent adds a reminder to the invitation.  -  The requester and the agent receive a message x minutes (x = the time the agent defined when he created the ticket) before the beginning of the assistance session.   | New |
| New ticket request | Notify the supervisor that there is a new assistance request so he can open it and assign it to an agent. | User | Supervisor | Prerequisite: 
 
Subscribe to the **DIAG - Enterprise** offer
 - A user fills in the assistance form.  - When the assistance request is sent, the supervisor receives a message (email or SMS according to the notification preferences he checked in his user account). 
 <table class="seeAlso" cellspacing="0" cellpadding="0"> <tbody> <tr><td>  **See also&#160;**&#160;<a href="https://doc.apizee.com/smart/project-diag-help-desk/configure-the-agents/a/h1__984823644" target="_blank">Configure the agents - Define a user role and activate the notifications</a> 
 </td> </tr> </tbody> </table>   | New |
| Ticket assistance started | Notify the requester that the video assistance started. | Agent | The requester and the agent | The notification is sent when the session starts with the requester and the agent. | In progress |
| Ticket completed | Notify the requester that the assistance is finished. | Agent | Requester |  -  If there is a period of inactivity after an assistance session, the ticket automatically changes it status into&#160;**Done**. 
 **or**  -  The ticket changes into&#160;**Done**&#160;if the agent or the requester clicks&#160;**Done**&#160;on the interface. 
 
 There must have been a contact between the requester and the agent. 
   | Done |
| Ticket invitation declined | Notify the agent assigned to a ticket that the requester refused the video assistance invitation. | Requester | Agent (assigned) | Prerequisite:
 
Create a ticket for a scheduled assistance session.
 -  The requester has received an invitation for a scheduled assistance. The requester declined the invitation.  -  The agent receives a message (email or SMS according to the notification preferences he checked in his user account).  -  The agent sends an invitation again with another appointment date/hour.   | Declined |
| Ticket invitation expired | Notify the agent that the assistance link sent to the requester expired. | Agent | Agent |  -  The agent sends an assistance invitation to the requester.  -  If there is period of inactivity after an assistance invitation (the requester did not click on the link), the ticket expires.  -  The agent receives the notification so he can send another assistance invitation to the requester.   | Expired |
| Ticket canceled | Notify the requester that the assistance is canceled | Agent | Requester | Prerequisite:

The agent sent an invitation for an assistance. For some reason, the assistance has to be canceled.
- In the assistance list, the agent clicked **Cancel**.
or- In the assistance page, the agent clicked **Cancel session**.

{% hint style="info" %}

*See also** [Cancel a session](../video-assistance/agents/follow-up-the-assistances-on-the-portal/cancel-a-session.md)

{% endhint %}
| Ticket rejected | Notify the requester that the assistance request is rejected. | Agent | Requester | Prerequisite:
 
Subscribe to the **DIAG - Enterprise** offer
 -  A user fills in the assistance form.  -  The ticket is considered.  -  An agent changes the ticket status into&#160;**Rejected**. (Probably because the requester did not subscribe to the Support offer).   | Rejected |
| Ticket closed | Notify the requester that assistance is closed. The requester will no longer be able to interact with the agent. | Agent | Requester | Last status of a ticket.
 
The ticket status changes into **Closed** after the following status:
 -  **Expired**  -  **Rejected**&#160;or  -  **Done**   | Closed |
| Expired ticket closed | Notify the agent that the assistance automatically closed after the expiration of the assistance link the requester received. | Requester that did not do any action | Agent |  -  The agent received an assistance request.  -  The agent creates a ticket.  -  The requester received a message with a link to the assistance session but he never clicked on the link.  -  The link expired after a period of inactivity from the requester.  -  The ticket automatically closes after a period of inactivity from the agent who did not send a new invitation.   | Closed |
| Ticket escalation: declined | Notify the supervisor that the invitation to the video assistance has been refused. | Requester | Supervisor | Prerequisite:
 
Create a ticket for a scheduled assistance session.
 -  The requester declined the invitation.  -  If the agent does not send an invitation again with another appointment date/hour (Inaction from the agent) then, the ticket is transferred to the supervisor.   | Declined |
| Ticket escalation: completed | Notify the supervisor that the ticket is complete but that it is still not closed. | Agent | Supervisor |  -  The ticket changes into&#160;**Done**.  -  If the agent does not change the ticket status into&#160;**Closed**&#160;after x minutes (x = the time the agent defined when he created the ticket) then, the ticket is transferred to the supervisor.   | Done |
| Ticket escalation: expired | Notify the supervisor that the assistance request is not done because the ticket has expired. | Requester | Supervisor | * The ticket changes into **Expired** if the requester does not click on the link in the assistance invitation message.
 * If the agent does not send an invitation again with another appointment date/hour before the end of the idle time (defined by the administrators then, the ticket is transferred to the supervisor.
 

| **See also** [Customize the tickets](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md) |
| --- | | Expired |

1. In the **Notifications tab**, click **Conference notifications** to open the menu.
2. Repeat the same actions by click the **Switch** button to activate or deactivate the notifications.
3. Click **Save**.

{% hint style="success" %}
Your choices are saved.
{% endhint %}
