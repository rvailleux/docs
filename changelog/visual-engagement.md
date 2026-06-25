---
description: "Release notes for Visual Engagement — video assistance, multi-participant sessions, meetings, and telehealth."
icon: video
---

# Visual Engagement

{% updates format="full" %}

{% update date="2026-06-30" tags="visual-engagement,new-feature,improvement" %}
## Cloud 7.5.0 — Configurable Reference field in Diag invitation form

The **Reference** field in Diag invitation forms can now be set as optional or required per service.

* Administrators choose whether guests must fill in a reference number before joining
* Geolocation link now renders correctly in PDF exports (was missing in some configurations)
{% endupdate %}

{% update date="2026-06-16" tags="visual-engagement,improvement,fix" %}
## Cloud 7.4.5 · Meet 4.43.1 · Diag 2.24.4 — Clearer notifications, ghost stream fix

**Improvements**

* SMS and email invitation notifications have been rewritten to be shorter and clearer
* The **Reminder** field in invitation forms is now adaptive and adjusts to the channel selected

**Bug fixes**

* Meet: ghost video stream no longer appears after a participant reconnects (ApiRTC 5.0.35)
* Meet: rear-camera activation on iOS is now stable after the 4.43.0 regression
* Diag: language selection is now correctly applied throughout the guest session
* Multiple fixes for invitation edge cases, conference payment flow, and CSV export formatting
{% endupdate %}

{% update date="2026-04-20" tags="visual-engagement,new-feature,improvement,fix" %}
## Cloud 7.4.3 · Meet 4.43.0 — Rear camera on entry, phone-audio UX

**New features**

* Meet sessions can now be configured to **activate the rear camera automatically** when a guest joins (useful for field-inspection scenarios)
* Phone-audio sessions (no video) now show a simplified interface — the microphone button is always visible and the camera controls are hidden

**Improvements**

* Admin configuration screens display a clearer message when a setting is inherited from a parent service
* TLS 1.3 is now supported; Nginx has been updated to the latest stable release

**Bug fixes**

* SMS messages longer than one segment are now split correctly without truncation
{% endupdate %}

{% update date="2026-02-25" tags="visual-engagement,new-feature,fix" %}
## Cloud 7.3.16 · Meet 4.42.3 · Diag 2.24.3 — Optional invitation channels

**New feature — optional invitation channels**

It is now possible to **disable automatic SMS or email sending** while still collecting the guest's contact information. This lets agents or integrations dispatch the invitation via an alternative channel (WhatsApp, N8N automation, etc.) without the platform sending a duplicate notification.

**Bug fixes**

* Meet: launcher button URL length limit raised (previously truncated long URLs)
* Diag: ticket state transitions are now applied correctly after an agent closes a session
* Meet: recording no longer stops when an agent manually hangs up and then re-joins
* Meet: the organizer tab no longer displays a blank section in certain configurations
{% endupdate %}

{% update date="2026-02-18" tags="visual-engagement,improvement" %}
## Cloud 7.4.0 — Laravel 12 upgrade

The Cloud platform has been upgraded to **Laravel 12**. This is an infrastructure update with no change to end-user behaviour; it improves long-term maintainability and unlocks future performance work.
{% endupdate %}

{% update date="2026-01-07" tags="visual-engagement,new-feature,fix" %}
## Cloud 7.3.15 · Meet 4.42.2 · Diag 2.24.1 — Calendar invitations for DiagConf, black screen fix

**New feature**

* Scheduled **DiagConf** (multi-participant) invitations now include an **ICS calendar attachment** so guests can add the session directly to their calendar

**Bug fixes**

* Black screen on Microsoft Edge + iOS: resolved by an ApiRTC update (3.66.2) that addresses a WebRTC stream subscription edge case
{% endupdate %}

{% update date="2026-01-07" tags="visual-engagement,fix" %}
## Cloud 7.3.14 · Meet 4.42.1 · Diag 2.24.0 — Bug fixes

* Photo thumbnails captured on mobile are now displayed with the correct orientation (portrait photos were rotated 90°)
* Meet: stream subscriptions are re-established correctly after a network reconnect
* Diag: the end-session confirmation popup now always appears when an agent closes a session
* Multi-service invitation page: a warning is now shown when the SMS prefix is missing
* Storage quota alert emails now clearly state which threshold (80% or 100%) was reached
{% endupdate %}

{% update date="2025-12-10" tags="visual-engagement,new-feature,fix" %}
## Cloud 7.3.13 · Meet 4.42.0 — Custom launcher buttons in Meet

**New feature — configurable shortcut buttons**

