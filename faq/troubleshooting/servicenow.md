---
description: "Troubleshooting guide for the Apizee ServiceNow connector."
icon: wrench
---

# Troubleshooting — ServiceNow

Use this guide to resolve common issues with the Apizee connector for ServiceNow.

---

## Connector installation fails

**Check these first:**

* You are on **connector v3.1 or later**, which supports scoped applications and the ServiceNow Vancouver release. Earlier versions required a global app — install from the ServiceNow Store to get the latest version.
* The installing user has the **admin** role in ServiceNow.
* If installing from a ZIP file (pre-Store versions), verify the package version matches your ServiceNow release.

For private distribution updates, contact [support](https://apizee.atlassian.net/servicedesk/customer/user/login?destination=portals) to obtain the correct package.

---

## Video session not starting from an incident

**Check these first:**

* The Apizee widget is added to the incident form layout.
* The logged-in ServiceNow user has the **x\_apizee\_connector.user** role (or equivalent).
* The Apizee connector is configured with a valid API key in **System Properties → Apizee**.

---

## Incident not automatically linked to a session

Automatic incident-to-session linking was introduced in the May 2026 release (connector v3.1+).

**If sessions are not linking to incidents:**

* Confirm you are on connector v3.1 or later.
* Retroactive linking does not apply to sessions that occurred before the v3.1 upgrade.
* The linking occurs when the session is initiated **from the incident page** — sessions started from other entry points are not linked automatically.

---

## Metrics not showing in the dashboard

* The metrics dashboard requires the **x\_apizee\_connector.admin** role to view.
* Data is aggregated and may take up to 15 minutes to reflect completed sessions.
* Confirm that the metrics feature is enabled in **System Properties → Apizee → Metrics**.

---

## Classic UI — different behavior

The ServiceNow Classic UI (prior to the San Diego release) has a separate connector module with limited functionality.

Key differences in Classic UI:
* Some features available in the modern UI (incident linking, metrics) are not supported.
* Use the **Apizee for ServiceNow — Classic UI** section of the documentation for Classic UI-specific steps.

{% content-ref url="../../servicenow/apizee-servicenow-classicui/README.md" %}
[About Apizee for ServiceNow in Classic UI](../../servicenow/apizee-servicenow-classicui/README.md)
{% endcontent-ref %}

---

## Events not appearing in the events log

* Events are fetched in near-real-time but may take up to 60 seconds.
* Verify the Apizee webhook is configured in **System Properties → Apizee → Webhooks**.
* Check **System Logs → Application Logs** in ServiceNow for any errors related to the Apizee connector.

---

{% include "../../shared/.gitbook/includes/support-cta.md" %}
