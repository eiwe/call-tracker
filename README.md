# Weekly Call Tracker

A simple web app to track weekly calls with team members.

## Default Password

```
calltracker123
```

## How to Change the Password

1. Open your browser console (F12 or right-click > Inspect > Console)
2. Run this command with your desired password:
```javascript
await crypto.subtle.digest('SHA-256', new TextEncoder().encode('YourPasswordHere')).then(h => Array.from(new Uint8Array(h)).map(b => b.toString(16).padStart(2, '0')).join(''))
```
3. Copy the output hash
4. Open `index.html` and replace the `PASSWORD_HASH` value (around line 288) with your new hash

## Features

- Track 6 team members: Sagat, Kellerman, Sidle, Merlis, Terezakis, DeVito
- Automatic reset every Wednesday at 9:00 PM
- Deadline countdown to next Wednesday at 7:00 PM
- Progress tracking with visual progress bar
- 30-day authentication session
- Data persists in browser localStorage

## Security Note

This uses client-side password protection, which means the password hash is visible in the source code. This is suitable for keeping casual visitors out, but is NOT secure against determined attackers. For true security, use server-side authentication.
