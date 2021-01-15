---
title: Identity_Storage_CloudControllers_Api_Tenants_Invitations v20210115.08
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_cloudcontrollers_api_tenants_invitations-invitations">Invitations</h1>

## GET Invitations

<a id="opIdInvitations_GetInvitation"></a>

Get an Invitation from Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

<h3 id="invitations_getinvitation-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string invitationId`<br/>Id of Invitation.</br></br>

<h3 id="invitations_getinvitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Invitation specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": 0,
  "TenantId": "string",
  "UserId": "string"
}
```

## PUT Invitations

<a id="opIdInvitations_UpdateInvitation"></a>

Update an Invitation. Expired invitations will not be extended.
            automatically upon updates.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

### Request Body

New InvitationCreateOrUpdate object. Properties that are not set or are null will not be changed.<br/>

```json
{
  "ExpiresDateTime": "2019-08-24T14:15:22Z",
  "State": 0,
  "SendInvitation": true,
  "IdentityProviderId": "string"
}
```

<h3 id="invitations_updateinvitation-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string invitationId`<br/>Id of Invitation.</br></br>

<h3 id="invitations_updateinvitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Invitation](#schemainvitation)|Updated Invitation.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": 0,
  "TenantId": "string",
  "UserId": "string"
}
```

## DELETE Invitations

<a id="opIdInvitations_DeleteInvitation"></a>

Delete an Invitation. Users who already have an Invitation email
            will not be able to sign-up once the Invitation is deleted.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

<h3 id="invitations_deleteinvitation-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string invitationId`<br/>Id of Invitation.</br></br>

<h3 id="invitations_deleteinvitation-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Invitation or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 400 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

## HEAD Invitations

<a id="opIdInvitations_GetInvitationHeader"></a>

Validate that an Invitation exists. This endpoint is identical to the GET
            one, but it does not return an object in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Invitations/{invitationId}
```

<h3 id="invitations_getinvitationheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string invitationId`<br/>Id of Invitation.</br></br>

<h3 id="invitations_getinvitationheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Invitation specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Invitation or Tenant not found.|
|500|None|Internal server error.|

## GET Invitations

<a id="opIdInvitations_GetInvitations"></a>

Get all non-expired invitations from a Tenant. Optionally include expired invitations.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Invitations
```

<h3 id="invitations_getinvitations-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of invitations to skip.</br></br>`[optional] integer(int32) count`<br/>Maximum number of invitations to return.</br></br>`[optional] boolean includeExpiredInvitations`<br/>Specify whether to return expired invitations.</br></br>

<h3 id="invitations_getinvitations-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Invitations found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "Issued": "2019-08-24T14:15:22Z",
    "Expires": "2019-08-24T14:15:22Z",
    "Accepted": "2019-08-24T14:15:22Z",
    "State": 0,
    "TenantId": "string",
    "UserId": "string"
  }
]
```

## HEAD Invitations

<a id="opIdInvitations_GetInvitationsHeader"></a>

Return total number of non-expired Invitations in a Tenant. Optionally include expired invitations.
            The value will be set in the Total-Count header. This endpoint is identical to the GET one but
            it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Invitations
```

<h3 id="invitations_getinvitationsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] boolean includeExpiredInvitations`<br/>Specify to return expired invitations.</br></br>

<h3 id="invitations_getinvitationsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Invitations found.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

# Schemas

<h2 id="tocS_Invitation">Invitation</h2>

<a id="schemainvitation"></a>
<a id="schema_Invitation"></a>
<a id="tocSinvitation"></a>
<a id="tocsinvitation"></a>

```json
{
  "Id": "string",
  "Issued": "2019-08-24T14:15:22Z",
  "Expires": "2019-08-24T14:15:22Z",
  "Accepted": "2019-08-24T14:15:22Z",
  "State": 0,
  "TenantId": "string",
  "UserId": "string"
}

```

Object for an Invitation.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string¦null|false|none|Gets or sets unique Invitation Id.|
|Issued|string(date-time)|false|none|Gets or sets invitation issuing timestamp.|
|Expires|string(date-time)|false|none|Gets or sets invitation expiration timestamp.|
|Accepted|string(date-time)¦null|false|none|Gets or sets invitation accepted timestamp.|
|State|[InvitationStates](#schemainvitationstates)|false|none|Gets or sets invitation state. Can be None (0), InvitationEmailSent (1), InvitationAccepted (2).|
|TenantId|string(guid)|false|none|Gets or sets ID of the Tenant the invitation belongs to.|
|UserId|string(guid)|false|none|Gets or sets ID of the User whom the invitation was issued to.|

<h2 id="tocS_InvitationStates">InvitationStates</h2>

<a id="schemainvitationstates"></a>
<a id="schema_InvitationStates"></a>
<a id="tocSinvitationstates"></a>
<a id="tocsinvitationstates"></a>

```json
0

```

Invitation states.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer|false|none|Invitation states.|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|
|*anonymous*|2|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>

<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}

```

Object returned whenever there is an error.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|any|false|none|none|
|OperationId|string|true|none|Gets or sets operationId of action that caused the Error.|
|Error|string|true|none|Gets or sets error description.|
|Reason|string|true|none|Gets or sets reason for the Error.|
|Resolution|string|true|none|Gets or sets what can be done to resolve the Error.|

<h2 id="tocS_InvitationCreateOrUpdate">InvitationCreateOrUpdate</h2>

<a id="schemainvitationcreateorupdate"></a>
<a id="schema_InvitationCreateOrUpdate"></a>
<a id="tocSinvitationcreateorupdate"></a>
<a id="tocsinvitationcreateorupdate"></a>

```json
{
  "ExpiresDateTime": "2019-08-24T14:15:22Z",
  "State": 0,
  "SendInvitation": true,
  "IdentityProviderId": "string"
}

```

Object used to create or update an Invitation.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ExpiresDateTime|string(date-time)¦null|false|none|Gets or sets invitation expiration date. Must be in the future.<br />Maximum allowed is two month in the future.<br />Defaults to 21 days on creation.<br />It should be in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) and either<br />include a *Z* at the end to represent UTC timezone<br />or include the offset in hours. If neither is present<br />time will be treated in the local time zone of the server.|
|State|[InvitationStates](#schemainvitationstates)¦null|false|none|Gets or sets set the state of invitation. For OSISoft internal use only.|
|SendInvitation|boolean¦null|false|none|Gets or sets send an invitation email. Invitation will be sent to the<br />ContactEmail in the User this invitation is attached to.<br />Default is true.|
|IdentityProviderId|string(guid)¦null|false|none|Gets or sets Identity Provider to use for accepting this invitation.<br />Required when creating an Invitation.|

