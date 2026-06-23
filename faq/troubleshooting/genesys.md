---
description: "Troubleshooting guide for the Apizee Genesys Cloud integration."
icon: wrench
---

# Troubleshooting — Genesys

Use this guide to resolve common issues with the Apizee connector for Genesys Cloud.

---

## Integration not connecting

**Check these first:**

* The Apizee integration is installed and enabled in your Genesys Cloud organization under **Admin → Integrations**.
* The OAuth credentials (Client ID and Secret) are correctly entered in the Apizee integration settings.
* The Genesys Cloud region matches the region configured in the Apizee connector.
* The Apizee-side Genesys configuration points to the correct Genesys Cloud environment URL.

---

## Agent presence not updating in Genesys

Agent presence synchronization (marking agents as "On a session" in Genesys while in an Apizee call) was improved in the May 2026 release. Previously, status updates could take up to 30 seconds.

**If presence is still not updating after the May 2026 release:**

* Verify the Apizee integration has the **Modify Agent Presence** OAuth scope granted.
* Check that the agent's Genesys user account is linked to the corresponding Apizee agent account.
* Confirm the agent is using the Apizee widget inside the Genesys Cloud interface (not a standalone Apizee session).

---

## Transfer to queue failing

A bug where the routing queue name was not passed during session transfers was fixed in the April 2026 release.

**If transfers are still failing after that release:**

* Verify the transfer-to-queue flow is configured with the correct queue name.
* Check the Genesys routing configuration — the queue must exist and be active.
* No configuration changes are required if you are on the April 2026 release or later; the fix is automatic.

---

## Session data not appearing in Genesys conversation details

* Apizee session data is attached to the Genesys conversation via the integration's event hooks. Confirm the hooks are active in the Apizee integration settings.
* There can be a delay of up to 2 minutes before session metadata appears in the conversation record.

---

## Uninstalling the integration

If you need to remove the Apizee integration from your Genesys Cloud organization, follow the steps in:

{% content-ref url="../../genesys/uninstall-the-apizee-for-genesys-integration.md" %}
[Uninstall the Apizee for Genesys integration](../../genesys/uninstall-the-apizee-for-genesys-integration.md)
{% endcontent-ref %}

---

{% include "../../shared/.gitbook/includes/support-cta.md" %}
