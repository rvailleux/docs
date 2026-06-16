# Architecture Plan: ApizeeLegacy Docs Reorganization

## Overview

This plan implements the architectural decisions for the ApizeeLegacy GitBook site.

## 1. Top-Level Taxonomy (GitBook Site Level)

### Current State
9 top-level tabs mixing product lines, integrations, and FAQ:
- FAQ | Video Assistance | Video Assistance Multi | Meetings | Telehealth | Embed | Salesforce | Genesys | ServiceNow

### Target State
2 section groups + 1 header link:

#### Section Group: Visual Engagement
Contains 5 product spaces (in order):
1. Video Assistance
2. Multi-participant Assistance
3. Meetings
4. Telehealth
5. Embed

#### Section Group: Integration
Contains 3 integration spaces (in order):
1. Salesforce
2. Genesys
3. ServiceNow

#### FAQ
Removed from top tabs. Linked via custom header menu item (top-right).

### Implementation

**Via GitBook UI (recommended, since API write operations require full payload):**
1. Go to https://app.gitbook.com → ApizeeLegacy site → Settings → Structure
2. Create "Visual Engagement" section group
3. Move sections: Video Assistance, Multi-participant Assistance, Meetings, Telehealth, Embed into the group
4. Create "Integration" section group
5. Move sections: Salesforce, Genesys, ServiceNow into the group
6. For FAQ space: uncheck "Show in navigation" to hide it from tabs
7. Go to Settings → Customization → Header
8. Add a link: `FAQ` → `https://apizeelegacy.gitbook.io/apizeelegacy-docs/faq` positioned on the right

**Alternative: Via GitBook API**
- POST `/orgs/{orgId}/sites/{siteId}/section-groups` for each group
- PATCH site-space `hidden: true` for FAQ
- PATCH site customization `header.links[]` for FAQ link

## 2. Per-Space Menu Reorganization (Repo Level)

### Principle

Within each space, the sidebar (`SUMMARY.md`) is reorganized from **per-audience sections** to **action-based categories**.

Admin-only actions are isolated in a dedicated "Administration" section.

### Verified Finding

Side-by-side diff confirms that **per-audience page content is identical** across `admins/`, `agents/`, `guests/` folders for the Embed space (and likely others). The audience-specific folders contain exact copies of the same files.

Therefore, we can safely use **one canonical audience path** per action in the SUMMARY without losing information.

### New SUMMARY Pattern (Embed example)

```
# Summary

## Getting started
* [Authentication](admins/video/log-in-to-video-tool.md)
* [Send an invitation](admins/video/send-an-invitation-to-a-video-session.md)
* [Join as an agent](admins/video/join-a-video-session-as-an-agent.md)
* [Join as a guest](admins/video/join-a-video-session-as-a-guest.md)
* [Leave a video session](admins/video/leave-a-video-session.md)

## During a video session
* [Enable and disable the microphone and camera](admins/video/enable-and-disable-the-microphone-and-camera.md)
* [Take a picture of the guest video](admins/video/take-picture-of-guest-video.md)
* [Change camera](admins/video/change-camera.md)
* [Share the pointer](admins/video/share-pointer.md)
* [Share a screen](admins/video/share-screen.md)
* [Turn on the guest flashlight](admins/video/turn-on-guest-flashlight.md)
* [Configure my video session settings](admins/video/configure-my-video-session-settings.md)

## Portal
* [Log in and log out](admins/portal/log-in-and-log-out.md)
* [Create a new user](admins/portal/create-new-user.md)
* [Create a Service Account](admins/portal/create-service-account.md)
* [Customize the workflow](admins/portal/customize-workflow.md)
* [Check the sessions](admins/portal/check-sessions.md)
* [Download the files](admins/portal/download-files.md)

## Administration
* [Webhook subscriptions](admins/portal/webhook-subscriptions/README.md)
  * [Add a webhook subscription](admins/portal/webhook-subscriptions/add-webhook-subscription.md)
  * [Edit a webhook subscription](admins/portal/webhook-subscriptions/edit-webhook-subscription.md)
  * [Delete a webhook subscription](admins/portal/webhook-subscriptions/delete-webhook-subscription.md)
  * [Enable or disable a webhook subscription](admins/portal/webhook-subscriptions/enable-or-disable-webhook-subscription.md)
* [SSO - Retrieve Microsoft Entra ID data required for SAML federation](admins/sso-retrieve-microsoft-entra-id-data-required-for-saml-federation.md)

## Back-Office (IT operators)
* [Log in and log out](it-operators/back-office/bo-log-in-and-log-out.md)
* [Create a new Tenant (Company)](it-operators/back-office/create-new-tenant-company.md)
```

