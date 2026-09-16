# Sending reminders before Twilio is approved

A2P 10DLC registration gates **automated** texting from a business number.
Twilio's docs are explicit: trial accounts cannot register, and campaign
review currently takes **10-15 days**.

Nothing gates a person texting from their own phone.

So until the campaign is approved, the dashboard does the thinking and Juan
does the sending:

1. The **Reminders to send** panel lists everyone who owes money today or is
   behind, worst first.
2. Each one shows the message already written - name, amount, due date,
   balance after payment, and the four payment handles.
3. **Copy message**, paste into his own texts, send.

This stays useful after Twilio is live: it is the fallback for a customer
who opted out of automated texts but still needs a nudge, and for anyone
without consent recorded.

The automated path replaces step 3 only. Steps 1 and 2 are the same code
(`daily-reminders` uses the same message builder), so nothing is thrown
away.
