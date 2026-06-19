---
description: "Release notes for the Apizee Embed widget, SDK, and integration libraries."
icon: code
---

# Embed

{% updates format="full" %}

{% update date="2026-06-10" tags="embed,new-feature" %}
## Widget v4.2 — floating button positioning

The floating launcher button can now be positioned at any corner of the viewport using the new `position` parameter. A custom offset from each edge is supported.

```js
ApizeeEmbed.init({
  position: 'bottom-left',
  offsetX: 24,
  offsetY: 24,
});
```

* Accepted values: `bottom-right` (default), `bottom-left`, `top-right`, `top-left`
* Position is persisted across page navigations in single-page applications
{% endupdate %}

{% update date="2026-05-20" tags="embed,improvement" %}
## Reduced bundle size

The embed script has been refactored to use dynamic imports. The initial payload is now 18 kB (gzipped), down from 42 kB.

* Core widget logic loads eagerly; video and co-browsing modules load on demand
* No API changes — existing integrations pick up the improvement automatically on next deploy
{% endupdate %}

{% update date="2026-05-05" tags="embed,new-feature" %}
## Dark mode support

The widget now detects the visitor's OS color scheme preference (`prefers-color-scheme`) and switches to a dark theme automatically. The theme can also be forced via configuration.

```js
ApizeeEmbed.init({
  theme: 'dark', // 'light' | 'dark' | 'auto' (default)
});
```
{% endupdate %}

{% update date="2026-04-15" tags="embed,improvement" %}
## Contextual data pre-fill

Agents now receive the visitor's current page URL, page title, and any custom metadata passed via `context` at the start of the session, visible in the session panel.

```js
ApizeeEmbed.init({
  context: {
    plan: 'enterprise',
    accountId: '12345',
  },
});
```
{% endupdate %}

{% update date="2026-03-25" tags="embed,fix" %}
## Fix: widget initialization race condition on SPAs

When the embed script loaded after the route change event on React and Vue applications, the widget could initialize on the wrong page and display an incorrect button state. This is now resolved with a deferred init guard.
{% endupdate %}

{% update date="2026-02-14" tags="embed,breaking-change" %}
## Breaking change: `onSessionEnd` callback signature update

The `onSessionEnd` callback now receives a full session summary object instead of just the session ID. Update your integration if you use this callback.

**Before:**
```js
onSessionEnd: (sessionId) => { ... }
```

**After:**
```js
onSessionEnd: ({ sessionId, duration, rating }) => { ... }
```
{% endupdate %}

{% endupdates %}
