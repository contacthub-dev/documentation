---
title: Activities
---

# Activities

The custom Activity types for the service are related to contact information
management and sharing:

- `CreateContactInfo`: Create new contact information.
- `UpdateContactInfo`: Update existing contact information.
- `DeleteContactInfo`: Delete contact information.
- `ShareContactInfo`: Share contact information with another user.
- `AcceptShare`: Accept a request to share contact information.
- `RejectShare`: Reject a request to share contact information.
- `RequestContactInfo`: User B requests contact information from User A.
- `AcceptRequest`: User A accepts the request from User B.
- `RejectRequest`: User A rejects the request from User B.

## CreateContactInfo

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "CreateContactInfo",
  "id": "https://example.com/user/username/activity/createcontactinfo",
  "actor": "https://example.com/user/username",
  "object": "https://example.com/user/username/contactinfo"
}
```

## ShareContactInfo

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "ShareContactInfo",
  "id": "https://example.com/user/username/activity/sharecontactinfo",
  "actor": "https://example.com/user/username",
  "object": "https://example.com/user/username/contactinfo",
  "target": "https://otherinstance.com/user/otheruser"
}
```

## AcceptShare

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "AcceptShare",
  "id": "https://otherinstance.com/user/otheruser/activity/acceptshare",
  "actor": "https://otherinstance.com/user/otheruser",
  "object": "https://example.com/user/username/activity/sharecontactinfo"
}
```

## RequestContactInfo

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "RequestContactInfo",
  "id": "https://otherinstance.com/user/otheruser/activity/requestcontactinfo",
  "actor": "https://otherinstance.com/user/otheruser",
  "target": "https://example.com/user/username"
}
```

## AcceptRequest

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "AcceptRequest",
  "id": "https://example.com/user/username/activity/acceptrequest",
  "actor": "https://example.com/user/username",
  "object": "https://otherinstance.com/user/otheruser/activity/requestcontactinfo"
}
```

## RejectRequest

```json
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "type": "RejectRequest",
  "id": "https://example.com/user/username/activity/rejectrequest",
  "actor": "https://example.com/user/username",
  "object": "https://otherinstance.com/user/otheruser/activity/requestcontactinfo"
}
```