### Mapping for Other Spaces

The same pattern applies to each space. Here is the category mapping:

| Space | Getting Started | During Session | Portal/Admin | Administration | Other |
|-------|-----------------|----------------|---------------|----------------|-------|
| Embed | Authentication, Invite, Join, Leave | Mic/camera, Picture, Camera, Pointer, Screen, Flashlight, Settings | Log in/out, Create user, Service Account, Workflow, Sessions, Files | Webhooks, SSO | Back-Office (IT) |
| Salesforce | Send invitation, Getting started | Picture, Camera, Pointer, Screen, Flashlight, Settings, Transcription, Leave | — | — | — |
| Genesys | Getting started | — | — | — | — |
| ServiceNow | Getting started | — | — | — | Classic UI |
| Video Assistance | Portal login, Create ticket, Join, User roles | Actions during assistance | Portal mgmt | Configuration, Services, Users | FAQ |
| Meetings | Create conference, Join as guest/organizer | Actions during conference | Portal mgmt | Configuration | FAQ |
| Telehealth | Create appointment, Join as patient/practitioner | Actions during teleconsultation | Portal mgmt | Configuration, Billing | FAQ |
| Multi-participant | Portal login, Create ticket, Join, User roles | Actions during assistance | Portal mgmt | Configuration | FAQ |

### Cleanup Required After SUMMARY Rewrite

1. **Orphaned audience READMEs**: `admins/video/README.md`, `agents/video/README.md`, etc. — identical copies. After SUMMARY rewrite, only one is referenced. The others can be removed or preserved in `_unassigned/`.
2. **Orphaned per-audience page trees**: The `agents/`, `guests/`, `it-operators/` folder trees will no longer be referenced by SUMMARY. GitBook will still serve them by direct URL but they won't appear in the sidebar.
3. **Long-term**: Consider physically deduplicating the per-audience folders (merge into a single `users/` tree) in a future pass.

## 3. Scope & Effort Estimate

| Space | SUMMARY.md Rewrite | Files to Remove/Orphan | Estimate |
|-------|-------------------|----------------------|----------|
| Embed | Yes | ~25 per-audience files | 30 min |
| Salesforce | Yes | ~8 files | 15 min |
| Genesys | Yes ~2 files | 15 min |
| ServiceNow | Yes | ~5 files | 15 min |
| Video Assistance | Yes | ~80 files (4 audiences) | 1 hour |
| Meetings | Yes | ~60 files (3 audiences) | 45 min |
| Telehealth | Yes | ~60 files (3 audiences) | 45 min |
| Multi-participant | Yes | ~80 files (3 audiences) | 1 hour |

**Total effort**: ~4.5 hours of editorial work + GitBook site-level config (~15 min via UI).

## 4. Validation Checklist

After each SUMMARY rewrite:
- [ ] All links resolve to existing `.md` files
- [ ] No orphaned `README.md` referenced by SUMMARY is missing
- [ ] GitBook preview renders the sidebar correctly
- [ ] Cross-space links still work (e.g., `../video-assistance/...`)

After site-level changes:
- [ ] Top nav shows "Visual Engagement" and "Integration" dropdowns
- [ ] FAQ tab is hidden
- [ ] FAQ header link appears top-right on every page
- [ ] All 9 spaces remain reachable by URL (no 404s)
