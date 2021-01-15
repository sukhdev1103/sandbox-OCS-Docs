---
title: Identity_Storage_Controllers_Ops_IdentityProviders v20210115.07
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_controllers_ops_identityproviders-identityproviders">IdentityProviders</h1>

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderConsent"></a>

Returns an IdentityProviderConsent object.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}/Consent
```

<h3 id="identityproviders_getidentityproviderconsent-parameters">Parameters</h3>

`string(guid) identityProviderId`<br/>Id of provider.</br></br>
`[optional] string idpTenantDomain`<br/>Identity Provider Tenant Domain. Mutually exclusive to idpTenantId. Currently only supports AAD Domain.</br></br>`[optional] string idpTenantId`<br/>Identity Provider Tenant Id. Mutually exclusive to idpTenantDomain. Currently only supports AAD Tenant Id.</br></br>`[optional] any format`<br/>Output format.</br></br>

<h3 id="identityproviders_getidentityproviderconsent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|IdentityProviderConsent object.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity Provider or specified Aad Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "DisplayName": "string",
  "Scheme": "string",
  "UserIdClaimType": "string",
  "ClientId": "string",
  "IsConfigured": true,
  "Capabilities": {
    "User": {
      "SignIn": null,
      "Invitation": null,
      "Search": null
    },
    "Group": {
      "Authorize": null,
      "Search": null
    }
  }
}
```

# Schemas

<h2 id="tocS_IdentityProvider">IdentityProvider</h2>

<a id="schemaidentityprovider"></a>
<a id="schema_IdentityProvider"></a>
<a id="tocSidentityprovider"></a>
<a id="tocsidentityprovider"></a>

```json
{
  "Id": "string",
  "DisplayName": "string",
  "Scheme": "string",
  "UserIdClaimType": "string",
  "ClientId": "string",
  "IsConfigured": true,
  "Capabilities": {
    "User": {
      "SignIn": null,
      "Invitation": null,
      "Search": null
    },
    "Group": {
      "Authorize": null,
      "Search": null
    }
  }
}

```

The model for an Identity Provider in Identity Storage.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string(guid)|false|none|Gets or sets id of an identity provider.|
|DisplayName|string¦null|false|none|Gets or sets identity provider display name to use.|
|Scheme|string¦null|false|none|Gets or sets the name of the cookie handler that will temporarily store the outcome of the external authentication.|
|UserIdClaimType|string¦null|false|none|Gets or sets type of claim.|
|ClientId|string¦null|false|none|Gets or sets the ClientId of the identity provider.|
|IsConfigured|boolean|false|none|Gets or sets a value indicating whether the identity provider has been configured.|
|Capabilities|[IdentityProviderCapabilities](#schemaidentityprovidercapabilities)¦null|false|none|Gets or sets the Capabilities of the identity provider.|

<h2 id="tocS_IdentityProviderCapabilities">IdentityProviderCapabilities</h2>

<a id="schemaidentityprovidercapabilities"></a>
<a id="schema_IdentityProviderCapabilities"></a>
<a id="tocSidentityprovidercapabilities"></a>
<a id="tocsidentityprovidercapabilities"></a>

```json
{
  "User": {
    "SignIn": true,
    "Invitation": true,
    "Search": true
  },
  "Group": {
    "Authorize": true,
    "Search": true
  }
}

```

The model for the Capabilities of an Identity Provider in Identity Storage.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|User|[IdentityProviderUserCapabilites](#schemaidentityproviderusercapabilites)¦null|false|none|Gets or sets user level capabilities|
|Group|[IdentityProviderGroupCapabilites](#schemaidentityprovidergroupcapabilites)¦null|false|none|Gets or sets group level capabilities|

<h2 id="tocS_IdentityProviderUserCapabilites">IdentityProviderUserCapabilites</h2>

<a id="schemaidentityproviderusercapabilites"></a>
<a id="schema_IdentityProviderUserCapabilites"></a>
<a id="tocSidentityproviderusercapabilites"></a>
<a id="tocsidentityproviderusercapabilites"></a>

```json
{
  "SignIn": true,
  "Invitation": true,
  "Search": true
}

```

The model for the user level capabilities of an Identity Provider in Identity Storage.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|SignIn|boolean|false|none|Gets or sets a value indicating whether user sign-in is supported.|
|Invitation|boolean|false|none|Gets or sets a value indicating whether authorization via the invitation flow is supported.|
|Search|boolean|false|none|Gets or sets a value indicating whether user search is supported.|

<h2 id="tocS_IdentityProviderGroupCapabilites">IdentityProviderGroupCapabilites</h2>

<a id="schemaidentityprovidergroupcapabilites"></a>
<a id="schema_IdentityProviderGroupCapabilites"></a>
<a id="tocSidentityprovidergroupcapabilites"></a>
<a id="tocsidentityprovidergroupcapabilites"></a>

```json
{
  "Authorize": true,
  "Search": true
}

```

The model for the group level capabilities of an Identity Provider in Identity Storage.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Authorize|boolean|false|none|Gets or sets a value indicating whether authorization via groups is supported.|
|Search|boolean|false|none|Gets or sets a value indicating whether group search is supported.|

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

<h2 id="tocS_AadIdentityProviderConsentOutputFormat">AadIdentityProviderConsentOutputFormat</h2>

<a id="schemaaadidentityproviderconsentoutputformat"></a>
<a id="schema_AadIdentityProviderConsentOutputFormat"></a>
<a id="tocSaadidentityproviderconsentoutputformat"></a>
<a id="tocsaadidentityproviderconsentoutputformat"></a>

```json
0

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|

