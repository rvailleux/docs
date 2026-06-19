---
description: "Release notes for Visual Engagement — video assistance, co-browsing, multi-participant sessions, meetings, and telehealth."
icon: video
---

# Visual Engagement

{% updates format="full" %}

{% update date="2026-06-01" tags="visual-engagement,new-feature" %}
## HD video mode for Video Assistance

Agents and guests can now switch to HD resolution (1080p) during a session when bandwidth allows. The quality setting is accessible from the session toolbar under **Settings → Video quality**.

* Automatic fallback to standard quality when bandwidth drops below threshold
* HD mode is enabled by default for sessions on desktop browsers
* Mobile guests remain on adaptive quality
{% endupdate %}

{% update date="2026-05-15" tags="visual-engagement,improvement" %}
## Improved co-browsing performance

Co-browsing latency has been reduced by up to 40% on pages with complex DOM structures. Scrolling and click events are now synchronized in under 80 ms on a standard broadband connection.

* Reduced CPU usage on the agent side during long co-browsing sessions
* Better handling of iframes and shadow DOM elements
{% endupdate %}

{% update date="2026-05-01" tags="visual-engagement,new-feature" %}
## Multi-participant session recording

Session recordings now capture all participant streams in a single composite video file. Recordings are available in the portal under **Sessions → Recordings** within 5 minutes of session end.

* Configurable layout: side-by-side or picture-in-picture
* Recordings are stored for 90 days by default (configurable per account)
* Export to MP4 available from the portal
{% endupdate %}

{% update date="2026-04-10" tags="visual-engagement,improvement" %}
## Telehealth: waiting room enhancements

The patient waiting room now displays the estimated waiting time and the name of the care provider. Agents can send a pre-session message directly from the waiting room queue.

* Waiting room message supports plain text and a single image
* Queue view updated to show patient connection status in real time
{% endupdate %}

{% update date="2026-03-20" tags="visual-engagement,fix" %}
## Fix: camera switching on iOS 17

A regression introduced in the previous release caused the camera switch button to stop working on iOS 17 devices mid-session. This is now resolved.

* Affected: iOS 17.0–17.3 on Safari and Chrome
* No workaround was available; updating resolves the issue immediately
{% endupdate %}

{% update date="2026-03-01" tags="visual-engagement,new-feature" %}
## Meetings: calendar invitations

Meeting invitations now include an `.ics` file attachment. Guests receive a calendar event for their meeting directly in the invitation email.

* Compatible with Google Calendar, Outlook, and Apple Calendar
* ICS timezone is automatically set from the agent's portal locale
{% endupdate %}

{% endupdates %}
