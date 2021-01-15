---
title: Identity_Storage_Controllers_Api_IdentityProviders_ClaimTypeNames v20210115.08
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_controllers_api_identityproviders_claimtypenames-claimtypenames">ClaimTypeNames</h1>

## GET ClaimTypeNames

<a id="opIdClaimTypeNames_GetIdentityProviderClaimTypeNames"></a>

Get all Identity Provider Claim Type Names for an Identity Provider.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames
```

<h3 id="claimtypenames_getidentityproviderclaimtypenames-parameters">Parameters</h3>

`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of Identity Providers to skip.</br></br>`[optional] integer(int32) count`<br/>Maximum number of Identity Providers to return.</br></br>

<h3 id="claimtypenames_getidentityproviderclaimtypenames-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Identity Provider Type Names found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity Provider not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "TypeName": "string",
    "IdentityProviderId": "string"
  }
]
```

## HEAD ClaimTypeNames

<a id="opIdClaimTypeNames_GetIdentityProviderClaimTypeNamesHeader"></a>

Get Header for all Identity Provider Claims Type Names for an Identity Provider.

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames
```

<h3 id="claimtypenames_getidentityproviderclaimtypenamesheader-parameters">Parameters</h3>

`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="claimtypenames_getidentityproviderclaimtypenamesheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Identity Provider Claim Type Names.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity Provider not found.|
|500|None|Internal server error.|

## GET ClaimTypeNames

<a id="opIdClaimTypeNames_GetIdentityProviderClaimTypeName"></a>

Get an Identity Provider Claim Type Name from an Identity Provider.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames/{identityProviderClaimTypeNameId}
```

<h3 id="claimtypenames_getidentityproviderclaimtypename-parameters">Parameters</h3>

`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>`string(guid) identityProviderClaimTypeNameId`<br/>Id of Identity Provider Claim Type Name.</br></br>

<h3 id="claimtypenames_getidentityproviderclaimtypename-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity Proivder Claim Type Name specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity Provider, or Identity Provider Claim Type Name not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}
```

## HEAD ClaimTypeNames

<a id="opIdClaimTypeNames_GetIdentityProviderClaimTypeNameHeader"></a>

Get an Identity Provider Claim Type Name Header from an Identity Provider.

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}/ClaimTypeNames/{identityProviderClaimTypeNameId}
```

<h3 id="claimtypenames_getidentityproviderclaimtypenameheader-parameters">Parameters</h3>

`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>`string(guid) identityProviderClaimTypeNameId`<br/>Id of Identity Provider Claim Type Name.</br></br>

<h3 id="claimtypenames_getidentityproviderclaimtypenameheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Identity Provider Claim Type Name specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity Provider, or Identity Provider Claim Type Name not found.|
|500|None|Internal server error.|

# Schemas

<h2 id="tocS_IdentityProviderClaimTypeName">IdentityProviderClaimTypeName</h2>

<a id="schemaidentityproviderclaimtypename"></a>
<a id="schema_IdentityProviderClaimTypeName"></a>
<a id="tocSidentityproviderclaimtypename"></a>
<a id="tocsidentityproviderclaimtypename"></a>

```json
{
  "Id": "string",
  "TypeName": "string",
  "IdentityProviderId": "string"
}

```

Claim Type Name associated with an Identity Provider.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string(guid)|false|none|Gets or sets the ID for this Claim Type Name.|
|TypeName|string¦null|false|none|Gets or sets the Claim Type Name.|
|IdentityProviderId|string(guid)|false|none|Gets or sets the Identity Provider Id associated with this Claim Type Name.|

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

<h2 id="tocS_IdentityProviderClaim">IdentityProviderClaim</h2>

<a id="schemaidentityproviderclaim"></a>
<a id="schema_IdentityProviderClaim"></a>
<a id="tocSidentityproviderclaim"></a>
<a id="tocsidentityproviderclaim"></a>

```json
{
  "Id": "string",
  "TypeName": "string",
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object representing a claim from an Identity Provider to map to a Role.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string(guid)|false|none|Gets or sets the IdentityProvider Claim Id.|
|TypeName|string¦null|false|none|Gets or sets the Type Name for this IdentityProvider Claim.|
|Value|string¦null|false|none|Gets or sets the value for this IdentityProvider Claim.|
|RoleIds|[string]¦null|false|none|Gets or sets a list of RoleIds that this claim on this IdentityProvider will map to.|

