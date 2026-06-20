---
description: "Release notes for the Apizee Embed widget, SDK, and integration libraries."
icon: code
---

# Embed

{% updates format="full" %}

{% update date="2026-06-03" tags="embed,new-feature,improvement" %}
## v3.5.4 — Multilingual interface, guest profiles, Design System

**Multilingual support**

The Embed interface is now available in Spanish (`es`), Italian (`it`), and German (`de`), in addition to the existing English (`en`), French (`fr`), Dutch (`nl`). Language is auto-detected from the browser locale and can be overridden with the `?lang=` URL parameter.

**Guest profiles**

Agents can now attach a guest profile (name, email, phone) to a session before sending the invitation. Profile data is saved to the interaction record and visible in session history.

**Design System alignment**

The widget UI has been updated to align with the Apizee Design System — updated typography, spacing, and button styles. No functional changes.
{% endupdate %}

{% update date="2026-05-20" tags="embed,improvement,security" %}
## Keycloak permission refactor

User permissions and role assignments are now managed through Keycloak, replacing the previous ad-hoc role system. This change affects:

* How agent roles are assigned in the Embed portal — use **Administration → Users → Roles** to reassign permissions.
* SSO federation: if you use SAML/Entra ID, verify that your identity provider attribute mapping is still correct after the update.

No changes are required for tenants not using SSO. Existing sessions and interaction data are unaffected.
{% endupdate %}

{% update date="2026-04-15" tags="embed,new-feature,fix,breaking-change" %}
## v3.5.0 / v3.5.1 — Guest tracker, face-to-face mode, transcription improvements, security patch

**New features (v3.5.0)**

* **Guest tracker**: Agents can now see the guest's current page URL and device type during a session, visible in the session side panel.
* **Face-to-face mode**: A new display layout where both agent and guest cameras are shown side-by-side at equal size. Enable via the layout toggle in the session toolbar.
* **Photo notifications**: Agents receive an in-app notification when the guest takes a photo during the session.
* **Transcription speaker names**: Live transcription now labels each speaker by name instead of "Agent" / "Guest".

**Architecture improvements**

* Session creation now automatically creates a linked interaction record. Sessions started outside of an interaction context (e.g. direct API calls) will generate a new interaction automatically.
* Agent authentication is now required to start a session. Unauthenticated sessions will be rejected.

**Breaking changes**

* The `nP` URL parameter and `number_of_participants` postMessage were removed — participant count is now managed exclusively through `interactionTemplate`.
* The `onSessionEnd` callback signature changed: it now receives `{ sessionId, duration, rating }` instead of just `sessionId`.
* postMessage events for invitations and transcriptions now follow the standardized format: `{ key, status, success, payload, timestamp }`.

**Bug fixes (v3.5.1)**

* Fixed a regression introduced in v3.5.0 (CVE-2026-2386) where guests were unable to join sessions between April and May 2026. Update to v3.5.1 or later.
* Fixed a "429 Too Many Requests" error when sending invitations from Salesforce, Zendesk, or Sandbox integrations.
{% endupdate %}

{% update date="2026-02-25" tags="embed,new-feature" %}
## Webhook event delivery via Hook0

Embed now supports webhook subscriptions through Hook0. Configure event subscriptions in the Embed portal under **Administration → Webhooks** to receive real-time notifications for session start, session end, invitation sent, and transcription ready events.

Each event follows the standardized payload format: `{ key, status, success, payload, timestamp }`.

See the [webhooks troubleshooting guide](../faq/troubleshooting/embed.md#webhooks-not-receiving-events) if events are not arriving.
{% endupdate %}

{% update date="2026-01-21" tags="embed,new-feature,improvement" %}
## Agent authentication required; session–interaction auto-link

**Agent authentication**

Starting from this release, agents must authenticate with their Apizee credentials before using the Embed widget. Unauthenticated access is no longer permitted. Ensure all agent accounts exist in the Embed portal before deploying.

If you use SSO (SAML/Entra ID), configure federation metadata in **Administration → SSO** before enabling this release.

**Session–interaction auto-link**

Sessions created from the Embed widget are now automatically linked to an interaction record. This enables full session history, file access, and timeline tracking from the Embed portal.

Sessions created before this release are not retroactively linked.
{% endupdate %}

{% endupdates %}
