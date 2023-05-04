---
title: Actors
---

# Actors

The primary Actor type for this service is the `Person` actor, representing
individual users. Each user will have a unique identifier in the format
`@username@example.com`.

## Person

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Person",
  "id": "https://example.com/user/username",
  "preferredUsername": "username",
  "inbox": "https://example.com/user/username/inbox",
  "outbox": "https://example.com/user/username/outbox",
  "followers": "https://example.com/user/username/followers",
  "following": "https://example.com/user/username/following"
}
```