Administrators can now configure **up to 6 custom launcher buttons** per service in Meet. Each button opens a URL in a new tab and can be labelled and ordered independently. Typical use cases: link to a CRM record, open a knowledge base article, or launch an internal tool during a session.

**Bug fix**

* SSO: language fallback now works correctly when the user's preferred language is not available in the platform configuration
{% endupdate %}

{% update date="2025-11-26" tags="visual-engagement,fix,improvement" %}
## Cloud 7.3.12 — API spec corrections, quota renewal fix

* OpenAPI specification updated with corrected field descriptions (used for GitBook API documentation automation)
* Custom storage quota renewal bug fixed — renewal dates were not always computed correctly for enterprise accounts
* GCS (Google Cloud Storage) integration code cleanup
{% endupdate %}

{% update date="2025-11-05" tags="visual-engagement,improvement" %}
## Cloud 7.3.11 — Data retention policy

Default data retention periods have been standardised across the platform:

| Data type | Retention period |
|---|---|
| Tickets, sessions, stats | 12 months |
| Media files (recordings, snapshots) | 18 months |
| Inactive non-admin user accounts on inactive enterprises | 6 months |

SMS prefix enforcement is now applied at send time to prevent misconfigured prefixes from silently generating undeliverable messages.
{% endupdate %}

{% update date="2025-10-22" tags="visual-engagement,fix" %}
## Cloud 7.3.10 — Bug fixes

* Scheduled tickets now respect the default filter (last 7 days) introduced in 7.3.8
* Agent name and avatar are now correctly included in PDF image captions
* DiagConf (multi-participant): PDF export now works when only one guest was present
* Meet: QoS (quality-of-service) graphs display correctly in the session report
{% endupdate %}

{% update date="2025-09-24" tags="visual-engagement,improvement,fix" %}
## Cloud 7.3.8 · 7.3.9 — Ticket list filter, performance cap

**Improvements**

* The ticket list now defaults to the **last 7 days** instead of showing all tickets, which significantly improves load time for high-volume accounts
* A **warning banner** appears when the result set exceeds 1,000 tickets, prompting the agent to narrow the filter

**Bug fix**

* Multi-participant session statistics export (CSV) now includes all participants correctly
{% endupdate %}

{% update date="2025-09-10" tags="visual-engagement,fix" %}
## Cloud 7.3.7 — Bug fixes

* SSO super-admin: ticket access is now correctly granted when logging in through SSO with elevated privileges
* Agents no longer lose access to the end-of-session notification screen in certain browser configurations
{% endupdate %}

{% update date="2025-08-20" tags="visual-engagement,new-feature,security" %}
## Cloud 7.3.6 — JWT-based SSO

The platform now supports **JWT-based Single Sign-On**. Administrators can configure a public key (x509 or RSA) via a new **Custom Domain** tab in SSO settings. The `POST /token` endpoint accepts a JWT signed by your identity provider — no password exchange required.

This enables seamless integration with enterprise IdPs that issue JWT tokens (Okta, Azure AD, etc.).
{% endupdate %}

{% update date="2025-08-20" tags="visual-engagement,new-feature,improvement" %}
## Cloud 7.3.4 — Customizable PDF export template

Administrators can now control which sections appear in the **PDF session report** exported from Diag:

* Toggle individual sections on or off (summary, timeline, snapshots, geolocation map, etc.)
* The **Advanced** tab is now shown first in the service configuration panel for faster access
* The **Report** tab has been removed from the session view (its content is now accessible directly in the PDF export settings)
* Assistance Request settings are now loaded dynamically and no longer require a page refresh
{% endupdate %}

{% update date="2025-07-23" tags="visual-engagement,improvement,fix" %}
## Cloud 7.3.2 — Platform optimisations, SMS timeout

**Improvements**

* Info page access: the separate access-trigger setting has been removed; the platform now uses the file retention setting to control access consistently
* Database queries for webhook delivery have been optimised, reducing platform load during high-traffic periods
* A missing index on the contact table has been added, improving lookup performance

**Bug fixes**

* Diag notification emails now use the correct custom domain when one is configured
* SMS validation requests now time out gracefully instead of blocking the invitation flow
{% endupdate %}

{% update date="2025-07-02" tags="visual-engagement,new-feature,improvement,fix" %}
## Cloud 7.3.0 · 7.3.1 — Storage quota alerts, MapTiler geocoding

**New features**

* **Storage quota alerts**: administrators receive an email notification when storage usage reaches **80%** and again at **100%** of the plan quota
* Geocoding (used for geolocation snapshots in Diag) now uses **MapTiler** instead of Google Maps — no Google API key required
* Webhook URLs can now be saved even when no webhooks are currently active, allowing administrators to pre-configure integrations
* Supervisors can now create tickets via the API using the supervisor role credentials

