# Murmur

Murmur is a personal, non-commercial research tool. It looks for problems that
non-technical people repeatedly ask for help with in public online communities,
so I can find needs that could be solved with small, simple tools.

The source code lives in a private repository. Access is available on request.

## What it does

- Collects public posts and comments from a few everyday communities
  (personal finance, DIY, parenting, travel, pets, cooking, etc.) and public app
  reviews, using official APIs only.
- Groups similar posts by topic and summarizes the problems that come up again
  and again (for example, "many parents struggle to track shared custody schedules").
- Produces private notes for my own use. Nothing is published.

## Reddit usage

- **Read-only.** It never posts, comments, votes or sends messages.
- **OAuth script app**, single user (my own account).
- **Low volume.** It polls `/r/{sub}/new` and `/comments/{id}` every few hours on
  about 10-20 public subreddits. That is a few thousand items per day at most, well below the
  rate limits. It sends a descriptive User-Agent and backs off on HTTP 429.
- **Privacy.** Usernames are never stored in clear text (salted SHA-256 hash).
  Content deleted on Reddit is removed from the local database when detected.
- **No AI training.** Short excerpts are analyzed to summarize recurring
  problems. No Reddit data is used to train models, and nothing is sold, shared or
  republished.

## Stack

Python, PostgreSQL with pgvector, Docker Compose, running on a single home server.

## Contact

Open an issue in this repository.
