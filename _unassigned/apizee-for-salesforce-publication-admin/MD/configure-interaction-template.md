# How to configure the interaction template

The interaction template defines how a video call session works for your organization. It controls two things: the **sequence of steps** each user follows, and the **features** available during the call.
 
You edit the interactionTemplate on the **Flow** page of the Admin portal.

## Access the Flow page

1. Log in to the Admin portal.
2. Click **Flow** in the left navigation.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The Flow page opens with a JSON editor showing the current configuration. |
| --- | --- |

* * *

##

## Structure of the flow JSON
The flow contains two top-level sections: agent and guest. Each section defines an initialStep and a list of steps.

```json
{
  "agent": {
    "initialStep": "invitation",
    "steps": [...]
  },
  "guest": {
    "initialStep": "consent",
    "steps": [...]
  }
}
```

```json
{
  "agent": {
    "initialStep": "invitation",
    "steps": [...]
  },
  "guest": {
    "initialStep": "consent",
    "steps": [...]
  }
}
```


Each step has the following fields:

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `key` | string | Yes | Name of the step. Must be a valid step key (see tables below). |
| `target` | string | No | Key of the next step after this one completes. |
| `options` | object | No | Step-level display options. |
| `functions` | array | No | List of features to configure for this step. |

| ![Information](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/info.png) | Features defined in functions apply globally, not only during the step they are declared in. You can declare all features on the same step for clarity.<br>The application adds an error step automatically if it is absent from the list. |
| --- | --- |

### **Agent steps**

Valid `key` values for the `agent` section:
 | Key | Description |
| --- | --- |
| `standingBy` | Waiting screen before a call starts. |
| `invitation` | The agent sends an invitation to the guest. |
| `device` | The agent authorizes camera and microphone. |
| `visio` | The video call is active. |
| `error` | Error screen. Added automatically if absent. |
### **Guest steps**

Valid `key` values for the `guest` section:
 | Key | Description |
| --- | --- |
| `consent` | The guest accepts the legal consents. |
| `device` | The guest authorizes camera and microphone. |
| `entry` | The guest tests devices before joining. |
| `waiting` | The guest waits for the agent to accept (moderation). |
| `visio` | The video call is active. |
| `end` | End-of-call screen. |
| `error` | Error screen. Added automatically if absent. |

| ![Information](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/info.png) | To skip, for example, the consent step, set initialStep to device and remove consent from the steps list.<br>To enable the moderation waiting room, include waiting as a step and set it as the target of entry. |
| --- | --- |

## Features reference

Features configure which buttons and behaviors are available during the call. Declare them in the `functions` array of any step.
 
### **Boolean features**

These features control button visibility and default state.
 | `key` | Section | `isVisible` | `isActive` | Default |
| --- | --- | --- | --- | --- |
| `camera` | agent, guest | Shows the camera button | Camera on at start | visible, active |
| `micro` | agent, guest | Shows the microphone button | Mic on at start | visible, active |
| `snapshot` | agent | Shows the snapshot button | — | visible |
| `screenSharing` | agent | Shows the screen share button | — | visible |
| `laser` | agent | Shows the laser pointer button | — | visible |
| `torch` | agent | Shows the guest flashlight button | — | visible |
| `switchCamera` | agent, guest | Shows the switch camera button | — | visible |
| `helpAndDebug` | agent | Shows the help and debug button | — | visible |
| `invitationSms` | agent | Shows the SMS invitation option | — | active |
| `invitationMail` | agent | Shows the email invitation option | — | active |
| `transcription` | agent | Shows the transcription button | Transcription starts automatically | hidden |
**Syntax:**
 
```json
{ "key": "camera", "isVisible": true, "isActive": true }


```

```json
{ "key": "camera", "isVisible": true, "isActive": true }


```


```

```


* `isVisible: true` — the button appears in the call bar.
* `isVisible: false` — the button is hidden.
* `isActive: true` — the feature starts automatically (camera on, mic on, transcription running).
* `isActive: false` — the feature is off by default. The user must activate it manually.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/warning.png) | isActive has no effect when isVisible is false.<br>If camera is hidden, snapshot, laser, and torch are also hidden automatically for the agent. |
| --- | --- |

### **Value features**

These features accept a specific value instead of `isVisible` / `isActive`.
 | `key` | Section | Type | Values | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `facingMode` | guest | string | `"user"`, `"environment"` | `"user"` | Default camera direction for the guest. Use `"environment"` for the rear camera. |
