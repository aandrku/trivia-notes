#  Project Descripition
A real time multiplayer quiz game to play with your friends.

# Technical details

## Stack

### Backend
- Language: Go
- HTTP Server 
    - Most likely: Go's stdlib http package or Echo
    - Worth considering: Gin, Fiber
- DB: Postgres

### Frontend
- Next.js + TypeScript

### Hosting and Deployment
- Frontend hosting options:
    - Netlify - very simple, can be done in a couple minutes
    - Include with backend, can be embedded inside Go binary.
    Not very flexible. If backend server goes down, so does frontend.
    - Vercel - I am not familiar with this at all. **Needs research**

- Backend hosting options:
    - AWS - I am not very familiar with this, can be expensive, unless free
    tier. I used to host my personal website on AWS EC2 instance and I believe
    that I dont have much of it left.
    - Linode - This is what I use for my personal website right now. You can get a cheap
    linux server for approximately 5$/month.
    - **Extra** - I've recently came across Caddy and would love to check it out
    as a reverse-proxy to handle our TLS certificates.


## Authentication
- MVP:
    - Simple email + password authentication (store password hashes + salting)
- Post-MVP
    - Oauth2 + email verification (needs research)
    - Possible 2-factor for email auth, would be fun to learn.

## Session management
- JWTs + Cookies

## Game implementation decisions
- We will start by trying to use server sent events (EventSource) 
to send game state updates from the server and regular http request from client side
to interact with the game.
- If SSE won't work for us, we'll probably have to use web sockets.

# Game rules and misc thoughts

## MVP
- Someone has to host the game and share the link, so others could join.
Alternative option: assign an id to each game, then players should be able to use some kinf of 
generated code to join the game.

- Players compete with each other (no teams)
- Players should be able to pick a category for the game.
- Players earn points by answering questions.
- Each question is worth an arbitrary amount of points.
- The quicker you answer the question, more points you get.
- Wrong answer means no points.
- Players should be able to see a ranking, which will show 
how many points each player has earned so far.
- Whoever scores the biggest amount of points wins.

## Post-MVP
- We'll se later

# Desing??

Honestly, idk. I would love to use some kind of pixelated font like in old games,
dark colors with one accent color, square corners, and thick borders.