**Bug fixes**

* Several API response fixes for ticket and session endpoints
{% endupdate %}

{% update date="2025-06-11" tags="visual-engagement,new-feature,improvement" %}
## Cloud 7.2.6 — PDF export by API, Genesys connector enhancements

**New feature — PDF export via API**

Diag session reports can now be exported as PDF programmatically via the REST API, and shared by email directly from the API response.

**Genesys connector**

* The **Reference** field now accepts up to **65 characters** (was 32)
* Webhook payloads sent to Genesys now include richer session metadata
{% endupdate %}

{% update date="2025-05-28" tags="visual-engagement,new-feature,improvement,fix" %}
## Cloud 7.2.5 — Session events API, quick-invitation groups

**New feature — session events**

Session lifecycle events are now available:

* New API endpoint: `GET /tickets/:id/events` — returns the full event timeline for a session
* New webhook event: `ticket.events.updated` — triggers whenever a new event is recorded on a session

**Improvements**

* Quick Invitation links now automatically assign the guest to the correct user group based on the service configuration
* Meet conference search is now available via the API (`GET /conferences`)

**Bug fixes**

* Various fixes for invitation edge cases and notification delivery
{% endupdate %}

{% update date="2025-04-23" tags="visual-engagement,security,fix" %}
## Cloud 7.2.4 — Security hardening, bug fixes

**Security**

* Info page URL is now hardened against enumeration attacks

**Bug fixes**

* Platform latency reduced under high concurrent session load
* Session timeline no longer auto-scrolls unexpectedly when an agent is reading older events
* Multi-participant session: invitation notification is now sent to all participants correctly
* Various theme rendering fixes (button colours, spacing)
{% endupdate %}

{% update date="2025-04-09" tags="visual-engagement,new-feature,improvement" %}
## Cloud 7.2.0 — Multi-participant assistance

**New feature — multi-participant sessions**

Agents can now **invite multiple people to the same Diag session** simultaneously:

* A new **Participants** section in the ticket panel lists all invited guests and their connection status
* Each guest receives their own invitation link; all streams appear in the same session view
* A **Join** button lets a second agent join an ongoing session
* Guest URLs can be copied individually for manual sharing

**Meet — screen sharing restriction**

Screen sharing in Meet is now restricted to **individual tabs or windows**. Full-desktop capture is no longer offered, aligning with enterprise security policies.

**Quick Invitation**

The portal now shows a dedicated **Quick Invitation** button that replaces the old multi-step flow.
{% endupdate %}

{% update date="2025-03-26" tags="visual-engagement,fix,security" %}
## Cloud 7.1.10 — Bug fixes

* **Diag with custom domain**: session timeline events are now correctly recorded for enterprises using a custom domain (e.g. Keyyo)
* **Webhooks**: media webhook payloads now include the `conference` object (was missing; documented but absent)
* **SSO**: certificate validation is now enforced when verifying the ID token in OpenID Connect mode
* **Conference payment**: the card brand selector is now shown in post-session payment forms, as required by new EU payment regulations
* Scheduled Diag invitation: guests who previously declined an invitation no longer receive a 404 when clicking the link again — they are redirected to the ticket information page
* Sub-enterprise management: admins without an explicit role assigned no longer get locked out of the menu
* Subscription confirmation email is now sent correctly on first monthly subscription
{% endupdate %}

{% update date="2025-03-12" tags="visual-engagement,new-feature,improvement,fix" %}
## Cloud + Diag — Laravel 11 upgrade, new guest UX

**Infrastructure**

* The platform has been upgraded to **Laravel 11**, improving performance and security baseline

**Diag — new guest experience**

* The guest entry screen has been redesigned with a cleaner layout
* The end-of-session screen has been updated to match the new design system

**Bug fixes**

* Meet: duplicate survey submission is now blocked
* Diag: session statistics are computed correctly after the Laravel 11 migration
* Re-invitation timer: the cooldown before a guest can be re-invited now resets correctly
{% endupdate %}

{% update date="2025-02-12" tags="visual-engagement,new-feature,improvement" %}
## Cloud 7.1.6 — Multi-service invitation page (lot 2)

Building on the multi-service quick invitation page introduced in 7.1.3, this release adds:

* **Email and SMS support**: guests can now receive the quick-invitation link by email or SMS, not just by direct URL copy
* **URL parameters**: the invitation URL accepts `phone`, `email`, and `service_key` query parameters for pre-filling the form
* **Set as homepage**: the multi-service invitation page can be set as the default landing page for an enterprise
* **Multi-recipient paste**: agents can paste a comma-separated list of recipients to send to multiple guests at once

