---
description: "Troubleshooting guide for the Apizee Embed widget, SDK, and portal."
icon: wrench
---

# Troubleshooting — Embed

Use this guide to resolve common issues with the Apizee Embed widget and portal.

---

## Widget not loading on the page

**Check these first:**

* The Embed script tag is present and loaded before the `ApizeeEmbed.init()` call.
* There are no JavaScript console errors blocking script execution (open DevTools → Console).
* The domain is whitelisted in the Embed portal under **Settings → Allowed domains**.
* Content Security Policy (CSP) headers on your site allow the Embed script origin.

If the widget loads on first visit but disappears after navigation (SPA), ensure you are calling `ApizeeEmbed.init()` after each route change, or upgrading to v3.5.x which includes a deferred init guard.

---

## Authentication error — users can't log in

Since Embed v3.5.x, agents must authenticate with their Apizee credentials before using the widget.

**If the login page is not showing or returning an error:**

* Confirm the user account exists in the Embed portal.
* Check that the user's role has the correct permissions assigned in Keycloak (introduced in the May 2026 permission refactor).
* Clear browser cookies and cache, then retry.
* If using SSO (SAML/Entra ID), verify the federation metadata in **Administration → SSO**.

---

## Guest can't join a session

**Check these first:**

* The invitation link has not expired (links expire after the configured session timeout).
* The guest is using a compatible browser (Chrome, Firefox, Edge, or Safari on iOS 14+).
* The guest allowed camera and microphone access when prompted.
* The session is still open on the agent side.

If guests were unable to join between April and May 2026 specifically, this was a known regression in v3.5.0 (CVE patch) — fixed in v3.5.1. Ensure you are on v3.5.1 or later.

---

## Invitation sending fails (429 error)

A "429 Too Many Requests" error when sending invitations from Salesforce, Zendesk, or Sandbox integrations was a known issue fixed in v3.5.0.

**If you are seeing this error on v3.5.0 or later:**

* Check that your integration is not sending invitations in a tight loop — add a delay between retries.
* Verify that the Service Account token is valid and has not expired.
* Contact [support](https://apizee.atlassian.net/servicedesk/customer/user/login?destination=portals) if the issue persists after verifying the above.

---

## Webhooks not receiving events

If you configured webhooks via Hook0 but are not receiving events:

* Verify the webhook URL is publicly accessible (not localhost or behind a firewall).
* Check Hook0's delivery log for failed attempts and HTTP response codes.
* Confirm the correct event types are subscribed in Hook0.
* Test with a manual trigger from the Embed portal to rule out configuration issues.

---

## Language detection not working

Automatic browser language detection was introduced in v3.5.x.

**If the interface is showing the wrong language:**

* Pass the `lang` URL parameter explicitly (e.g., `?lang=es`) to override auto-detection.
* Confirm the desired language (Spanish `es`, Italian `it`, German `de`, French `fr`, English `en`, Dutch `nl`) is enabled for your tenant.
* If the login page is stuck in English, update to v3.5.0 or later — this was a known bug fixed in that release.

---

## Webhook postMessage format changed

If your integration broke after the April 2026 update (v3.5.x), check for these breaking changes:

* The `nP` URL parameter and `number_of_participants` postMessage were removed — participant count is now managed exclusively through `interactionTemplate`.
* The `onSessionEnd` callback signature changed: it now receives `{ sessionId, duration, rating }` instead of just `sessionId`.
* postMessage events for invitations and transcriptions now follow the standardized format: `{ key, status, success, payload, timestamp }`.

---

## Session not visible in the portal after ending

Sessions should appear in the Embed portal under **Sessions** within a few minutes of ending.

If a session is missing:

* Confirm the agent was authenticated during the session (unauthenticated sessions are not logged).
* Check the session was created via an interaction — since v3.5.x, session creation automatically creates an interaction record.
* If you are an IT operator, verify the tenant configuration in the Back-Office.

---

{% include "../../shared/.gitbook/includes/support-cta.md" %}
