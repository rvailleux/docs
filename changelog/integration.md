---
description: "Release notes for Apizee integrations — Salesforce, Genesys, and ServiceNow connectors."
icon: puzzle-piece
---

# Integrations

{% updates format="full" %}

{% update date="2026-06-05" tags="integration,new-feature" %}
## Salesforce: session activity logged as Task records

Video and co-browsing sessions are now automatically logged as Salesforce Task records linked to the relevant Contact or Case. Agents no longer need to manually log activity after a session.

* Task subject: `Apizee session — {date} — {duration}`
* Task status is set to `Completed` automatically
* Custom field mapping available under **Setup → Apizee → Activity Logging**
{% endupdate %}

{% update date="2026-05-25" tags="integration,improvement" %}
## Genesys: improved presence synchronization

Agent presence in Genesys Cloud is now updated in real time when an Apizee session starts or ends. Previously, the status update could take up to 30 seconds.

* Agents marked as "On a session" in Genesys while in an active Apizee video call
* Status reverts automatically when all sessions end
{% endupdate %}

{% update date="2026-05-10" tags="integration,new-feature" %}
## ServiceNow: incident auto-creation

When a video session is initiated from a ServiceNow incident, a relationship link is automatically created between the session record and the incident. Supervisors can view all sessions linked to an incident from the incident page.

* Requires ServiceNow connector v3.1 or later
* Retroactive linking is not applied to sessions prior to this release
{% endupdate %}

{% update date="2026-04-20" tags="integration,improvement" %}
## Salesforce: click-to-call from Lightning component

The Apizee Lightning component now supports click-to-call from phone number fields on Contact, Lead, and Case records. The call is initiated as an Apizee video session.

* Configured under **Setup → Apizee → Click-to-call**
* Works with custom phone fields — map any field in the configuration
{% endupdate %}

{% update date="2026-04-01" tags="integration,fix" %}
## Fix: Genesys routing queue not populated on transfer

When an agent transferred an active Apizee session to a Genesys routing queue, the queue name was not passed along, causing the transfer to fail silently. This is now resolved.

* Affected Genesys Cloud integrations using the transfer-to-queue flow
* No configuration changes required — the fix applies automatically
{% endupdate %}

{% update date="2026-03-10" tags="integration,new-feature" %}
## ServiceNow connector v3.1 released

The ServiceNow connector has been updated to support the Vancouver release of ServiceNow. Key changes:

* Uses the new Now Platform REST API v2
* Supports scoped applications (no more global app requirement)
* Installation via the ServiceNow Store — no manual import needed
{% endupdate %}

{% endupdates %}
