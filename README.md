# NextAuth Session Null on Client-Side in Next.js 15

This repository demonstrates a bug where the NextAuth session is always null on the client-side in a Next.js 15 application, even though server-side verification appears to be successful.

## Bug Description
The `unstable_getServerSession` function retrieves the session correctly on the server, but the client-side always receives a null session object. This makes client-side authentication impossible.

## Steps to Reproduce
1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Navigate to `/about`.  The console will show a null session, and the UI will show 'You are not logged in' even if logged in.

## Expected Behavior
The client-side should receive the authenticated session object from NextAuth.

## Actual Behavior
The client-side always receives a null session object, regardless of authentication status.

## Solution
The solution involves ensuring proper session persistence between server and client rendering. This often requires re-fetching data on the client after rendering, leveraging cookies or similar methods for managing the authentication state.