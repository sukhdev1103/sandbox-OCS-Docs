---
title: Identity_Storage_Controllers_Api_Tenants_ImplicitClients v20210115.08
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_controllers_api_tenants_implicitclients-implicitclients">ImplicitClients</h1>

## POST ImplicitClients

<a id="opIdImplicitClients_CreateImplicitClient"></a>

Create an Implicit Client in a Tenant. No Secret will be generated for this
            Client.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/ImplicitClients
```

### Request Body

New ImplicitClient object.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_createimplicitclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="implicitclients_createimplicitclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ImplicitClient](#schemaimplicitclient)|Implicit Client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or Client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Client Id already exists.|
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
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

## GET ImplicitClients

<a id="opIdImplicitClients_GetImplicitClients"></a>

Get all Implicit clients from a Tenant.
            Optionally, get a list of requested clients. Total number
            of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_getimplicitclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. Will be ignored if a list of Ids is passed.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return. Will be ignored if a list of Ids is passed.</br></br>

<h3 id="implicitclients_getimplicitclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Implicit Clients found.|
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
    "RedirectUris": [
      "string"
    ],
    "PostLogoutRedirectUris": [
      "string"
    ],
    "ClientUri": "string",
    "LogoUri": "string",
    "AllowedCorsOrigins": [
      "string"
    ]
  }
]
```

## HEAD ImplicitClients

<a id="opIdImplicitClients_GetImplicitClientsHeader"></a>

Return total number of Implicit clients in a Tenant.
            Optionally, check based on a list of requested clients. The
            value will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return any objects
            in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_getimplicitclientsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only count Clients that have these tags.</br></br>

<h3 id="implicitclients_getimplicitclientsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Implicit Client headers found on Tenant.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## PUT ImplicitClients

<a id="opIdImplicitClients_UpdateImplicitClient"></a>

Update an Implicit Client. It can take up to one hour
            for update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

### Request Body

Updated Implicit Client values. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_updateimplicitclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="implicitclients_updateimplicitclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient](#schemaimplicitclient)|Implicit Client updated.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

## GET ImplicitClients

<a id="opIdImplicitClients_GetImplicitClient"></a>

Get an Implicit Client from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_getimplicitclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="implicitclients_getimplicitclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient](#schemaimplicitclient)|Implicit Client specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

## DELETE ImplicitClients

<a id="opIdImplicitClients_DeleteImplicitClient"></a>

Delete an Implicit Client. It can take up to one hour
            for deletion to manifest in the authentication process. Access
            tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_deleteimplicitclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="implicitclients_deleteimplicitclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

## HEAD ImplicitClients

<a id="opIdImplicitClients_GetImplicitClientHeader"></a>

Validate that an Implicit Client exists.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_getimplicitclientheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="implicitclients_getimplicitclientheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Implicit Client.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## POST ImplicitClients

<a id="opIdImplicitClients_CreateV1PreviewImplicitClient"></a>

Create an Implicit flow Clients.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/ImplicitClients
```

### Request Body

New ImplicitClient object.<br/>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_createv1previewimplicitclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="implicitclients_createv1previewimplicitclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ImplicitClient2](#schemaimplicitclient2)|Implicit Client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Client Id already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

## GET ImplicitClients

<a id="opIdImplicitClients_GetV1PreviewImplicitClients"></a>

Get all Implicit Clients.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ImplicitClients
```

<h3 id="implicitclients_getv1previewimplicitclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="implicitclients_getv1previewimplicitclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Implicit Clients found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "ClientId": "string",
    "Id": "string",
    "Name": "string",
    "Enabled": true,
    "Tags": [
      "string"
    ],
    "RedirectUris": [
      "string"
    ],
    "PostLogoutRedirectUris": [
      "string"
    ],
    "ClientUri": "string",
    "LogoUri": "string",
    "AllowedCorsOrigins": [
      "string"
    ]
  }
]
```

## PUT ImplicitClients

<a id="opIdImplicitClients_UpdateV1PreviewImplicitClient"></a>

Update an Implicit Client.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/ImplicitClients/{clientId}
```