| `limitParticipants` | agent | number | Integer ≥ 1 | `3` | Maximum number of guest participants the agent can invite. | 
**Syntax:**
 

```json
{ "key": "facingMode", "value": "environment" }
{ "key": "limitParticipants", "value": 5 }
```

```json
{ "key": "facingMode", "value": "environment" }
{ "key": "limitParticipants", "value": 5 }
```


### 

### **Step options**

Step options configure display behavior for a specific step.
 | Option | Step | Type | Default | Description |
| --- | --- | --- | --- | --- |
| `isFocused` | `guest.visio` | boolean | `true` | When `true`, the guest's own video stream is displayed in the large view. When `false`, the agent's stream is in the large view. | 
**Syntax:**
 
```json
{
  "key": "visio",
  "target": "end",
  "options": { "isFocused": false }
}
```

```json
{
  "key": "visio",
  "target": "end",
  "options": { "isFocused": false }
}
```

```

```


* * *

## Save, cancel, or reset
 
**To save changes:**

1. Edit the JSON in the editor.
2. Click **Save**.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The new configuration applies to all future calls. |
| --- | --- |

**To cancel unsaved changes:**

1. Click **Cancel**.
2. Confirm in the dialog.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The editor reverts to the last saved configuration. |
| --- | --- |

**To reset to defaults:**

1. Click **Reset**.
2. Confirm in the dialog.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The flow is deleted. The application uses the default settings. |
| --- | --- |

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/warning.png) | The JSON must be valid before you can save. The editor shows an error indicator if the format is incorrect. |
| --- | --- |

> 

## Complete example
 
This example shows a complete flow configuration with common features set:

```json
{
  "agent": {
    "initialStep": "invitation",
    "steps": [
      { "key": "invitation", "target": "device" },
      { "key": "device",     "target": "visio"  },
      {
        "key": "visio",
        "target": "invitation",
        "functions": [
          { "key": "camera",           "isVisible": true,  "isActive": true  },
          { "key": "micro",            "isVisible": true,  "isActive": true  },
          { "key": "snapshot",         "isVisible": true                     },
          { "key": "screenSharing",    "isVisible": true                     },
          { "key": "laser",            "isVisible": true                     },
          { "key": "transcription",    "isVisible": true,  "isActive": false },
          { "key": "invitationSms",    "isVisible": true                     },
          { "key": "invitationMail",   "isVisible": true                     },
          { "key": "limitParticipants","value": 3                            }
        ]
      },
      { "key": "error", "target": "invitation" }
    ]
  },
  "guest": {
    "initialStep": "consent",
    "steps": [
      { "key": "consent", "target": "device" },
      { "key": "device",  "target": "entry"  },
      { "key": "entry",   "target": "visio"  },
      {
        "key": "visio",
        "target": "end",
        "options": { "isFocused": true },
        "functions": [
          { "key": "camera",     "isVisible": true, "isActive": true },
          { "key": "micro",      "isVisible": true, "isActive": true },
          { "key": "facingMode", "value": "user"                     }
        ]
      },
      { "key": "end"   },
      { "key": "error" }
    ]
  }
}
```

```json
{
  "agent": {
    "initialStep": "invitation",
    "steps": [
      { "key": "invitation", "target": "device" },
      { "key": "device",     "target": "visio"  },
      {
        "key": "visio",
        "target": "invitation",
        "functions": [
          { "key": "camera",           "isVisible": true,  "isActive": true  },
          { "key": "micro",            "isVisible": true,  "isActive": true  },
          { "key": "snapshot",         "isVisible": true                     },
          { "key": "screenSharing",    "isVisible": true                     },
          { "key": "laser",            "isVisible": true                     },
          { "key": "transcription",    "isVisible": true,  "isActive": false },
          { "key": "invitationSms",    "isVisible": true                     },
          { "key": "invitationMail",   "isVisible": true                     },
          { "key": "limitParticipants","value": 3                            }
        ]
      },
      { "key": "error", "target": "invitation" }
    ]
  },
  "guest": {
    "initialStep": "consent",
    "steps": [
      { "key": "consent", "target": "device" },
      { "key": "device",  "target": "entry"  },
      { "key": "entry",   "target": "visio"  },
      {
        "key": "visio",
        "target": "end",
        "options": { "isFocused": true },
        "functions": [
          { "key": "camera",     "isVisible": true, "isActive": true },
          { "key": "micro",      "isVisible": true, "isActive": true },
          { "key": "facingMode", "value": "user"                     }
        ]
      },
      { "key": "end"   },
      { "key": "error" }
    ]
  }
}
```
