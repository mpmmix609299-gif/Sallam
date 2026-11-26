# Mr pishro — Private Chat

A two-person, password-protected chat starter. Messages are kept only in server memory and are never written to a database or file. When either participant disconnects, the room is cleared for everyone.

## Requirements
- Node.js 18+
- A hosting service that supports a long-running Node.js app and WebSockets
- HTTPS in production

## Run locally
```bash
npm install
```
Set environment variables (do not put real secrets in source code):
```bash
# macOS/Linux
export CHAT_PASSWORD='choose-a-long-unique-shared-password'
export SESSION_SECRET='replace-with-a-long-random-secret'
npm start
```
On Windows PowerShell:
```powershell
$env:CHAT_PASSWORD='choose-a-long-unique-shared-password'
$env:SESSION_SECRET='replace-with-a-long-random-secret'
npm start
```
Open http://localhost:3000/login

## Important privacy notes
- This is a starter project, not a guarantee of absolute privacy.
- Use HTTPS when deployed publicly.
- The app does not store chat messages in a database, but messages may briefly exist in server/client memory and network infrastructure.
- Disconnecting either user clears the room for both. A temporary network drop can therefore clear the chat.
- The default express-session memory store is suitable only for a small demo. For a public deployment, use a carefully configured session store with short expiry, and review hosting logs/backups.
- Anyone who knows the shared password can enter. Do not reuse a personal account password.
