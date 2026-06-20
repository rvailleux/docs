---
description: "Troubleshooting guide for the Apizee Salesforce integration."
icon: wrench
---

# Troubleshooting — Salesforce

Use this guide to resolve common issues with the Apizee connector for Salesforce.

---

## Video call not starting from Salesforce

**Check these first:**

* The Apizee Lightning component is added to the record page layout (Contact, Lead, or Case).
* The logged-in Salesforce user has the **Apizee User** permission set assigned.
* The Apizee connector package is installed and up to date — go to **Setup → Installed Packages**.
* The Salesforce org is connected to the correct Apizee tenant in **Setup → Apizee → Configuration**.

---

## Session activity not logged as a Task

Automatic Task logging was introduced in the June 2026 release.

**If sessions are not creating Task records:**

* Confirm you are on the June 2026 release or later — earlier versions do not support automatic logging.
* Go to **Setup → Apizee → Activity Logging** and verify the feature is enabled.
* Check that the running user has permission to create Task records.
* Verify the custom field mapping if you are using non-standard Contact or Case fields.

---

## Click-to-call not working from phone number fields

Click-to-call from phone fields (Contact, Lead, Case) was added in the April 2026 release.

**If the click-to-call trigger is not appearing:**

* Go to **Setup → Apizee → Click-to-call** and confirm the feature is enabled.
* Verify the phone field you are using is mapped in the click-to-call configuration.
* Custom phone fields require explicit mapping — standard fields (`Phone`, `MobilePhone`) are mapped by default.
* Ensure the Lightning component is on a supported page layout (not Classic UI).

---

## Connector installation or update fails

If the managed package installation fails:

* Check that the installing user has the **System Administrator** profile.
* Confirm there are no Apex test failures blocking the install — run pending tests first.
* For updates: if you are updating from a version older than V2, contact [support](https://apizee.atlassian.net/servicedesk/customer/user/login?destination=portals) for a migration guide.

For private app distribution updates, follow the steps in the [Apizee connector update guide](https://apizee.atlassian.net/wiki/spaces/IN/pages/4100947969).

---

## Agentforce integration not working

**Check these first:**

* The **Apizee for Agentforce** flow action is published and assigned to the relevant agent topic.
* The Agentforce user's profile has the **Apizee User** permission set.
* Verify the flow configuration references the correct Apizee service (queue/flow).

---

## Events not appearing in the Watch the Events log

* Confirm the **Apizee Events** tab is accessible to the current user's profile.
* Events are near-real-time but may take up to 30 seconds to appear.
* If no events appear at all, verify that the webhook from Apizee to Salesforce is configured and active in **Setup → Apizee → Webhooks**.

---

{% include "../../shared/.gitbook/includes/support-cta.md" %}
