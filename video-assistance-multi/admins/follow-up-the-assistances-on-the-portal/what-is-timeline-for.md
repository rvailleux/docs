#  Real-time timeline of the session.

{% hint style="info" %}
You are an agent and you need to:
  - understand **in which step your interlocutor ****is **to join the video assistance  - **retrieve some events** of the video assistance  - have a **quick sum up** of what happened during the video assistance  
{% endhint %}

1. In the left-hand menu, click the service you want.
2. In the ticket list, find the ticket you want to follow up and click ![](../../.gitbook/assets/button-edit.png)

![](../../.gitbook/assets/EN-portal-service-assistance-edit-ticket.png)

{% hint style="success" %}
The assistance page displays.
{% endhint %}
 ![](../../.gitbook/assets/EN-portal-assistance-multi-page-timeline-location.png)
3. On the right hand side, under **Timeline**, check the different events.

| Event | Event | Explanation | Event ID\* |
| --- | --- | --- | --- |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Session created | An agent or a supervisor [created a ticket](../video-assistance/agents/start-a-video-assistance/create-a-ticket-send-an-invitation/create-a-ticket-common-invitation.md). | 12 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Assistance assigned to someone | The assistance has been assigned to an agent [during the creation](../video-assistance/agents/start-a-video-assistance/create-a-ticket-send-an-invitation/create-a-ticket-common-invitation.md/a/assign-assistance-ticket-creation), or [after](../video-assistance/agents/follow-up-the-assistances-on-the-portal/follow-a-ticket.md/a/assigne-assistance-follow-ticket). | 13 |
| ![](../../.gitbook/assets/Icon=Paper-plane.png) | Invitation sent | The invitation to an assistance has been sent after the ticket creation. | 4 |
| ![](../../.gitbook/assets/Icon=Clock.png) | Invitation link not clicked | The guest did not click the link in the assistance invitation.

![](../../.gitbook/assets/EN-diag-guest-invitation-not-clicked.png) | 27 |
{% hint style="info" %}
Invitation declined | | ![Information](../../.gitbook/assets/info.png) | For **scheduled** assistance only.
{% endhint %}
The guest clicked the **More information** link in the invitation, then, **declined** the invitation. 
The agent can still invite the guest again on another date and time that suits best.

![](../../.gitbook/assets/EN-diag-guest-decline-invitation.png) | 5 |
{% hint style="info" %}
Invitation accepted | | ![Information](../../.gitbook/assets/info.png) | For **scheduled** assistance only.
{% endhint %}
The guest **accepted** the invitation to the assistance.

![](../../.gitbook/assets/EN-diag-guest-accept-invitation.png) | 6 |
{% hint style="info" %}
Priority of the session changed into "scheduled" | | ![Information](../../.gitbook/assets/info.png) | [Scheduling](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md/a/schedule-feature-description) option has to be activated.
{% endhint %}
The video assistance was immediate and has been changed to be scheduled on another moment. | 18 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Appointment canceled | The agent [canceled the video assistance appointment](../video-assistance/agents/follow-up-the-assistances-on-the-portal/cancel-a-session.md).

![](../../.gitbook/assets/EN-portal-assistance-page-cancel-session-button.png) | 37 |
| ![](../../.gitbook/assets/Icon=Paper-plane.png) | Another invitation sent | The agent [sent a new invitation](../video-assistance/agents/follow-up-the-assistances-on-the-portal/send-new-invitation-for-same-session.md) to the guest for the same assistance.

 ![](../../.gitbook/assets/EN-portal-assistance-multi-invite-again-button.png) | 35 |
| ![](../../.gitbook/assets/Icon=Check.png) | Session can start | The page of the link displays on the guest screen now.

![](../../.gitbook/assets/EN-diag-guest-legals-not-checked.png) | 10 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Agent completed the assistance | The agent clicked **Complete session** in the assistance page.

![](../../.gitbook/assets/EN-portal-assistance-page-complete-session-button.png) | 11 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | System changed the session status into "completed" | The status of the session automatically changed into "completed" because the **[End transfer notification delay (min)](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md/a/end-transfer-notification-delay)** trigger is exceeded.

{% hint style="info" %}
**See also** [Configure the triggers](../video-assistance/agents/follow-up-the-assistances-on-the-portal/attach-a-report-to-the-ticket.md)
{% endhint %}
{% hint style="info" %}
**See also** [What status for my ticket?](../video-assistance/agents/follow-up-the-assistances-on-the-portal/video-assistance-ticket-status.md)
{% endhint %}
| ![](../../.gitbook/assets/Icon-Ticket.png) | Agent closed this session | The agent clicked **Close session** in the assistance page.

![](../../.gitbook/assets/EN-portal-assistance-page-close-session-button.png) | 8 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | The system changed the session status into “closed” | The status of the session automatically changed into "closed" because the **[Max expiration time (min)](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md/a/max-expiration-time)** trigger is exceeded.

{% hint style="info" %}
**See also**https://doc.apizee.com/articles/project-diag-help-desk-diagnostic-center/attach-a-report-to-the-ticket[Configure the triggers](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md)
{% endhint %}
{% hint style="info" %}
**See also**https://doc.apizee.com/articles/project-diag-help-desk-diagnostic-center/attach-a-report-to-the-ticket[What status for my ticket?](../video-assistance/agents/follow-up-the-assistances-on-the-portal/video-assistance-ticket-status.md)
{% endhint %}

{% hint style="info" %}
\* **Event ID** is only for users who use the APIs.
{% endhint %}
