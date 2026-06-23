---
description: "Troubleshooting guide for Video Assistance, Multi-participant, Meetings, and Telehealth sessions."
icon: wrench
---

# Troubleshooting — Visual Engagement

Use this guide to resolve the most common issues across Video Assistance, Multi-participant sessions, Meetings, and Telehealth.

---

## Can't join a session

**Check these first:**

* You are using a [compatible browser](../general/faq-about-apizee-solutions.md) (Chrome, Firefox, Edge, Opera, or Safari on iOS 14+).
* You clicked the link in the invitation email or SMS — do not type the URL manually.
* Your profile status in the portal is set to **Available** (not Busy or Unavailable).
* You have allowed the browser to access your camera and microphone.

{% content-ref url="../general/i-do-not-manage-to-join-the-session.md" %}
[Can't join the session?](../general/i-do-not-manage-to-join-the-session.md)
{% endcontent-ref %}

---

## Camera not working / people can't see me

**Check these first:**

* The camera button in the video toolbar is enabled (not crossed out).
* You clicked **Allow** when the browser asked for camera permission.
* The camera is not in use by another application (Teams, Zoom, Citrix, etc.).
* In **Settings**, the correct camera device is selected.
* On mobile, you are not using the front camera while the back camera is expected.

{% content-ref url="../general/people-cannot-see-me.md" %}
[People can't see me](../general/people-cannot-see-me.md)
{% endcontent-ref %}

---

## Microphone not working / people can't hear me

**Check these first:**

* The microphone button is enabled in the session toolbar.
* You allowed the browser to access your microphone.
* The correct audio input is selected in **Settings → Audio**.
* Your physical microphone is not muted via a hardware button.
* On mobile, you granted microphone permission in your device settings.

{% content-ref url="../general/people-cannot-hear-me.md" %}
[People can't hear me](../general/people-cannot-hear-me.md)
{% endcontent-ref %}

---

## Video or audio cuts out

**Most likely causes:**

* Unstable internet connection — minimum 300 kb/s required, 4G/LTE recommended.
* Too many applications using bandwidth simultaneously.
* The session was idle for too long and timed out — rejoin using the same link.

{% content-ref url="../general/the-video-and-the-audio-cut-off.md" %}
[Video or audio keeps cutting out](../general/the-video-and-the-audio-cut-off.md)
{% endcontent-ref %}

---

## Audio sounds distorted or robotic

This is usually caused by an echo loop (two devices in the same room) or a driver conflict.

**Try:**

1. Use headphones to break the echo loop.
2. In **Settings → Audio**, switch to a different audio output device.
3. Disable any virtual audio devices (VirtualCable, Voicemeeter, etc.).

{% content-ref url="../general/the-audio-is-strange.md" %}
[Audio sounds strange or distorted](../general/the-audio-is-strange.md)
{% endcontent-ref %}

---

## No sound notifications

If you do not hear notification sounds when a guest joins or a new session arrives:

* Check that your browser tab is not muted.
* Check your system volume and that the browser is not muted in your OS mixer.
* Check that notification sounds are enabled in your portal account settings.

{% content-ref url="../general/i-do-not-have-the-sound-notifications.md" %}
[Sound notifications not working?](../general/i-do-not-have-the-sound-notifications.md)
{% endcontent-ref %}

---

## Browser permission denied

If you previously denied camera or microphone access, the browser will not ask again automatically.

{% content-ref url="../general/allow-the-web-browser-to-access-the-camera-and-the-microphone-on-my-computer.md" %}
[Allow your browser to access the camera and microphone](../general/allow-the-web-browser-to-access-the-camera-and-the-microphone-on-my-computer.md)
{% endcontent-ref %}

---

## Telehealth — billing and payment issues

For telehealth-specific billing problems (patient payment not received, unable to bill, Stripe configuration):

* Verify that online billing is enabled in **Administration → Billing**.
* Check that the patient's email address is correct on the ticket.
* Confirm that your Stripe account is connected and active.

Contact [support](https://apizee.atlassian.net/servicedesk/customer/user/login?destination=portals) if Stripe payments are failing or if you need to reissue an invoice.

---

{% include "../../shared/.gitbook/includes/support-cta.md" %}
