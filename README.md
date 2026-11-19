# AnonyForum

An anonymous forum. No accounts, no names, just posts and votes.

## What it does

- Post a title and text with no sign-up. Posts show a generated anonymous name.
- Upvote or downvote. A random id kept in the browser's `localStorage` stops a browser from voting twice on a post.
- The list polls the API every 20 seconds, so it stays fresh without sockets.
- Sort by trending (net votes) or newest.
- An admin view, enabled by a token in `localStorage`, can reply to a post and delete it.

## Stack

- Frontend: Next.js 14, React 18, TypeScript, Tailwind CSS, Axios
- Backend: Node.js, Express 5, MongoDB with Mongoose

## Run it locally

```bash
# backend (port 5000)
cd backend
npm install
npm run dev

# frontend (port 3000)
cd frontend
pnpm install
pnpm dev
```

Backend env vars: `MONGO_URI`, `PORT`, `FRONTEND_URL`

Frontend env vars: `NEXT_PUBLIC_BACKEND_URL` (falls back to a hosted backend that may no longer exist, so set it to `http://localhost:5000`), `NEXT_PUBLIC_ADMIN_TOKEN`

## Notes

Built with [Govindan007](https://github.com/Govindan007).

The old Vercel deployment is gone, so there is no live link. The admin check only happens in the browser, and the reply and delete endpoints have no auth. Fine for a toy, not something to put real people on.
