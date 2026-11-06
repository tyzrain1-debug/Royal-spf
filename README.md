# ROYAL SPADE — Multiplayer Virtual-Chip Poker Starter

## Included
- React + Vite luxury poker lobby UI
- Express + Socket.IO backend
- Nickname/password demo registration and login
- Virtual-chip wallet starting balance
- Realtime table lobby and table state
- Server-side deck shuffle/deal and basic Texas Hold'em hand ranking
- Fold / check / call / raise controls

## Run locally
1. Install Node.js 20 or newer.
2. Extract this ZIP and open a terminal in this folder.
3. Run `npm install`
4. Copy `.env.example` to `.env` and set a long random `JWT_SECRET`.
5. Run `npm run dev`
6. Open http://localhost:5173 in two browser windows and register two different accounts to test table joining.

## Important limitations before public launch
This is a starter prototype, not a production-ready poker service:
- Users and balances are currently held in server memory and reset when the server restarts.
- The initial betting-round logic is intentionally minimal; it needs full QA for edge cases, side pots, all-ins, disconnect/reconnect, and hand progression.
- Authentication needs rate limiting, email/identity recovery, secure deployment secrets, and persistent database storage.
- Add database transactions, audit logs, anti-cheat controls, abuse prevention, monitoring, and automated tests before public use.
- Omaha and 6 Card Omaha are shown as future game modes; only Texas Hold'em prototype logic is included.
- This project is virtual-chip-only and does not implement cash deposits, withdrawals, or cash-out.

## Deployment architecture
Deploy the Node server to a WebSocket-capable host and the frontend to a static host, or serve the Vite build from the Node app. Set `CLIENT_ORIGIN`, `JWT_SECRET`, and `PORT` in the server environment. Use HTTPS/WSS in production.
