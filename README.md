Checking-for-Compromised-Accounts

Overview:
We want to inform our users if their account has been involved in a security breach on another site since their last login. Since people sometimes reuse passwords across multiple sites, we'll encourage them to update their information in case their password is no longer secure.

Our goal:
Hitting an external breach data API called Hack Check.
Look for recent breaches that involve passwords. Limit the breaches in sampleResponse to breaches where:

- IsSensitive is false
- DataClasses array contains the value 'Passwords'
- AddedDate is after the user's lastLogin

Suggest password change:
Now that we know the recent breaches the user has been involved in, we want to show a warning on their Dashboard if they have been involved in any breaches.
When the user logs in, if they have any breaches, show an Alert card with listed breaches information fetched from the API response.

Dismiss button on Alert Card:
The button to dismiss in the Alert dialog should dismiss the alert for the rest of the user's session.

No alerts:
If no recent breaches being found or the alert has been dismissed, show "No alerts" inside the card body.

Test users provided:
You can use the following accounts to test, which are located in src/sample/users.js. The safe user is to return no breaches, and the unsafe user is to return breaches.

User with no breaches ("Safe User")
Email: safe@example.com
Password: pw

User with breaches ("Unsafe User")
Email: test@example.com
Password: pw
