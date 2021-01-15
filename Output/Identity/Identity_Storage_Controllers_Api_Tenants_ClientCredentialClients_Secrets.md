---
title: Identity_Storage_Controllers_Api_Tenants_ClientCredentialClients_Secrets
  v20210115.07
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_controllers_api_tenants_clientcredentialclients_secrets-secrets">Secrets</h1>

## GET Secrets

<a id="opIdSecrets_GetClientCredentialClientSecrets"></a>

Get all secrets for a Client Credential Client.
            Total number of secrets in the Client set in the
            Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

<h3 id="secrets_getclientcredentialclientsecrets-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="secrets_getclientcredentialclientsecrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Client Credential Secret information found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Expiration": "2019-08-24T14:15:22Z",
    "Expires": true,
    "Description": "string",
    "Id": 0
  }
]
```

## POST Secrets

<a id="opIdSecrets_AddClientCredentialClientSecret"></a>

Add a new Secret to a Client Credential Client.
            A Client can have a maximum of 10 secrets.
            We advise against creating secrets that do not expire.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

### Request Body

ClientSecretCreateOrUpdate object.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_addclientcredentialclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="secrets_addclientcredentialclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse](#schemaclientsecretresponse)|Client Credential Client Secret updated information.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0,
  "Secret": "string"
}
```

## HEAD Secrets

<a id="opIdSecrets_GetClientCredentialClientSecretsHeader"></a>

Return total number of Secrets in a Client. The value
            will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return
            any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

<h3 id="secrets_getclientcredentialclientsecretsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="secrets_getclientcredentialclientsecretsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Client Credential Client Secret header information.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## GET Secrets

<a id="opIdSecrets_GetClientCredentialClientSecret"></a>

Get a Client Credential Client Secret.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_getclientcredentialclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_getclientcredentialclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Client Credential Client Secret information specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0
}
```

## PUT Secrets

<a id="opIdSecrets_UpdateClientCredentialClientSecret"></a>

Update a Client Credential Client Secret.
            It can take up to one hour for the update
            to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

### Request Body

ClientSecretCreateOrUpdate object. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_updateclientcredentialclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_updateclientcredentialclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Updated Client Credential Client Secret information.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0
}
```

## DELETE Secrets

<a id="opIdSecrets_DeleteClientCredentialClientSecret"></a>

Delete a Secret from a Client Credential Client.
            It can take up to one hour for deletion to manifest
            in the authentication process. Access tokens issued
            using this Secret will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_deleteclientcredentialclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_deleteclientcredentialclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
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

## HEAD Secrets

<a id="opIdSecrets_GetClientCredentialClientSecretHeader"></a>

Validate that a Secret with given Id exists in the Client.
            This endpoint is identical to the GET one but it does not
            return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_getclientcredentialclientsecretheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_getclientcredentialclientsecretheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Client Credential Client Secret.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Secret, Client, or Tenant not found.|
|500|None|Internal server error.|

## GET Secrets

<a id="opIdSecrets_GetV1PreviewClientCredentialClientSecrets"></a>

Get all secrets for a Client Credential Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

<h3 id="secrets_getv1previewclientcredentialclientsecrets-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="secrets_getv1previewclientcredentialclientsecrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Client Credential Client Secrets found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Expiration": "2019-08-24T14:15:22Z",
    "Expires": true,
    "Description": "string",
    "SecretId": "string",
    "Id": "string"
  }
]
```

## POST Secrets

<a id="opIdSecrets_AddV1PreviewClientCredentialClientSecret"></a>

Add a new secret for a Client Credential Client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets
```

### Request Body

