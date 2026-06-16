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
![](../../.gitbook/assets/EN-portal-assistance-page-timeline-location.png)
3. On the right hand side, under **Timeline**, check the different events.

| Event | Event | Explanation | Event ID\* |
| --- | --- | --- | --- |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Session created | An agent or a supervisor [created a ticket](../start-a-video-assistance/create-a-ticket-send-an-invitation/create-a-ticket-common-invitation.md). | 12 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Assistance assigned to someone | The assistance has been assigned to an agent [during the creation](../start-a-video-assistance/create-a-ticket-send-an-invitation/create-a-ticket-common-invitation.md#assign-assistance-ticket-creation), or [after](follow-a-ticket.md#assigne-assistance-follow-ticket). | 13 |
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
| ![](../../.gitbook/assets/Icon-Ticket.png) | Appointment canceled | The agent [canceled the video assistance appointment](cancel-a-session.md). <br><br> ![](../../.gitbook/assets/EN-portal-assistance-page-cancel-session-button.png) | 37 |
| ![](../../.gitbook/assets/Icon=Paper-plane.png) | Another invitation sent | The agent [sent a new invitation](send-new-invitation-for-same-session.md) to the guest for the same assistance. <br><br> ![](../../.gitbook/assets/EN-portal-assistance-page-edit-button.png) | 35 |
| ![](../../.gitbook/assets/Icon=Handpoint.png) | Invitation link clicked | The guest clicked the link in the assistance invitation. <br><br> ![](../../.gitbook/assets/EN-diag-guest-invitation-clicked.png) | 26 |
| ![](../../.gitbook/assets/Icon=Check.png) | Session can start | The page of the link displays on the guest screen now. <br><br> ![](../../.gitbook/assets/EN-diag-guest-legals-not-checked.png) | 10 |
| ![](../../.gitbook/assets/Icon=Check.png) | Legal terms agreed | The guest checked the boxes and clicked **Confirm** to the legal terms. <br><br> ![](../../.gitbook/assets/EN-diag-guest-legals-confirmed.png) | 19 |
| ![](../../.gitbook/assets/Icon=Handpoint.png) | Contact an agent button clicked | The guest clicked the button to join the assistance. <br><br> ![](../../.gitbook/assets/EN-diag-guest-contact-agent-button-clicked.png) | 30 |
| ![](../../.gitbook/assets/Icon=Share.png) | Camera and microphone allowed | According to the video assistance configuration, the guest can be asked to allow the access to both camera and microphone. <br><br> In this case, the guest **allowed** both of them. <br><br> ![](../../.gitbook/assets/EN-diag-guest-allow-cam-and-mic.png) | 20 |
| ![](../../.gitbook/assets/Icon=Share-refused.png) | Camera and microphone denied | According to the video assistance configuration, the guest can be asked to allow the access to both camera and microphone. <br> In this case, the guest **blocked** the access to both of them. Or **did not click** at all. <br><br> ![](../../.gitbook/assets/EN-diag-guest-block-mic-and-cam.png) | 21 |
| ![](../../.gitbook/assets/Icon=Share-camera.png) | Camera allowed | According to the video assistance configuration, the guest can be asked to allow the access to the camera only. <br><br> In this case the guest **allowed**. | 22 |
| ![](../../.gitbook/assets/Icon=Share-camera-refused.png) | Camera denied | According to the video assistance configuration, the guest can be asked to allow the access to the camera only. <br><br> In this case the guest **blocked** it. | 23 |
| ![](../../.gitbook/assets/Icon=Share-micro.png) | Microphone allowed | According to the video assistance configuration, the guest can be asked to allow the access to the microphone only. <br><br> In this case the guest **allowed**. | 24 |
| ![](../../.gitbook/assets/Icon=Share-micro-refused.png) | Microphone denied | According to the video assistance configuration, the guest can be asked to allow the access to the microphone only. <br><br> In this case the guest **blocked** it. | 25 |
| ![](../../.gitbook/assets/Icon=Headset.png) | Session started | The agent picks up the call. <br><br> ![](../../.gitbook/assets/EN-Diag-portal-agent-receiving-call.png) | 36 |
| ![](../../.gitbook/assets/Icon=Camera.png) | Picture taken by the agent | The agent [took a screenshot](../actions-during-the-video-assistance/take-a-picture-and-draw-on-it.md) of the guest video. <br><br> ![](../../.gitbook/assets/Portal-diag-agent-take-picture.png) | 38 |
| ![](../../.gitbook/assets/Icon=Camera.png) | Picture sent by the guest | The guest [shared a file](../actions-during-the-video-assistance/share-and-download-files/share-file-with-an-agent.md) with the agent. <br> - **During **a call: <br> ![](../../.gitbook/assets/Diag-requester-mobile-take-picture-with-mobile-camera.png) <br> - **After **a call: <br> ![](../../.gitbook/assets/EN-Diag-guest-share-file-after-session-result.png) | 39 |
| ![](../../.gitbook/assets/Icon=Place.png) | Geolocation accepted | The guest **allowed** the geolocation. <br><br> ![](../../.gitbook/assets/EN-Diag-guest-allow-geolocation.png) | 28 |
| ![](../../.gitbook/assets/Icon=Place-off.png) | Geolocation declined | The guest **blocked** the geolocation. | 29 |
| ![](../../.gitbook/assets/Icon=Exit-User.png) | Guest left the session | The guest clicked **leave** to hang up the call. <br><br> ![](../../.gitbook/assets/Diag-guest-leave-session.png) | 33 |
| ![](../../.gitbook/assets/Icon=Exit-Admin.png) | Agent left the session | The agent clicked **leave** to hang up the call. <br><br> ![](../../.gitbook/assets/Portal-diag-agent-leave-session.png) | 32 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Agent completed the assistance | The agent clicked **Complete session** in the assistance page. <br><br> ![](../../.gitbook/assets/EN-portal-assistance-page-complete-session-button.png) | 11 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Guest completed the assistance | The guest clicked **close** to complete the assistance. <br><br> ![](../../.gitbook/assets/EN-Diag-Requester-end-session-page-close-button-clicked.png) | 11 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | System changed the session status into "completed" | The status of the session automatically changed into "completed" because the **[End transfer notification delay (min)](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md/a/end-transfer-notification-delay)** trigger is exceeded.

{% hint style="info" %}
**See also** [Configure the triggers](../video-assistance/agents/follow-up-the-assistances-on-the-portal/attach-a-report-to-the-ticket.md)
{% endhint %}
{% hint style="info" %}
**See also** [What status for my ticket?](video-assistance-ticket-status.md)
{% endhint %}
| ![](../../.gitbook/assets/image-20231011-143535.png) | Guest responded to the survey | After the session, the guest [responded to the satisfaction survey](../respond-to-the-satisfaction-survey.md) and clicked **Send**. <br><br> ![](../../.gitbook/assets/EN-Diag-requester-survey.png) | 40 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | Agent closed this session | The agent clicked **Close session** in the assistance page. <br><br> ![](../../.gitbook/assets/EN-portal-assistance-page-close-session-button.png) | 8 |
| ![](../../.gitbook/assets/Icon-Ticket.png) | The system changed the session status into “closed” | The status of the session automatically changed into "closed" because the **[Max expiration time (min)](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md/a/max-expiration-time)** trigger is exceeded.

{% hint style="info" %}
**See also**https://doc.apizee.com/articles/project-diag-help-desk-diagnostic-center/attach-a-report-to-the-ticket[Configure the triggers](../video-assistance/admins/configuration-on-the-apizee-portal/configure-the-video-assistance/customize-the-tickets.md)
{% endhint %}
{% hint style="info" %}
**See also**https://doc.apizee.com/articles/project-diag-help-desk-diagnostic-center/attach-a-report-to-the-ticket[What status for my ticket?](video-assistance-ticket-status.md)
{% endhint %}

{% hint style="info" %}
\* **Event ID** is only for users who use the APIs.
{% endhint %}
