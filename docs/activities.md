---
title: Activities
---

# Activities

ContactHub uses various ActivityPub activities to facilitate the sharing and
management of contact information. This document outlines the main activities
used in the service and provides examples of their ActivityPub schemas.

## CreateContactInfo

The `CreateContactInfo` activity is used to create new contact information for a
user.

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Create",
  "actor": "https://example.com/user/username",
  "object": {
    "type": "ContactInfo",
    "id": "https://example.com/user/username/contactinfo",
    "owner": "https://example.com/user/username",
    "name": "John Doe",
    "email": "johndoe@example.com",
    "phone": "+1234567890",
    "address": {
      "addressLine1": "123 Main St",
      "addressLine2": "Apt 4B",
      "addressLine3": null,
      "city": "Anytown",
      "state": "CA",
      "province": null,
      "postalCode": "12345",
      "country": "USA",
      "region": null,
      "subregion": null
    }
  },
  "to": "https://example.com/user/username/followers"
}
```

## UpdateContactInfo

The `UpdateContactInfo` activity is used to update existing contact information
for a user.

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Update",
  "actor": "https://example.com/user/username",
  "object": {
    "type": "ContactInfo",
    "id": "https://example.com/user/username/contactinfo",
    "owner": "https://example.com/user/username",
    "name": "John Doe",
    "email": "johndoe@example.com",
    "phone": "+1234567890",
    "address": {
      "addressLine1": "456 New St",
      "addressLine2": "Apt 8C",
      "addressLine3": null,
      "city": "Anytown",
      "state": "CA",
      "province": null,
      "postalCode": "12345",
      "country": "USA",
      "region": null,
      "subregion": null
    }
  },
  "to": "https://example.com/user/username/followers"
}
```

## DeleteContactInfo

The `DeleteContactInfo` activity is used to delete contact information for a
user.

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Delete",
  "actor": "https://example.com/user/username",
  "object": "https://example.com/user/username/contactinfo",
  "to": "https://example.com/user/username/followers"
}
```

## ShareContactInfo

The `ShareContactInfo` activity is used when a user (User A) wants to share
their contact information with another user (User B).

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Offer",
  "actor": "https://example.com/user/usernameA",
  "object": "https://example.com/user/usernameA/contactinfo",
  "target": "https://example.com/user/usernameB",
  "to": "https://example.com/user/usernameB/inbox"
}
```

## AcceptShare

The `AcceptShare` activity is used when a user (User B) accepts an offer to
share contact information from another user (User A).

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Accept",
  "actor": "https://example.com/user/usernameB",
  "object": {
    "type": "Offer",
    "actor": "https://example.com/user/usernameA",
    "object": "https://example.com/user/usernameA/contactinfo",
    "target": "https://example.com/user/usernameB"
  },
  "to": "https://example.com/user/usernameA/inbox"
}
```

## RejectShare

The `RejectShare` activity is used when a user (User B) rejects an offer to
share contact information from another user (User A).

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Reject",
  "actor": "https://example.com/user/usernameB",
  "object": {
    "type": "Offer",
    "actor": "https://example.com/user/usernameA",
    "object": "https://example.com/user/usernameA/contactinfo",
    "target": "https://example.com/user/usernameB"
  },
  "to": "https://example.com/user/usernameA/inbox"
}
```

## RequestContactInfo

The `RequestContactInfo` activity is used when a user (User B) requests contact
information from another user (User A).

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Offer",
  "actor": "https://example.com/user/usernameB",
  "object": "https://example.com/user/usernameA/contactinfo",
  "to": "https://example.com/user/usernameA/inbox"
}
```

## AcceptRequest

The `AcceptRequest` activity is used when a user (User A) accepts a request for
contact information from another user (User B).

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Accept",
  "actor": "https://example.com/user/usernameA",
  "object": {
    "type": "Offer",
    "actor": "https://example.com/user/usernameB",
    "object": "https://example.com/user/usernameA/contactinfo"
  },
  "to": "https://example.com/user/usernameB/inbox"
}
```

## RejectRequest

The `RejectRequest` activity is used when a user (User A) rejects a request for
contact information from another user (User B).

Example:

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "Reject",
  "actor": "https://example.com/user/usernameA",
  "object": {
    "type": "Offer",
    "actor": "https://example.com/user/usernameB",
    "object": "https://example.com/user/usernameA/contactinfo"
  },
  "to": "https://example.com/user/usernameB/inbox"
}
```

These activities form the core interactions for sharing and managing contact
information in ContactHub. By leveraging the ActivityPub protocol, ContactHub
allows users to communicate and share contact information in a decentralized
manner while preserving privacy.
