---
title: Actors
---

# Actors

In ContactHub, there are two primary types of actors involved in the sharing of
contact information: users and servers. Users are individuals who utilize the
service to store and share their contact information, while servers are the
decentralized instances hosting the user data and facilitating communication.

Here is an example of the ActivityPub schema for a ContactHub user's "Person"
actor:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Person",
  "id": "https://example.com/user/username",
  "name": "John Doe",
  "preferredUsername": "username",
  "inbox": "https://example.com/user/username/inbox",
  "outbox": "https://example.com/user/username/outbox",
  "followers": "https://example.com/user/username/followers",
  "following": "https://example.com/user/username/following",
  "url": "https://example.com/user/username",
  "manuallyApprovesFollowers": true
}
```

## User (Person Actor)

Users are represented as "Person" actors in the ActivityPub protocol. Each user
has a unique identifier (id) in the format `https://example.com/user/username`.
A user's "Person" actor includes several important properties, such as `inbox`,
`outbox`, `followers`, and `following`. In ContactHub, we also set the
`manuallyApprovesFollowers` property to `true`, which ensures that the user must
explicitly approve or reject follower requests, enhancing privacy.

### Followers and Following

In ContactHub, the `followers` and `following` properties serve a different
purpose than in traditional social media platforms. Instead of representing a
social connection, these properties indicate the users with whom contact
information can be shared or requested.

When a user (User A) follows another user (User B), User A is requesting access
to User B's contact information. User B must approve this request for User A to
become a follower. Once approved, User A will be able to access User B's shared
contact information. In this context, the `followers` property represents the
users who have been granted access to the user's contact information, and the
`following` property represents the users whose contact information the user can
access.

## Server

Servers in ContactHub are instances that host user data and implement the
ActivityPub protocol to facilitate communication between users. Each server has
its own domain and can interact with other servers in the network. Servers
handle activities such as storing and retrieving contact information, processing
incoming and outgoing ActivityPub messages, and managing user authentication and
authorization.

By using a federated architecture, ContactHub allows users to choose their
preferred server or even host their own server to maintain control over their
data. This decentralization helps ensure user privacy and prevents a single
point of failure or data breach.

For more information on the various activities and objects used in ContactHub,
refer to the [Activities](/activities) and [Objects](/objects) documentation.
