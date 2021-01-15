---
title: Identity_Storage_CloudControllers_Api_Communities_ClientCredentialClients
  v20210115.08
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_cloudcontrollers_api_communities_clientcredentialclients-clientcredentialclients">ClientCredentialClients</h1>

## HEAD ClientCredentialClients

<a id="opIdClientCredentialClients_GetCommunityClientCredentialClientsCount"></a>

Get Client Credential Client Count for a Community.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_getcommunityclientcredentialclientscount-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of the Tenant that belongs to this Community.</br></br>`string(guid) communityId`<br/>Id of the Community.</br></br>

<h3 id="clientcredentialclients_getcommunityclientcredentialclientscount-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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

## GET ClientCredentialClients

<a id="opIdClientCredentialClients_GetCommunityClientCredentialClients"></a>

Get Client Credential clients for a Community.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_getcommunityclientcredentialclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of the Tenant that belongs to this Community.</br></br>`string(guid) communityId`<br/>Id of Community.</br></br>

<h3 id="clientcredentialclients_getcommunityclientcredentialclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Success.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
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
    "Name": "string",
    "Enabled": true,
    "AccessTokenLifetime": 0,
    "Tags": [
      "string"
    ],
    "RoleIds": [
      "string"
    ]
  }
]
```

## PUT ClientCredentialClients

<a id="opIdClientCredentialClients_AddClientCredentialClientToCommunity"></a>

Add a Client Credential Client to a Community.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_addclientcredentialclienttocommunity-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of the Tenant that belongs to this Community</br></br>`string(guid) communityId`<br/>Id of Community.</br></br>`string clientId`<br/>Id of the Client Credential Client to add to the specified Community.</br></br>

<h3 id="clientcredentialclients_addclientcredentialclienttocommunity-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientCredentialClient](#schemaclientcredentialclient)|Created.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ]
}
```

## DELETE ClientCredentialClients

<a id="opIdClientCredentialClients_RemoveClientCredentialClientFromCommunity"></a>

Remove a Client Credential Client from a Community.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Communities/{communityId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_removeclientcredentialclientfromcommunity-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of the Tenant that belongs to this Community.</br></br>`string(guid) communityId`<br/>Id of Community.</br></br>`string clientId`<br/>Id of the Client Credential Client to remove from the specified Community.</br></br>

<h3 id="clientcredentialclients_removeclientcredentialclientfromcommunity-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|Removed.|
|400|[ErrorResponse](#schemaerrorresponse)|BadRequest.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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

# Schemas

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

<h2 id="tocS_ClientCredentialClient">ClientCredentialClient</h2>

<a id="schemaclientcredentialclient"></a>
<a id="schema_ClientCredentialClient"></a>
<a id="tocSclientcredentialclient"></a>
<a id="tocsclientcredentialclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ]
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Client](#schemaclient)|false|none|Base object used during Client creation.|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|Object to get or update a Client Credential Client.|
|» RoleIds|[string]¦null|false|none|Gets or sets list of Roles to be assigned to this client. Member role is always required.<br />For security reasons we advise against assigning Admin roles to a client.|

<h2 id="tocS_Client">Client</h2>

<a id="schemaclient"></a>
<a id="schema_Client"></a>
<a id="tocSclient"></a>
<a id="tocsclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ]
}

```

Base object used during Client creation.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string¦null|false|none|Gets or sets client ID for this client. This ID should be a GUID.|
|Name|string¦null|false|none|Gets or sets name of Client.|
|Enabled|boolean¦null|false|none|Gets or sets whether client is enabled. Client can be used for authentication<br />if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|integer(int32)¦null|false|none|Gets or sets lifetime of access token issued for this client after authentication.<br />Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|[string]¦null|false|none|Gets or sets for OSIsoft internal use only.|