### Request Body

Updated Implicit Client values.<br/>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

<h3 id="implicitclients_updatev1previewimplicitclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="implicitclients_updatev1previewimplicitclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient2](#schemaimplicitclient2)|Updated Implicit Client.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

## GET ImplicitClients

<a id="opIdImplicitClients_GetV1PreviewImplicitClient"></a>

Get an Implicit Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ImplicitClients/{clientId}
```

<h3 id="implicitclients_getv1previewimplicitclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="implicitclients_getv1previewimplicitclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ImplicitClient2](#schemaimplicitclient2)|Implicit Client specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}
```

# Schemas

<h2 id="tocS_ImplicitClient">ImplicitClient</h2>

<a id="schemaimplicitclient"></a>
<a id="schema_ImplicitClient"></a>
<a id="tocSimplicitclient"></a>
<a id="tocsimplicitclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[WebClient](#schemawebclient)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|Object used during Implicit Client creation.|
|» AllowedCorsOrigins|[string]¦null|false|none|Gets or sets the values used by the default CORS policy service implementations to build a<br />CORS policy for JavaScript clients.<br />Maximum 10 for client.|

<h2 id="tocS_WebClient">WebClient</h2>

<a id="schemawebclient"></a>
<a id="schema_WebClient"></a>
<a id="tocSwebclient"></a>
<a id="tocswebclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string"
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
|*anonymous*|object|false|none|Object used during Client creation.|
|» RedirectUris|[string]¦null|false|none|Gets or sets the allowed URIs to which return tokens or authorization codes can be returned.<br />Wildcards are ignored. URIs must match exactly what you are redirecting to<br />after login. If URIs do not match, the authentication process will fail<br />with a bad_client error.<br />Maximum 10 per client.|
|» PostLogoutRedirectUris|[string]¦null|false|none|Gets or sets allowed URIs to redirect to after logout. Wildcards are ignored.<br />URIs must match exactly what you are redirecting to after logout.<br />Maximum 10 for client.|
|» ClientUri|string¦null|false|none|Gets or sets URI to a page with information about client (used on consent screen).|
|» LogoUri|string¦null|false|none|Gets or sets URI to client logo (used on consent screen).|

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

<h2 id="tocS_ImplicitClient2">ImplicitClient2</h2>

<a id="schemaimplicitclient2"></a>
<a id="schema_ImplicitClient2"></a>
<a id="tocSimplicitclient2"></a>
<a id="tocsimplicitclient2"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string",
  "AllowedCorsOrigins": [
    "string"
  ]
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[WebClient2](#schemawebclient2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» AllowedCorsOrigins|[string]¦null|false|none|none|

<h2 id="tocS_WebClient2">WebClient2</h2>

<a id="schemawebclient2"></a>
<a id="schema_WebClient2"></a>
<a id="tocSwebclient2"></a>
<a id="tocswebclient2"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RedirectUris": [
    "string"
  ],
  "PostLogoutRedirectUris": [
    "string"
  ],
  "ClientUri": "string",
  "LogoUri": "string"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Client2](#schemaclient2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» RedirectUris|[string]¦null|false|none|none|
|» PostLogoutRedirectUris|[string]¦null|false|none|none|
|» ClientUri|string¦null|false|none|none|
|» LogoUri|string¦null|false|none|none|

<h2 id="tocS_Client2">Client2</h2>

<a id="schemaclient2"></a>
<a id="schema_Client2"></a>
<a id="tocSclient2"></a>
<a id="tocsclient2"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ClientId|string¦null|false|none|none|
|Id|string¦null|false|none|none|
|Name|string¦null|false|none|none|
|Enabled|boolean¦null|false|none|none|
|Tags|[string]¦null|false|none|none|

