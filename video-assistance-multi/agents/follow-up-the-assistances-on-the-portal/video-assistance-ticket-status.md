# Ticket statuses

The statuses can change according to the type of video assistance. Click the menu that corresponds to your use:

{% tabs %}
{% tab title="Scheduled assistance" %}
![](../../.gitbook/assets/Assistance-form-ticket-statuses.png)
{% endtab %}
{% tab title="Immediate assistance" %}
![](../../.gitbook/assets/Instant-invitation-ticket-statuses.png)
{% endtab %}
{% tab title="Assistance request form" %}
![](../../.gitbook/assets/Scheduled-invitation-ticket-statuses.png)
{% endtab %}
{% endtabs %}

| Ticket status | Explanation |
| --- | --- |
| **New** | The requester filled the assistance request and sent it (Assistance request form only). |
| **Open** | The supervisor analyses the request and changes the status into **Open** before they assign it to an agent (Assistance request form only). |
| **Rejected** | The supervisor analyses the request and changes the status into **Rejected** (Assistance request form only). |
| **Invitation pending** | The invitation is sent to the guest. As a scheduled assistance, the guest can accept or decline the invitation. |
| **Invitation accepted** | The guest received the invitation. The guest accepted the invitation directly in the message or on the ticket public page (thanks to a link in the invitation). |
| **Declined** | The guest received the invitation. The guest declined the invitation directly in the message or on the ticket public page (thanks to a link in the invitation). |
| **Canceled** | The session can be **Canceled** by an agent when the status is **Open**, **Invitation pending**, **Invitation accepted**, or **In progress**. When a session is canceled it is as if it was closed. You cannot invite the guest to this session anymore. |
| **Expired** | The guest received the invitation but did not click the link. The ticket changes to **Expired** after a certain amount of time configured by the administrator ([Time trigger - Change status to Expired](../../admins/configuration-on-the-apizee-portal/configure-video-assistance/customize-the-tickets.md#expiration-time-after-invite)). |
| **In progress** | The video assistance started between the agent and the guest. |
| **Done (Completed)** | The ticket changes to **Done (Completed)** when: the guest or the agent clicked **Done**; when the satisfaction survey is activated and the guest clicks **Send** after answering; or when the **End transfer notification delay** is exceeded after a hang-up or file transfer. The delay is configured by the administrator ([Time trigger - Change status to Completed](../../admins/configuration-on-the-apizee-portal/configure-video-assistance/customize-the-tickets.md)). |
| **Closed** | The ticket changes to **Closed** when: the agent clicked **Close**; or the guest did not click the invitation link after a certain amount of time configured by the administrator ([Time trigger - Change status to Closed after expiration](../../admins/configuration-on-the-apizee-portal/configure-video-assistance/customize-the-tickets.md#max-expiration-time)). |

{% hint style="info" %}
After a **Declined** status, the agent can invite the guest again and change the date and time of the video assistance.
{% endhint %}

{% hint style="info" %}
After an **Expired** status, the agent can still invite the guest again if the expiration time is over 0.
{% endhint %}

{% hint style="info" %}
**See also** [Customize the tickets](../../admins/configuration-on-the-apizee-portal/configure-video-assistance/customize-the-tickets.md)
{% endhint %}