Client Secret to create.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_addv1previewclientcredentialclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="secrets_addv1previewclientcredentialclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse2](#schemaclientsecretresponse2)|Client Credential Client Secret created.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Client or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string",
  "ClientSecret": "string",
  "Secret": "string"
}
```

## GET Secrets

<a id="opIdSecrets_GetV1PreviewClientCredentialClientSecret"></a>

Get a specific Client Credential Client Secret.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_getv1previewclientcredentialclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>`integer(int32) secretId`<br/>Id of secret.</br></br>

<h3 id="secrets_getv1previewclientcredentialclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Client Credential Client Secret specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string"
}
```

## PUT Secrets

<a id="opIdSecrets_UpdateV1PreviewClientCredentialClientSecret"></a>

Update a Client Credential Client Secret
            Only Secret Description and Secret Expiration Date can be updated.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}/Secrets/{secretId}
```

### Request Body

Client Secret details.<br/>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}
```

<h3 id="secrets_updatev1previewclientcredentialclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>`integer(int32) secretId`<br/>secretId.</br></br>

<h3 id="secrets_updatev1previewclientcredentialclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Updated Client Credential Client Secret.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Secret, Client, or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string"
}
```

# Schemas

<h2 id="tocS_ClientSecret">ClientSecret</h2>

<a id="schemaclientsecret"></a>
<a id="schema_ClientSecret"></a>
<a id="tocSclientsecret"></a>
<a id="tocsclientsecret"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ClientSecretCreateOrUpdate](#schemaclientsecretcreateorupdate)|false|none|Object to write a Client Secret.|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|Client Secret Object.|
|» Id|integer(int32)|false|none|Gets or sets id for this Secret.|

<h2 id="tocS_ClientSecretCreateOrUpdate">ClientSecretCreateOrUpdate</h2>

<a id="schemaclientsecretcreateorupdate"></a>
<a id="schema_ClientSecretCreateOrUpdate"></a>
<a id="tocSclientsecretcreateorupdate"></a>
<a id="tocsclientsecretcreateorupdate"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string"
}

```

Object to write a Client Secret.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Expiration|string(date-time)¦null|false|none|Gets or sets expiration date for the client secret. Will be null if the secret does not expire.|
|Expires|boolean¦null|false|none|Gets or sets determines if the secret expires. Defaults to true.<br />If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced.<br />If Expires is set to true (or null) and Expiration is null, a 400 error will be returned.<br />If Expires is set to false and Expiration is not null, a 400 error will be returned.<br />If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string¦null|false|none|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying<br />secrets easier.|

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

<h2 id="tocS_ClientSecretResponse">ClientSecretResponse</h2>

<a id="schemaclientsecretresponse"></a>
<a id="schema_ClientSecretResponse"></a>
<a id="tocSclientsecretresponse"></a>
<a id="tocsclientsecretresponse"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "Id": 0,
  "Secret": "string"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ClientSecret](#schemaclientsecret)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|Object returned after a Client Secret is created.|
|» Secret|string¦null|false|none|Gets or sets client secret.|

<h2 id="tocS_ClientSecret2">ClientSecret2</h2>

<a id="schemaclientsecret2"></a>
<a id="schema_ClientSecret2"></a>
<a id="tocSclientsecret2"></a>
<a id="tocsclientsecret2"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ClientSecretCreateOrUpdate](#schemaclientsecretcreateorupdate)|false|none|Object to write a Client Secret.|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» SecretId|string¦null|false|none|none|
|» Id|string¦null|false|none|none|

<h2 id="tocS_ClientSecretResponse2">ClientSecretResponse2</h2>

<a id="schemaclientsecretresponse2"></a>
<a id="schema_ClientSecretResponse2"></a>
<a id="tocSclientsecretresponse2"></a>
<a id="tocsclientsecretresponse2"></a>

```json
{
  "Expiration": "2019-08-24T14:15:22Z",
  "Expires": true,
  "Description": "string",
  "SecretId": "string",
  "Id": "string",
  "ClientSecret": "string",
  "Secret": "string"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ClientSecret2](#schemaclientsecret2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» ClientSecret|string¦null|false|none|none|
|» Secret|string¦null|false|none|none|