**Other improvements**

* Geolocation snapshot: timeout is now configurable to avoid blocking the session on slow GPS fixes
* Tickets stats API: the `created_at` field is now included in the response
{% endupdate %}

{% update date="2025-01-22" tags="visual-engagement,new-feature,improvement,security,fix" %}
## Cloud 7.1.4 — Service inheritance, user group APIs, security

**New features**

* **Service inheritance visibility**: child services now clearly show which settings are inherited from a parent service, and administrators can override them individually
* **User group management APIs**: user groups can now be created, updated, and deleted via the REST API

**Security**

* Enterprise listing endpoint now requires authentication (was publicly accessible)
* Super-admin access can be restricted to a configurable list of IP ranges

**Improvements**

* The trigger previously called "Pass to Completed" has been renamed to better reflect its function
* Media file security restrictions have been re-enabled after being temporarily relaxed during a migration

**Bug fixes**

* Tickets no longer auto-close unexpectedly when a guest disconnects briefly
* GCS invitation link generation fixed for enterprises with custom storage configurations
* SMS invitation link pre-loading now works correctly on the guest entry page
* Webhook names are now validated to prevent duplicate names within the same enterprise
{% endupdate %}

{% update date="2024-12-10" tags="visual-engagement,new-feature,improvement" %}
## Cloud 7.1.3 — Multi-service quick invitation, streamlined media editing

**New feature — multi-service Diag quick invitation page**

A new dedicated URL (`/quick-invitation`) serves a **service selector page** for enterprises with multiple Diag services:

* Guests select the appropriate service from a list before joining
* The service can be pre-selected via a `service_key` URL parameter
* Agents can share a single URL that adapts to the guest's choice

**Improvement — media editing**

* Editing a media file (image, PDF) now requires only **2 clicks** instead of navigating through a dialog
* **Drag-to-reorder** within a ticket now also reorders the pages in the exported PDF
{% endupdate %}

{% update date="2024-12-04" tags="visual-engagement,new-feature" %}
## Cloud 7.1.2 — Webhook event filtering

Administrators can now **select which event types trigger webhook deliveries** at the service level. Previously, all events were sent to all configured webhook endpoints. This reduces noise for integrations that only care about specific events (e.g. `ticket.closed` only).
{% endupdate %}

{% update date="2024-11-20" tags="visual-engagement,improvement,fix" %}
## Cloud 7.1.1 — SMS quota, Diag multi-call stats

**Improvements**

* SMS quota is now enforced at send time — invitations that would exceed the plan's SMS allowance are blocked with a clear error rather than silently failing
* Diag multi-call session statistics (duration, number of calls per ticket) are now computed correctly when a ticket involves more than one consecutive session

**Bug fixes**

* CPU usage spikes during peak concurrent sessions have been reduced
* CSPN report: CSV export no longer fails for enterprises with special characters in their name
* SSO waiting room: guests using SSO authentication are no longer sent to a blank page while waiting for an agent
{% endupdate %}

{% update date="2024-10-30" tags="visual-engagement,improvement" %}
## Cloud 7.1.0 — REST API overhaul

The REST API has been significantly updated to improve consistency and developer experience:

* **Deprecated endpoints removed**: endpoints marked deprecated in 6.x are no longer available
* **Routes standardised**: URL patterns are now consistent across all resources (plural nouns, version prefix)
* **Routes alphabetised**: resources are listed alphabetically in the OpenAPI specification for easier navigation
* **Richer error messages**: validation errors now return field-level detail instead of generic 422 responses
* **New query parameters**: several list endpoints now accept additional filtering and sorting parameters

Refer to the API reference for the full list of changes and migration notes.
{% endupdate %}

{% update date="2024-10-09" tags="visual-engagement,improvement,fix" %}
## Cloud 7.0.10 · Meet 4.40.3 — Notification inheritance, SSO fixes

**Cloud 7.0.10**

* **Notification template inheritance**: Closed, Cancelled, and Rejected ticket notifications now correctly inherit templates defined at the parent enterprise level
* **Conference visibility**: participants can now see a conference in the portal without requiring an explicit invitation link (access controlled by service configuration)
* **Information page**: the API link on the information page is now independent from the form access setting — the two can be configured separately
* **PDF export**: enterprise logo now renders correctly in all PDF export configurations

**Meet 4.40.3**

* End-page redirect: the `name` URL parameter is now correctly passed through to the post-session redirect URL
* SSO auto-authentication: guests joining via a room link with SSO configured are now authenticated automatically without a manual login step
{% endupdate %}

{% endupdates %}
