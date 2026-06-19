
# Watch "Call started" and "call ended" events in the activity feed of a Case or Incident

{% hint style="info" %}
* The Apizee Visual Support app is installed and activated on your ServiceNow instance.
 * You use the CSM or ITSM Workspace (**modernUI**)
{% endhint %}

When a Fulfiller [starts a new video call](getting-started-apizee-servicenow.md), the start date and time of the call automatically appear in the Case's or Incident's activity feed.

Similarly, when the Guest or the Agent hangs up, a timestamped 'call ended' event is inserted into the Case's or Incident's activity feed.
![](.gitbook/assets/Activity-Feed-CallTime.png)
![](.gitbook/assets/Activity-Feed-End-of-call.png)

# Get snapshots automatically attached to the Case or Incident

The Apizee solution allows Fullfillers to capture snapshots from the guest's front or rear camera stream.

Each time a snapshot is taken, it is automatically uploaded to the Case or Incident attachments, and a new event appears in the Case or Incident's activity feed.

![](.gitbook/assets/Activity-Feed-Snapshot.png)
