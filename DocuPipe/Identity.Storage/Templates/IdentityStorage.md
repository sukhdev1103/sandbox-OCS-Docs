---
title: OSIsoft.Identity.Storage.Controllers v20210112.27
language_tabs: []
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="osisoft-identity-storage-controllers-claimtypenames">ClaimTypeNames</h1>

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
|200|List of [IdentityProviderClaimTypeName](#schemaidentityproviderclaimtypename)|Identity Provider Type Names found.|
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

<h1 id="osisoft-identity-storage-controllers-identityproviders">IdentityProviders</h1>

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProvider"></a>

Returns an IdentityProvider object.

### Request
```text 
GET /api/v1/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_getidentityprovider-parameters">Parameters</h3>

`string(guid) identityProviderId`<br/>Id of provider.</br></br>

<h3 id="identityproviders_getidentityprovider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity Provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity Provider not found.|
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
      "SignIn": true,
      "Invitation": true,
      "Search": true
    },
    "Group": {
      "Authorize": true,
      "Search": true
    }
  }
}
```

## HEAD IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderHeader"></a>

Get header for an identity provider to check if the identity provider exists.

### Request
```text 
HEAD /api/v1/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_getidentityproviderheader-parameters">Parameters</h3>

`string(guid) identityProviderId`<br/>Id of provider.</br></br>

<h3 id="identityproviders_getidentityproviderheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|IdentityProvider or Tenant not found.|
|500|None|Internal server error.|

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderByScheme"></a>

Returns a list of IdentityProvider objects that follow a scheme.

### Request
```text 
GET /api/v1/IdentityProviders/schemes/{scheme}
```

<h3 id="identityproviders_getidentityproviderbyscheme-parameters">Parameters</h3>

`string scheme`<br/>Scheme name.</br></br>

<h3 id="identityproviders_getidentityproviderbyscheme-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity Provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Identity Provider not found.|
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
      "SignIn": true,
      "Invitation": true,
      "Search": true
    },
    "Group": {
      "Authorize": true,
      "Search": true
    }
  }
}
```

## HEAD IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderSchemeHeader"></a>

Get header for a scheme to check its validity.

### Request
```text 
HEAD /api/v1/IdentityProviders/schemes/{scheme}
```

<h3 id="identityproviders_getidentityproviderschemeheader-parameters">Parameters</h3>

`string scheme`<br/>Scheme name.</br></br>

<h3 id="identityproviders_getidentityproviderschemeheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Identity Provider not found.|
|500|None|Internal server error.|

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviders"></a>

Returns a list of IdentityProvider objects.

### Request
```text 
GET /api/v1/IdentityProviders
```

<h3 id="identityproviders_getidentityproviders-parameters">Parameters</h3>

`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of providers to skip.</br></br>`[optional] integer(int32) count`<br/>Maximum number of providers to return.</br></br>

<h3 id="identityproviders_getidentityproviders-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [IdentityProvider](#schemaidentityprovider)|Identity Providers found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "DisplayName": "string",
    "Scheme": "string",
    "UserIdClaimType": "string",
    "ClientId": "string",
    "IsConfigured": true,
    "Capabilities": {
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
  }
]
```

## HEAD IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProvidersHeader"></a>

Get header for Identity Providers to get the total number of Identity Providers.

### Request
```text 
HEAD /api/v1/IdentityProviders
```

<h3 id="identityproviders_getidentityprovidersheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for Identity Providers found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

## GET IdentityProviders

<a id="opIdIdentityProviders_GetTenantIdentityProviders"></a>

Get all Identity Providers from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders
```

<h3 id="identityproviders_gettenantidentityproviders-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of Identity Providers to skip.</br></br>`[optional] integer(int32) count`<br/>Maximum number of Identity Providers to return.</br></br>

<h3 id="identityproviders_gettenantidentityproviders-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [IdentityProvider](#schemaidentityprovider)|Identity Providers found.|
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
    "DisplayName": "string",
    "Scheme": "string",
    "UserIdClaimType": "string",
    "ClientId": "string",
    "IsConfigured": true,
    "Capabilities": {
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
  }
]
```

## POST IdentityProviders

<a id="opIdIdentityProviders_AddTenantIdentityProvider"></a>

Add an existing Identity Provider to a Tenant. This Identity Provider
            will be available in the Home Realm Discovery Page
            for users to sign-in or sign-up.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders
```

### Request Body

IdentityProviderAdd object.<br/>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string",
  "IdentityProviderId": "string",
  "AzureActiveDirectorySendConsent": true
}
```

<h3 id="identityproviders_addtenantidentityprovider-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="identityproviders_addtenantidentityprovider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[IdentityProvider](#schemaidentityprovider)|Identity Provider created.|
|302|None|Found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity Provider already exists in Tenant.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

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
      "SignIn": true,
      "Invitation": true,
      "Search": true
    },
    "Group": {
      "Authorize": true,
      "Search": true
    }
  }
}
```

## HEAD IdentityProviders

<a id="opIdIdentityProviders_GetTenantIdentityProvidersHeader"></a>

Return total number of Identity Providers in a Tenant. The
            value will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return any objects
            in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders
```

<h3 id="identityproviders_gettenantidentityprovidersheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="identityproviders_gettenantidentityprovidersheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider headers for Tenant.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

## GET IdentityProviders

<a id="opIdIdentityProviders_GetTenantIdentityProvider"></a>

Get an Identity Provider from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_gettenantidentityprovider-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="identityproviders_gettenantidentityprovider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProvider](#schemaidentityprovider)|Identity Provider specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
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
      "SignIn": true,
      "Invitation": true,
      "Search": true
    },
    "Group": {
      "Authorize": true,
      "Search": true
    }
  }
}
```

## DELETE IdentityProviders

<a id="opIdIdentityProviders_RemoveTenantIdentityProvider"></a>

Remove an Identity Provider from a Tenant. Users provisioned
            with this Identity Provider will remain in the Tenant, but will
            not be able to authenticate.
            An administrator cannot remove the Identity Provider they are signed in with.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_removetenantidentityprovider-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="identityproviders_removetenantidentityprovider-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
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

## HEAD IdentityProviders

<a id="opIdIdentityProviders_GetTenantIdentityProviderHeader"></a>

Validate that a Identity Provider exists in the Tenant.
            This endpoint is identical to the GET one but
            it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}
```

<h3 id="identityproviders_gettenantidentityproviderheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="identityproviders_gettenantidentityproviderheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Identity Provider.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|IdentityProvider or Tenant not found.|
|500|None|Internal server error.|

## GET IdentityProviders

<a id="opIdIdentityProviders_GetTenantIdentityProviderConsent"></a>

Get an Identity Provider Consent from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

<h3 id="identityproviders_gettenantidentityproviderconsent-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="identityproviders_gettenantidentityproviderconsent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderConsent](#schemaidentityproviderconsent)|Identity Provider Consent.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
}
```

## POST IdentityProviders

<a id="opIdIdentityProviders_UpdateTenantIdentityProviderConsent"></a>

Update an Identity Provider consent related to Deeper Integration.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

### Request Body

Identity Provider Consent.<br/>

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
}
```

<h3 id="identityproviders_updatetenantidentityproviderconsent-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="identityproviders_updatetenantidentityproviderconsent-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderConsent](#schemaidentityproviderconsent)|Identity Provider Consent.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
}
```

## HEAD IdentityProviders

<a id="opIdIdentityProviders_GetTenantIdentityProviderConsentHeader"></a>

Get header for an Identity Provider to check if any additional consent data exists.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Consent
```

<h3 id="identityproviders_gettenantidentityproviderconsentheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="identityproviders_gettenantidentityproviderconsentheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Ok if the Identity Provider Consent exists.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
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

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderUsers"></a>

Get the users based on the query parameters.
            Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/users
```

<h3 id="identityproviders_getidentityproviderusers-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) identityProviderId`<br/>Identity Provider Id.</br></br>`string query`<br/>Start of user name or Email to search for.</br></br>
`[optional] integer(int32) count`<br/>Sets the page size of results.</br></br>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.</br></br>

<h3 id="identityproviders_getidentityproviderusers-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderUser](#schemaidentityproviderresultsofidentityprovideruser)|List of users found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}
```

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderGroups"></a>

Get the groups based on the query parameters.
            Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/groups
```

<h3 id="identityproviders_getidentityprovidergroups-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) identityProviderId`<br/>Identity Provider Id.</br></br>`string query`<br/>Start of user name or Email to search for.</br></br>
`[optional] integer(int32) count`<br/>Sets the page size of results.</br></br>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.</br></br>

<h3 id="identityproviders_getidentityprovidergroups-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}
```

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderGroupsForUser"></a>

Get the groups a user is a member of.
            Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Users/{userId}/Groups
```

<h3 id="identityproviders_getidentityprovidergroupsforuser-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) identityProviderId`<br/>Identity Provider Id.</br></br>`string userId`<br/>Id of the user.</br></br>
`[optional] integer(int32) skip`<br/>Indexes into a result set.</br></br>`[optional] integer(int32) count`<br/>Sets the page size of results.</br></br>`[optional] integer(int32) timeout`<br/>The maximum time to allow for searching groups before returning the groups.</br></br>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.</br></br>

<h3 id="identityproviders_getidentityprovidergroupsforuser-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups user is a member of.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}
```

## POST IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderGroupsByIds"></a>

Get the groups based on the Ids.
            Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Groups
```

### Request Body

Group Id list.<br/>

```json
[
  "string"
]
```

<h3 id="identityproviders_getidentityprovidergroupsbyids-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) identityProviderId`<br/>Identity Provider Id.</br></br>

<h3 id="identityproviders_getidentityprovidergroupsbyids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderResultsOfIdentityProviderGroup](#schemaidentityproviderresultsofidentityprovidergroup)|List of groups.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}
```

## GET IdentityProviders

<a id="opIdIdentityProviders_GetIdentityProviderMembersInAGroup"></a>

Get the members in a group.
            Currently, Azure Active Directory provider is the only provider that supports this endpoint.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/groups/{groupId}/members
```

<h3 id="identityproviders_getidentityprovidermembersinagroup-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) identityProviderId`<br/>Identity Provider Id.</br></br>`string groupId`<br/>External Id of the group.</br></br>
`[optional] integer(int32) count`<br/>Sets the page size of results.</br></br>`[optional] string skipToken`<br/>Retrieves the next page of results from result sets that span multiple pages.</br></br>

<h3 id="identityproviders_getidentityprovidermembersinagroup-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderMembers](#schemaidentityprovidermembers)|List of members.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Users": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "Groups": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}
```

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
      "SignIn": true,
      "Invitation": true,
      "Search": true
    },
    "Group": {
      "Authorize": true,
      "Search": true
    }
  }
}
```

<h1 id="osisoft-identity-storage-controllers-authorizationcodeclients">AuthorizationCodeClients</h1>

## POST AuthorizationCodeClients

<a id="opIdAuthorizationCodeClients_CreateAuthorizationCodeClient"></a>

Create an Authorization Code flow Client. No Secret will be generated for this
            Client.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AuthorizationCodeClients
```

### Request Body

New AuthorizationCodeClient object.<br/>

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

<h3 id="authorizationcodeclients_createauthorizationcodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="authorizationcodeclients_createauthorizationcodeclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[AuthorizationCodeClient](#schemaauthorizationcodeclient)|Authorization Code Client created.|
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

## GET AuthorizationCodeClients

<a id="opIdAuthorizationCodeClients_GetAuthorizationCodeClients"></a>

Get all Authorization Code clients from a Tenant.
            Optionally, get a list of requested clients. Total number
            of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AuthorizationCodeClients
```

<h3 id="authorizationcodeclients_getauthorizationcodeclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="authorizationcodeclients_getauthorizationcodeclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [AuthorizationCodeClient](#schemaauthorizationcodeclient)|Authorization Code Clients found.|
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

## HEAD AuthorizationCodeClients

<a id="opIdAuthorizationCodeClients_GetAuthorizationCodeClientsHeader"></a>

Return total number of Authorization Code clients in a Tenant.
            Optionally, check based on a list of requested clients. The
            value will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return any objects
            in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AuthorizationCodeClients
```

<h3 id="authorizationcodeclients_getauthorizationcodeclientsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only count Clients that have these tags.</br></br>

<h3 id="authorizationcodeclients_getauthorizationcodeclientsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Authorization Code Client headers.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## PUT AuthorizationCodeClients

<a id="opIdAuthorizationCodeClients_UpdateAuthorizationCodeClient"></a>

Update an Authorization Code Client. It can take up to one hour
            for update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

### Request Body

Updated Authorization Code Client values. Properties that are not set or are null will not be changed.<br/>

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

<h3 id="authorizationcodeclients_updateauthorizationcodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="authorizationcodeclients_updateauthorizationcodeclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AuthorizationCodeClient](#schemaauthorizationcodeclient)|Authorization Code Client updated.|
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

## GET AuthorizationCodeClients

<a id="opIdAuthorizationCodeClients_GetAuthorizationCodeClient"></a>

Get an Authorization Code Client from Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

<h3 id="authorizationcodeclients_getauthorizationcodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="authorizationcodeclients_getauthorizationcodeclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AuthorizationCodeClient](#schemaauthorizationcodeclient)|Authorization Code Client specified.|
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

## DELETE AuthorizationCodeClients

<a id="opIdAuthorizationCodeClients_DeleteAuthorizationCodeClient"></a>

Delete an Authorization Code Client. It can take up to one hour
            for deletion to manifest in the authentication process. Access
            tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

<h3 id="authorizationcodeclients_deleteauthorizationcodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="authorizationcodeclients_deleteauthorizationcodeclient-responses">Responses</h3>

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

## HEAD AuthorizationCodeClients

<a id="opIdAuthorizationCodeClients_GetAuthorizationCodeClientHeader"></a>

Validate that an Authorization Code Client exists in Tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AuthorizationCodeClients/{clientId}
```

<h3 id="authorizationcodeclients_getauthorizationcodeclientheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="authorizationcodeclients_getauthorizationcodeclientheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Header for specified Authorization Code Client.|
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
  "RoleIds": [
    "string"
  ]
}
```

<h1 id="osisoft-identity-storage-controllers-azureactivedirectorytenants">AzureActiveDirectoryTenants</h1>

## POST AzureActiveDirectoryTenants

<a id="opIdAzureActiveDirectoryTenants_AddAadTenantToTenant"></a>

Add an Azure Active Directory Tenant to the OSIsoft Cloud Services Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_addaadtenanttotenant-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of OSIsoft Cloud Services Tenant.</br></br>`string aadTenantId`<br/>Id or Domain Name of Azure Active Directory Tenant.</br></br>

<h3 id="azureactivedirectorytenants_addaadtenanttotenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|AzureActiveDirectoryTenant object created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Id of Azure Active Directory Tenant. is already in use on the specified Tenant.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

## GET AzureActiveDirectoryTenants

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantForTenant"></a>

Get Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_getaadtenantfortenant-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of OSIsoft Cloud Services Tenant.</br></br>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.</br></br>

<h3 id="azureactivedirectorytenants_getaadtenantfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|AzureActiveDirectory specified.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}
```

## DELETE AzureActiveDirectoryTenants

<a id="opIdAzureActiveDirectoryTenants_RemoveAadTenantFromTenant"></a>

Removal of Azure Active Directory Tenant from an OSIsoft Cloud Services Tenant is not supported.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_removeaadtenantfromtenant-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of OSIsoft Cloud Services Tenant.</br></br>`string aadTenantId`<br/>Id of Azure Active Directory Tenant to remove.</br></br>

<h3 id="azureactivedirectorytenants_removeaadtenantfromtenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|NotSupportedException.|

### Example response body

> 200 Response

## HEAD AzureActiveDirectoryTenants

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantHeaderForTenant"></a>

Validate that Azure Active Directory Tenant exists in this OSIsoft Cloud Services Tenant.
            This endpoint is identical to the GET one but
            it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}
```

<h3 id="azureactivedirectorytenants_getaadtenantheaderfortenant-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of OSIsoft Cloud Services Tenant.</br></br>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.</br></br>

<h3 id="azureactivedirectorytenants_getaadtenantheaderfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Azure Active Directory Tenant.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

## GET AzureActiveDirectoryTenants

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantsForTenant"></a>

Get all Azure Active Directory Tenants from an OSIsoft Cloud Services Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants
```

<h3 id="azureactivedirectorytenants_getaadtenantsfortenant-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of OSIsoft Cloud Services Tenant.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of Azure Active Directory tenants to skip.</br></br>`[optional] integer(int32) count`<br/>Maximum number of Azure Active Directory tenants to return.</br></br>

<h3 id="azureactivedirectorytenants_getaadtenantsfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [AzureActiveDirectoryTenant](#schemaazureactivedirectorytenant)|List of AzureActiveDirectoryTenants found.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|or|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "ConsentState": 0,
    "Domain": "string"
  }
]
```

## HEAD AzureActiveDirectoryTenants

<a id="opIdAzureActiveDirectoryTenants_GetAadTenantsHeaderForTenant"></a>

Return total number of Azure Active Directory tenants in a OSIsoft Cloud Services Tenant. This endpoint
            is identical to the GET one but it does not return any objects
            in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants
```

<h3 id="azureactivedirectorytenants_getaadtenantsheaderfortenant-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of OSIsoft Cloud Services Tenant.</br></br>

<h3 id="azureactivedirectorytenants_getaadtenantsheaderfortenant-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for AzureActiveDirectoryTenants found.|
|400|None|Missing or invalid inputs.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|OSIsoft Cloud Services Tenant not found.|
|500|None|Internal server error.|

## POST AzureActiveDirectoryTenants

<a id="opIdAzureActiveDirectoryTenants_SendAadTenantConsentRequest"></a>

Send consent for an Azure Active Directory Tenant. OSIsoft Cloud Services needs to be granted
            permission to interact with the Azure Active Directory tenant. Otherwise, users from this Azure Active Directory Tenant
            cannot accept invitations from OSIsoft Cloud Services and log in. You can read more about this
            [here](https://pisquare.osisoft.com/docs/DOC-3986-msa-consent-for-azure-active-directory).

### Request
```text 
POST /api/v1/Tenants/{tenantId}/AzureActiveDirectoryTenants/{aadTenantId}/SendConsent
```

### Request Body

ConsentInformation object.<br/>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string"
}
```

<h3 id="azureactivedirectorytenants_sendaadtenantconsentrequest-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of OSIsoft Cloud Services Tenant.</br></br>`string aadTenantId`<br/>Id of Azure Active Directory Tenant.</br></br>

<h3 id="azureactivedirectorytenants_sendaadtenantconsentrequest-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|OSIsoft Cloud Services Tenant not found.|
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

<h1 id="osisoft-identity-storage-controllers-clientcredentialclients">ClientCredentialClients</h1>

## POST ClientCredentialClients

<a id="opIdClientCredentialClients_CreateClientCredentialClient"></a>

Create a Client Credential Client. A Client Id and Client Secret will be generated to perform
            authentication. Make sure to store the Secret somewhere safe as we do not store the
            actual value after the creation step. If you do not have access to the Secret value, we suggest
            deleting the Secret and adding a new one for this Client. Clients have unique Ids in a Tenant.
            Currently there is a limit of 50000 clients (of all types) per Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/ClientCredentialClients
```

### Request Body

ClientCredentialClientCreate object.<br/>

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
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="clientcredentialclients_createclientcredentialclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="clientcredentialclients_createclientcredentialclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientCredentialClientCreateResponse](#schemaclientcredentialclientcreateresponse)|Client Credential Client details for Client Credential Client created.|
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
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
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
}
```

## GET ClientCredentialClients

<a id="opIdClientCredentialClients_GetClientCredentialClients"></a>

Get a list of Client Credential clients from a Tenant.
            Optionally, get a list of requested clients. Total number
            of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_getclientcredentialclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of Client Credential Client Ids. Empty, whitespace or null Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. Will be ignored if a list of Ids is passed.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return. Will be ignored if a list of Ids is passed.</br></br>

<h3 id="clientcredentialclients_getclientcredentialclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientCredentialClient](#schemaclientcredentialclient)|Client Credential Clients found.|
|207|[ClientCredentialClientMultiStatusResponse](#schemaclientcredentialclientmultistatusresponse)|Client Credential Clients found.|
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

## HEAD ClientCredentialClients

<a id="opIdClientCredentialClients_GetClientCredentialClientsHeader"></a>

Return total number of Client Credential clients in a Tenant.
            Optionally, check based on a list of requested clients. The
            value will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return any objects
            in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_getclientcredentialclientsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of Client Credential Client Ids. Empty, whitespace or null Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only count Clients that have these tags.</br></br>

<h3 id="clientcredentialclients_getclientcredentialclientsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Client Credential Client Headers found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## PUT ClientCredentialClients

<a id="opIdClientCredentialClients_UpdateClientCredentialClient"></a>

Update a Client Credential Client. It can take up to one hour
            for these values to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

### Request Body

ClientCredentialClient object. Properties that are not set or are null will not be changed.<br/>

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

<h3 id="clientcredentialclients_updateclientcredentialclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="clientcredentialclients_updateclientcredentialclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Client Credential Client updated.|
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
  "RoleIds": [
    "string"
  ]
}
```

## GET ClientCredentialClients

<a id="opIdClientCredentialClients_GetClientCredentialClient"></a>

Get a Client Credential Client.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_getclientcredentialclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="clientcredentialclients_getclientcredentialclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Client Credential Client specified.|
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
  "RoleIds": [
    "string"
  ]
}
```

## DELETE ClientCredentialClients

<a id="opIdClientCredentialClients_DeleteClientCredentialClient"></a>

Delete a Client Credential Client. It can take up to one hour
            for deletion to manifest in the authentication process. Access
            tokens issued to this Client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_deleteclientcredentialclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="clientcredentialclients_deleteclientcredentialclient-responses">Responses</h3>

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

## HEAD ClientCredentialClients

<a id="opIdClientCredentialClients_GetClientCredentialClientHeader"></a>

Validate that a Client Credential Client exists.
            This endpoint is identical to the GET one but
            it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_getclientcredentialclientheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="clientcredentialclients_getclientcredentialclientheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Client Credential Client.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## GET ClientCredentialClients

<a id="opIdClientCredentialClients_GetV1PreviewClientCredentialClients"></a>

Get all Client Credential Clients.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients
```

<h3 id="clientcredentialclients_getv1previewclientcredentialclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="clientcredentialclients_getv1previewclientcredentialclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientCredentialClient2](#schemaclientcredentialclient2)|List of ClientCredentialClients found.|
|207|[ClientCredentialClientMultiStatusResponse2](#schemaclientcredentialclientmultistatusresponse2)|List of ClientCredentialClients found.|
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
    "RoleIds": [
      "string"
    ]
  }
]
```

## POST ClientCredentialClients

<a id="opIdClientCredentialClients_CreateV1PreviewClientCredentialClient"></a>

Create a Client Credential flow Client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients
```

### Request Body

New ClientCredentialClientCreate object.<br/>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="clientcredentialclients_createv1previewclientcredentialclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="clientcredentialclients_createv1previewclientcredentialclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientCredentialClientResponse](#schemaclientcredentialclientresponse)|Hybrid Client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or Client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
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
  "RoleIds": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z",
  "ClientSecret": "string",
  "SecretId": "string"
}
```

## GET ClientCredentialClients

<a id="opIdClientCredentialClients_GetV1PreviewClientCredentialClient"></a>

Get a Client Credential Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

<h3 id="clientcredentialclients_getv1previewclientcredentialclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="clientcredentialclients_getv1previewclientcredentialclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient2](#schemaclientcredentialclient2)|ClientCredentialClient specified.|
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
  "RoleIds": [
    "string"
  ]
}
```

## PUT ClientCredentialClients

<a id="opIdClientCredentialClients_UpdateV1PreviewClientCredentialClient"></a>

Update a Client Credential Client.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/ClientCredentialClients/{clientId}
```

### Request Body

Updated Client Credential Client values.<br/>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="clientcredentialclients_updatev1previewclientcredentialclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="clientcredentialclients_updatev1previewclientcredentialclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient2](#schemaclientcredentialclient2)|Updated ClientCredentialClient.|
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
  "RoleIds": [
    "string"
  ]
}
```

<h1 id="osisoft-identity-storage-controllers-secrets">Secrets</h1>

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
|200|List of [ClientSecret](#schemaclientsecret)|Client Credential Secret information found.|
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
|200|List of [ClientSecret2](#schemaclientsecret2)|Client Credential Client Secrets found.|
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

## GET Secrets

<a id="opIdSecrets_GetHybridClientSecrets"></a>

Get all secrets for a Hybrid Client.
            Total number of secrets in the Client
            set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

<h3 id="secrets_gethybridclientsecrets-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="secrets_gethybridclientsecrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientSecret](#schemaclientsecret)|Hybrid Client Secret information found.|
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

<a id="opIdSecrets_AddHybridClientSecret"></a>

Add a new secret to a Client Credential Client.
            A client can have a maximum of 10 secrets.
            We advise against creating secrets that do not expire.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
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

<h3 id="secrets_addhybridclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="secrets_addhybridclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse](#schemaclientsecretresponse)|Hybrid Client Secret created.|
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

<a id="opIdSecrets_GetHybridClientSecretsHeader"></a>

Return total number of Secrets in a Hybrid Client. The value
            will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return
            any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

<h3 id="secrets_gethybridclientsecretsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="secrets_gethybridclientsecretsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Hybrid Client Secret headers.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## GET Secrets

<a id="opIdSecrets_GetHybridClientSecret"></a>

Get a Hybrid Client Secret.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_gethybridclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_gethybridclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Hybrid Client Secret specified.|
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

<a id="opIdSecrets_UpdateHybridClientSecret"></a>

Update a Hybrid Client Secret. It can take up to one hour for
            the update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
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

<h3 id="secrets_updatehybridclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_updatehybridclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret](#schemaclientsecret)|Hybrid Client Secret updated.|
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

<a id="opIdSecrets_DeleteHybridClientSecret"></a>

Delete a Secret from a Hybrid Client. It can take up to one hour for
            deletion to manifest in the authentication process.
            Access tokens issued using this Secret will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_deletehybridclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_deletehybridclientsecret-responses">Responses</h3>

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

<a id="opIdSecrets_GetHybridClientSecretHeader"></a>

Validate that a Secret with given Id exists in the Client.
            This endpoint is identical to the GET one but it does not
            return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_gethybridclientsecretheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>`integer(int32) secretId`<br/>Id of Secret.</br></br>

<h3 id="secrets_gethybridclientsecretheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Hybrid Client Secret.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Secret, Client, or Tenant not found.|
|500|None|Internal server error.|

## GET Secrets

<a id="opIdSecrets_GetV1PreviewHybridClientSecrets"></a>

Get all secrets for a Hybrid Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
```

<h3 id="secrets_getv1previewhybridclientsecrets-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="secrets_getv1previewhybridclientsecrets-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientSecret2](#schemaclientsecret2)|Hybrid Client Secrets found.|
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

<a id="opIdSecrets_AddV1PreviewHybridClientSecret"></a>

Add a new secret for a Hybrid Client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets
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

<h3 id="secrets_addv1previewhybridclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="secrets_addv1previewhybridclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[ClientSecretResponse2](#schemaclientsecretresponse2)|Hybrid Client Secret created.|
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

<a id="opIdSecrets_GetV1PreviewHybridClientSecret"></a>

Get a specific Hybrid Client Secret.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
```

<h3 id="secrets_getv1previewhybridclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>`integer(int32) secretId`<br/>Id of secret.</br></br>

<h3 id="secrets_getv1previewhybridclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Hybrid Client Secret specified.|
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

<a id="opIdSecrets_UpdateV1PreviewHybridClientSecret"></a>

Update a Hybrid Client Secret
            Only Secret Description and Secret Expiration Date can be updated.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}/Secrets/{secretId}
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

<h3 id="secrets_updatev1previewhybridclientsecret-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>`integer(int32) secretId`<br/>secretId.</br></br>

<h3 id="secrets_updatev1previewhybridclientsecret-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientSecret2](#schemaclientsecret2)|Updated Hybrid Client Secret.|
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

<h1 id="osisoft-identity-storage-controllers-devicecodeclients">DeviceCodeClients</h1>

## POST DeviceCodeClients

<a id="opIdDeviceCodeClients_CreateDeviceCodeClient"></a>

Create an Device Code flow Client. No Secret will be generated for this Client.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/DeviceCodeClients
```

### Request Body

New DeviceCodeClient object.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

<h3 id="devicecodeclients_createdevicecodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="devicecodeclients_createdevicecodeclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[DeviceCodeClient](#schemadevicecodeclient)|Device Code Client created.|
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
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

## GET DeviceCodeClients

<a id="opIdDeviceCodeClients_GetDeviceCodeClients"></a>

Get all Device Code clients from a Tenant.
            Optionally, get a list of requested clients. Total number
            of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/DeviceCodeClients
```

<h3 id="devicecodeclients_getdevicecodeclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="devicecodeclients_getdevicecodeclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [DeviceCodeClient](#schemadevicecodeclient)|Device Code Clients found.|
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
    "DeviceCodeLifetime": 0,
    "ClientUri": "string",
    "LogoUri": "string"
  }
]
```

## HEAD DeviceCodeClients

<a id="opIdDeviceCodeClients_GetDeviceCodeClientsHeader"></a>

Return total number of Device Code clients in a Tenant.
            Optionally, check based on a list of requested clients. The
            value will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return any objects
            in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/DeviceCodeClients
```

<h3 id="devicecodeclients_getdevicecodeclientsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of ids for all clients to get. Empty or whitespace Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only count Clients that have these tags.</br></br>

<h3 id="devicecodeclients_getdevicecodeclientsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Device Code Client headers.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## PUT DeviceCodeClients

<a id="opIdDeviceCodeClients_UpdateDeviceCodeClient"></a>

Update an Device Code Client. It can take up to one hour
            for update to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

### Request Body

Updated Device Code Client values. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

<h3 id="devicecodeclients_updatedevicecodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="devicecodeclients_updatedevicecodeclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DeviceCodeClient](#schemadevicecodeclient)|Device Code Client updated.|
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
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

## GET DeviceCodeClients

<a id="opIdDeviceCodeClients_GetDeviceCodeClient"></a>

Get an Device Code Client from Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

<h3 id="devicecodeclients_getdevicecodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="devicecodeclients_getdevicecodeclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[DeviceCodeClient](#schemadevicecodeclient)|Device Code Client specified.|
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
  "DeviceCodeLifetime": 0,
  "ClientUri": "string",
  "LogoUri": "string"
}
```

## DELETE DeviceCodeClients

<a id="opIdDeviceCodeClients_DeleteDeviceCodeClient"></a>

Delete a Device Code Client. It can take up to one hour
            for deletion to manifest in the authentication process. Access
            tokens issued to this client will be valid until their expiration.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

<h3 id="devicecodeclients_deletedevicecodeclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="devicecodeclients_deletedevicecodeclient-responses">Responses</h3>

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

## HEAD DeviceCodeClients

<a id="opIdDeviceCodeClients_GetDeviceCodeClientHeader"></a>

Validate that an Device Code Client exists in Tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/DeviceCodeClients/{clientId}
```

<h3 id="devicecodeclients_getdevicecodeclientheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="devicecodeclients_getdevicecodeclientheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[ClientCredentialClient](#schemaclientcredentialclient)|Header for specified Device Code Client.|
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
  "RoleIds": [
    "string"
  ]
}
```

<h1 id="osisoft-identity-storage-controllers-hybridclients">HybridClients</h1>

## POST HybridClients

<a id="opIdHybridClients_CreateHybridClient"></a>

Create a Hybrid Client. A Client Id and Client Secret will be generated to perform
            authentication. Make sure to store the Secret somewhere safe as we do not store the
            actual value after the creation step. If you do not have access to the Secret value, we suggest
            deleting the Secret and adding a new one for this Client. Clients have unique ids in a Tenant.
            Currently there is a limit of 50000 clients (of all types) per Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/HybridClients
```

### Request Body

HybridClientCreate object.<br/>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="hybridclients_createhybridclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="hybridclients_createhybridclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[HybridClientCreateResponse](#schemahybridclientcreateresponse)|Hybrid Client created.|
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
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
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
    "AllowOfflineAccess": true,
    "AllowAccessTokensViaBrowser": true
  }
}
```

## GET HybridClients

<a id="opIdHybridClients_GetHybridClients"></a>

Get a list of Hybrid clients from a Tenant.
            Optionally, get a list of requested clients. Total number
            of clients in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients
```

<h3 id="hybridclients_gethybridclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of Hybrid Client Ids. Empty, whitespace or null Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. Will be ignored if a list of Ids is passed.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return. Will be ignored if a list of Ids is passed.</br></br>

<h3 id="hybridclients_gethybridclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [HybridClient](#schemahybridclient)|Hybrid Clients found.|
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
    "AllowOfflineAccess": true,
    "AllowAccessTokensViaBrowser": true
  }
]
```

## HEAD HybridClients

<a id="opIdHybridClients_GetHybridClientsHeader"></a>

Return total number of Hybrid clients in a Tenant.
            Optionally, check based on a list of requested clients. The
            value will be set in the Total-Count header. This endpoint
            is identical to the GET one but it does not return any objects
            in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients
```

<h3 id="hybridclients_gethybridclientsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of Hybrid Client Ids. Empty, whitespace or null Ids will be ignored.</br></br>`[optional] array[string] tag`<br/>Only count clients that have these tags.</br></br>

<h3 id="hybridclients_gethybridclientsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Hybrid Client Secrets found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## PUT HybridClients

<a id="opIdHybridClients_UpdateHybridClient"></a>

Update a Hybrid Client. It can take up to one hour
            for these values to manifest in the authentication process.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

### Request Body

HybridClient object. Properties that are not set or are null will not be changed.<br/>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

<h3 id="hybridclients_updatehybridclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="hybridclients_updatehybridclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient](#schemahybridclient)|Hybrid Client updated.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

## GET HybridClients

<a id="opIdHybridClients_GetHybridClient"></a>

Get a Hybrid Client from a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_gethybridclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="hybridclients_gethybridclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient](#schemahybridclient)|Hybrid Client specified.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

## DELETE HybridClients

<a id="opIdHybridClients_DeleteHybridClient"></a>

Delete a Hybrid Client. It can take up to one hour
            for deletion to manifest in the authentication process. Access
            tokens issued to this Client will be valid until their expiration.
            Refresh tokens issued to this will be valid up to one hour after deletion.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_deletehybridclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="hybridclients_deletehybridclient-responses">Responses</h3>

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

## HEAD HybridClients

<a id="opIdHybridClients_GetHybridClientHeader"></a>

Validate that a Hybrid Client exists.
            This endpoint is identical to the GET one but
            it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_gethybridclientheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of Client.</br></br>

<h3 id="hybridclients_gethybridclientheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified Hybrid Client.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Client or Tenant not found.|
|500|None|Internal server error.|

## POST HybridClients

<a id="opIdHybridClients_CreateV1PreviewHybridClient"></a>

Create a Hybrid flow Client.

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/HybridClients
```

### Request Body

New HybridClientCreate object.<br/>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}
```

<h3 id="hybridclients_createv1previewhybridclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="hybridclients_createv1previewhybridclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[HybridClientResponse](#schemahybridclientresponse)|Hybrid Client created.|
|400|[ErrorResponse](#schemaerrorresponse)|Client Limit exceeded.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z",
  "ClientSecret": "string",
  "SecretId": "string"
}
```

## GET HybridClients

<a id="opIdHybridClients_GetV1PreviewHybridClients"></a>

Get all Hybrid Clients.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients
```

<h3 id="hybridclients_getv1previewhybridclients-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] tag`<br/>Only return Clients that have these tags.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of clients to skip. From query.</br></br>`[optional] integer(int32) count`<br/>Maximum number of clients to return.</br></br>

<h3 id="hybridclients_getv1previewhybridclients-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [HybridClient2](#schemahybridclient2)|List of Hybrid Clients found.|
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
    "AllowOfflineAccess": true,
    "AllowAccessTokensViaBrowser": true
  }
]
```

## PUT HybridClients

<a id="opIdHybridClients_UpdateV1PreviewHybridClient"></a>

Update a Hybrid Client.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}
```

### Request Body

Updated Hybrid Client values.<br/>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

<h3 id="hybridclients_updatev1previewhybridclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="hybridclients_updatev1previewhybridclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient2](#schemahybridclient2)|Updated Hybrid Client.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

## GET HybridClients

<a id="opIdHybridClients_GetV1PreviewHybridClient"></a>

Get a Hybrid Client.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/HybridClients/{clientId}
```

<h3 id="hybridclients_getv1previewhybridclient-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string clientId`<br/>Id of client.</br></br>

<h3 id="hybridclients_getv1previewhybridclient-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[HybridClient2](#schemahybridclient2)|Hybrid Client specified.|
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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
}
```

<h1 id="osisoft-identity-storage-controllers-claims">Claims</h1>

## GET Claims

<a id="opIdClaims_GetIdentityProviderClaims"></a>

Get all Identity Provider Claims for an Identity Provider on a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

<h3 id="claims_getidentityproviderclaims-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of Identity Providers to skip.</br></br>`[optional] integer(int32) count`<br/>Maximum number of Identity Providers to return.</br></br>

<h3 id="claims_getidentityproviderclaims-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [IdentityProviderClaim](#schemaidentityproviderclaim)|List of Identity Provider Claims found.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or Identity Provider not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "TypeName": "string",
    "Value": "string",
    "RoleIds": [
      "string"
    ]
  }
]
```

## HEAD Claims

<a id="opIdClaims_GetIdentityProviderClaimsHeader"></a>

Get Header for all Identity Provider Claims for an Identity Provider on a Tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

<h3 id="claims_getidentityproviderclaimsheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="claims_getidentityproviderclaimsheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider Claim Header information.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Identity Provider not found.|
|500|None|Internal server error.|

## POST Claims

<a id="opIdClaims_PostIdentityProviderClaim"></a>

Create a new Identity Provider Claim for an Identity Provider on a Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims
```

### Request Body

Identity Provider Claim to create.<br/>

```json
{
  "Value": "string",
  "IdentityProviderClaimTypeNameId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="claims_postidentityproviderclaim-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>

<h3 id="claims_postidentityproviderclaim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity Provider Claim created.|
|302|None|Found.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, or Roles not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity Provider Claim configuration already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

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

## GET Claims

<a id="opIdClaims_GetIdentityProviderClaim"></a>

Get an Identity Provider Claim from an Identity Provider on a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_getidentityproviderclaim-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>`string(guid) identityProviderClaimId`<br/>Id of Identity Provider Claim.</br></br>

<h3 id="claims_getidentityproviderclaim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Identity Provider Claim specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, or Identity Provider Claim not found.|
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

## HEAD Claims

<a id="opIdClaims_GetIdentityProviderClaimHeader"></a>

Get an Identity Provider Claim Header from an Identity Provider on a Tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_getidentityproviderclaimheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>`string(guid) identityProviderClaimId`<br/>Id of Identity Provider Claim.</br></br>

<h3 id="claims_getidentityproviderclaimheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Identity Provider Claim specified header.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant, Identity Provider, or Identity Provider Claim not found.|
|500|None|Internal server error.|

## PUT Claims

<a id="opIdClaims_PutIdentityProviderClaim"></a>

Create a new Identity Provider Claim for an Identity Provider on a Tenant.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

### Request Body

Updated Identity Provider Claim values.<br/>

```json
{
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="claims_putidentityproviderclaim-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>`string(guid) identityProviderClaimId`<br/>Id of Identity Provider Claim.</br></br>

<h3 id="claims_putidentityproviderclaim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[IdentityProviderClaim](#schemaidentityproviderclaim)|Updated Identity Provider Claim.|
|400|[ErrorResponse](#schemaerrorresponse)|Bad Request.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, Identity Provider Claim, or Roles not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Identity Provider Claim configuration already exists.|
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

## DELETE Claims

<a id="opIdClaims_DeleteIdentityProviderClaim"></a>

Delete an Identity Provider Claim for an Identity Provider on a Tenant.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/IdentityProviders/{identityProviderId}/Claims/{identityProviderClaimId}
```

<h3 id="claims_deleteidentityproviderclaim-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Id of Identity Provider.</br></br>`string(guid) identityProviderClaimId`<br/>Id of Identity Provider Claim.</br></br>

<h3 id="claims_deleteidentityproviderclaim-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant, Identity Provider, or Identity Provider Claim not found.|
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

<h1 id="osisoft-identity-storage-controllers-implicitclients">ImplicitClients</h1>

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
|200|List of [ImplicitClient](#schemaimplicitclient)|Implicit Clients found.|
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
|200|List of [ImplicitClient2](#schemaimplicitclient2)|Implicit Clients found.|
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

<h1 id="osisoft-identity-storage-controllers-roles">Roles</h1>

## GET Roles

<a id="opIdRoles_GetTenantRoles"></a>

Get all Roles for a Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles
```

<h3 id="roles_gettenantroles-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of tenant.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of providers to skip.</br></br>`[optional] integer(int32) count`<br/>Max number of providers to return.</br></br>

<h3 id="roles_gettenantroles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [Role](#schemarole)|List of Roles found.|
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
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

## HEAD Roles

<a id="opIdRoles_GetTenantRolesHeader"></a>

Get header for Roles to get the total number of Roles for a given tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles
```

<h3 id="roles_gettenantrolesheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>

<h3 id="roles_gettenantrolesheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for Roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant not found.|
|500|None|Internal server error.|

## POST Roles

<a id="opIdRoles_PostTenantRole"></a>

Create a new `Role` for a Tenant.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/Roles
```

### Request Body

Role to create.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

<h3 id="roles_posttenantrole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant ID.</br></br>

<h3 id="roles_posttenantrole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[Role](#schemarole)|Role created.|
|302|None|A role with the same Id or Name already exists in the Tenant.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or Role not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|A role with some matching values already exists in Tenant.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

## HEAD Roles

<a id="opIdRoles_GetUsersCountForARole"></a>

Gets the total number of users for a given role.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}/users
```

<h3 id="roles_getuserscountforarole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id for the Role.</br></br>`string(guid) roleId`<br/>Role Id.</br></br>

<h3 id="roles_getuserscountforarole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for Roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

## GET Roles

<a id="opIdRoles_GetUsersForARole"></a>

Get all the Users for a given role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}/users
```

<h3 id="roles_getusersforarole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) roleId`<br/>Role Id.</br></br>

<h3 id="roles_getusersforarole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [User](#schemauser)|Users for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "GivenName": "string",
    "Surname": "string",
    "Name": "string",
    "Email": "string",
    "ContactEmail": "string",
    "ContactGivenName": "string",
    "ContactSurname": "string",
    "ExternalUserId": "string",
    "IdentityProviderId": "string",
    "RoleIds": [
      "string"
    ]
  }
]
```

## HEAD Roles

<a id="opIdRoles_GetClientCredentialClientsCountForARole"></a>

Get the total number of clients for a given role.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}/clientcredentialclients
```

<h3 id="roles_getclientcredentialclientscountforarole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) roleId`<br/>Role Id.</br></br>

<h3 id="roles_getclientcredentialclientscountforarole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for the total number of clients for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

## GET Roles

<a id="opIdRoles_GetClientCredentialClientsForARole"></a>

Get all the clients for a given role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}/clientcredentialclients
```

<h3 id="roles_getclientcredentialclientsforarole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) roleId`<br/>Role Id.</br></br>

<h3 id="roles_getclientcredentialclientsforarole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [ClientCredentialClient](#schemaclientcredentialclient)|Clients for a given role.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or Role not found.|
|500|None|Internal server error.|

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

## GET Roles

<a id="opIdRoles_GetTenantRole"></a>

Returns the specified Role.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_gettenantrole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant Id.</br></br>`string(guid) roleId`<br/>Role Id.</br></br>

<h3 id="roles_gettenantrole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Role specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Role or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

## HEAD Roles

<a id="opIdRoles_GetTenantRoleHeader"></a>

Get header for a Role on given tenant.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_gettenantroleheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of tenant.</br></br>`string(guid) roleId`<br/>Id of provider.</br></br>

<h3 id="roles_gettenantroleheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Role specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|IdentityProvider or Tenant not found.|
|500|None|Internal server error.|

## PUT Roles

<a id="opIdRoles_PutTenantRole"></a>

Update a `Role` for a Tenant.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

### Request Body

Role to update.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

<h3 id="roles_puttenantrole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant ID.</br></br>`string(guid) roleId`<br/>Role ID.</br></br>

<h3 id="roles_puttenantrole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Updated Role.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or Role not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

## DELETE Roles

<a id="opIdRoles_DeleteTenantRole"></a>

Delete a Role from a Tenant.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Roles/{roleId}
```

<h3 id="roles_deletetenantrole-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant ID.</br></br>`string(guid) roleId`<br/>Role ID.</br></br>

<h3 id="roles_deletetenantrole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|IdentityProvider or Tenant not found.|
|405|[ErrorResponse](#schemaerrorresponse)|Delete built-in Roles not allowed.|
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

## GET Roles

<a id="opIdRoles_GetUserRoles"></a>

Returns a list of Roles for a given User.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

<h3 id="roles_getuserroles-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant ID.</br></br>`string(guid) userId`<br/>User ID.</br></br>
`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of Roles to skip.</br></br>`[optional] integer(int32) count`<br/>Max number of Roles to return.</br></br>

<h3 id="roles_getuserroles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [Role](#schemarole)|List of Roles found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant or User not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

## HEAD Roles

<a id="opIdRoles_GetUserRolesHeader"></a>

Head request to get the total number of User Roles for the specified User.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

<h3 id="roles_getuserrolesheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant ID.</br></br>`string(guid) userId`<br/>User ID.</br></br>

<h3 id="roles_getuserrolesheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Headers for Roles found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Tenant or User not found.|
|500|None|Internal server error.|

## PUT Roles

<a id="opIdRoles_PutUserRoles"></a>

Replace existing User Roles. If Member Role is not provided it will be added.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}/Roles
```

### Request Body

Update Roles list.<br/>

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

<h3 id="roles_putuserroles-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Tenant ID.</br></br>`string(guid) userId`<br/>User ID.</br></br>

<h3 id="roles_putuserroles-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [Role](#schemarole)|No content.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
[
  {
    "Id": "string",
    "Name": "string",
    "Description": "string",
    "RoleScope": 1,
    "TenantId": "string",
    "CommunityId": "string",
    "RoleTypeId": "string"
  }
]
```

## GET Roles

<a id="opIdRoles_GetRole"></a>

Returns the specified Role.

### Request
```text 
GET /api/v1/Roles/{roleId}
```

<h3 id="roles_getrole-parameters">Parameters</h3>

`string(guid) roleId`<br/>Role Id.</br></br>

<h3 id="roles_getrole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Role specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Role not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

## HEAD Roles

<a id="opIdRoles_GetRoleHeader"></a>

Get header for a Role.

### Request
```text 
HEAD /api/v1/Roles/{roleId}
```

<h3 id="roles_getroleheader-parameters">Parameters</h3>

`string(guid) roleId`<br/>Id of provider.</br></br>

<h3 id="roles_getroleheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for Role specified.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|Role not found.|
|500|None|Internal server error.|

## PUT Roles

<a id="opIdRoles_PutRole"></a>

Update an existing `Role` .

### Request
```text 
PUT /api/v1/Roles/{roleId}
```

### Request Body

Role to update.<br/>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

<h3 id="roles_putrole-parameters">Parameters</h3>

`string(guid) roleId`<br/>Role ID.</br></br>

<h3 id="roles_putrole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[Role](#schemarole)|Role created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Role not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|409|[ErrorResponse](#schemaerrorresponse)|Role already exists.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}
```

## DELETE Roles

<a id="opIdRoles_DeleteRole"></a>

Delete a Role.

### Request
```text 
DELETE /api/v1/Roles/{roleId}
```

<h3 id="roles_deleterole-parameters">Parameters</h3>

`string(guid) roleId`<br/>Role ID.</br></br>

<h3 id="roles_deleterole-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Role not found.|
|405|[ErrorResponse](#schemaerrorresponse)|Delete built-in Roles not allowed.|
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

<h1 id="osisoft-identity-storage-controllers-users">Users</h1>

## GET Users

<a id="opIdUsers_GetUsers"></a>

Get a list of users from a Tenant. Optionally, get a list of requested users.
            Total number of users in the Tenant set in the Total-Count header.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users
```

<h3 id="users_getusers-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of User Ids to get.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of users to skip. Ignored if a list of Ids is passed.</br></br>`[optional] integer(int32) count`<br/>Maximum number of users to return. Ignored if a list of Ids is passed.</br></br>

<h3 id="users_getusers-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [User](#schemauser)|List of Users found.|
|207|[UserMultiStatusResponse](#schemausermultistatusresponse)|List of Users found.|
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
    "Id": "00000000-0000-0000-0000-000000000000",
    "GivenName": "Name",
    "Surname": "Surname",
    "Name": "Name",
    "Email": "user@company.com",
    "ContactEmail": "user@company.com",
    "ContactGivenName": "Name",
    "ContactSurname": "Surname",
    "ExternalUserId": "ExternalUserId",
    "IdentityProviderId": "00000000-0000-0000-0000-000000000000",
    "RoleIds": [
      "00000000-0000-0000-0000-000000000000",
      "00000000-0000-0000-0000-000000000000"
    ]
  },
  {
    "Id": "00000000-0000-0000-0000-000000000000",
    "GivenName": "Name",
    "Surname": "Surname",
    "Name": "Name",
    "Email": "user@company.com",
    "ContactEmail": "user@company.com",
    "ContactGivenName": "Name",
    "ContactSurname": "Surname",
    "ExternalUserId": "ExternalUserId",
    "IdentityProviderId": "00000000-0000-0000-0000-000000000000",
    "RoleIds": [
      "00000000-0000-0000-0000-000000000000",
      "00000000-0000-0000-0000-000000000000"
    ]
  }
]
```

> 207 Response

```json
{
  "OperationId": "OperationId",
  "Error": "Error",
  "Reason": "Reason",
  "ChildErrors": [
    {
      "StatusCode": 0,
      "ModelId": "ModelId",
      "OperationId": "OperationId",
      "Error": "Error",
      "Reason": "Reason",
      "Resolution": "Resolution"
    },
    {
      "StatusCode": 0,
      "ModelId": "ModelId",
      "OperationId": "OperationId",
      "Error": "Error",
      "Reason": "Reason",
      "Resolution": "Resolution"
    }
  ],
  "Data": [
    {
      "Id": "00000000-0000-0000-0000-000000000000",
      "GivenName": "Name",
      "Surname": "Surname",
      "Name": "Name",
      "Email": "user@company.com",
      "ContactEmail": "user@company.com",
      "ContactGivenName": "Name",
      "ContactSurname": "Surname",
      "ExternalUserId": "ExternalUserId",
      "IdentityProviderId": "00000000-0000-0000-0000-000000000000",
      "RoleIds": [
        "00000000-0000-0000-0000-000000000000",
        "00000000-0000-0000-0000-000000000000"
      ]
    },
    {
      "Id": "00000000-0000-0000-0000-000000000000",
      "GivenName": "Name",
      "Surname": "Surname",
      "Name": "Name",
      "Email": "user@company.com",
      "ContactEmail": "user@company.com",
      "ContactGivenName": "Name",
      "ContactSurname": "Surname",
      "ExternalUserId": "ExternalUserId",
      "IdentityProviderId": "00000000-0000-0000-0000-000000000000",
      "RoleIds": [
        "00000000-0000-0000-0000-000000000000",
        "00000000-0000-0000-0000-000000000000"
      ]
    }
  ]
}
```

> 400 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

> 401 Response

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

## POST Users

<a id="opIdUsers_CreateUser"></a>

Create a User in the Tenant. This endpoint does not create an invitation for the User.
            You will need to create an invitation in the respective endpoint for this User, otherwise
            they will not be able to finish the sign-up process. Users have unique Ids in a Tenant.
            Currently there is a limit of 50000 users per Tenant.
            For Windows Active Directory users, the externalUserId must be specified.

### Request
```text 
POST /api/v1/Tenants/{tenantId}/Users
```

### Request Body

UserCreateOrUpdate object.<br/>

```json
{
  "Id": "string",
  "ExternalUserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "IdentityProviderId": "string",
  "IdentityProviderSpecificUserId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_createuser-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="users_createuser-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[User](#schemauser)|User created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or the User limit exceeded for Tenant.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

## HEAD Users

<a id="opIdUsers_GetUsersHeader"></a>

Return total number of users in a Tenant. Optionally, check based on a list of requested users.
            The value will be set in the Total-Count header. This endpoint is identical to the GET one but
            it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users
```

<h3 id="users_getusersheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of User Ids.</br></br>

<h3 id="users_getusersheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|User Header found.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User not found.|
|500|None|Internal server error.|

## GET Users

<a id="opIdUsers_GetUsersStatus"></a>

[object Object]

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/Status
```

<h3 id="users_getusersstatus-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] id`<br/>Unordered list of User Ids to get.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Number of users to skip. Ignored if a list of Ids is passed.</br></br>`[optional] integer(int32) count`<br/>Maximum number of users to return. Ignored if a list of Ids is passed.</br></br>`[optional] array[string] status`<br/>Only return statuses that match these values. Possible User statuses are: InvitationAccepted, NoInvitation, InvitationNotSent, InvitationSent, InvitationExpired.</br></br>

<h3 id="users_getusersstatus-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [UserStatus](#schemauserstatus)|List of User Statuses found.|
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
    "InvitationStatus": 0,
    "User": {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "string",
      "ContactEmail": "string",
      "ContactGivenName": "string",
      "ContactSurname": "string",
      "ExternalUserId": "string",
      "IdentityProviderId": "string",
      "RoleIds": [
        "string"
      ]
    }
  }
]
```

> 400 Response

```json
{
  "OperationId": "docupipe-test",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error."
}
```

## GET Users

<a id="opIdUsers_GetUserModel"></a>

Get a User from Tenant.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_getusermodel-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>

<h3 id="users_getusermodel-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|User specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

## PUT Users

<a id="opIdUsers_UpdateUser"></a>

Update a User in a Tenant. The Id of a User cannot be changed.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}
```

### Request Body

UserCreateOrUpdate object. Properties that are not set or are null will not be changed.<br/>

```json
{
  "Id": "string",
  "ExternalUserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "IdentityProviderId": "string",
  "IdentityProviderSpecificUserId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_updateuser-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>

<h3 id="users_updateuser-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|Updated User.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

## DELETE Users

<a id="opIdUsers_DeleteUser"></a>

Delete a User. Users cannot delete themselves. Deleting a User does not invalidate any of the
            existing access tokens, but it prevents this User from being able to authenticate in the future.
            Existing access tokens for the User will be valid until their expiration date. Refresh tokens on
            behalf of the User will no longer be valid after the User has been deleted. Deleting a user with 
            explicit and claim role mappings will only have their explicit roles deleted. Forcibly deleting a user
            will delete a user completely regardless of claim role mappings.

### Request
```text 
DELETE /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_deleteuser-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>
`[optional] boolean force`<br/>Forcibly delete a User that can remain due to claim role mappings.</br></br>

<h3 id="users_deleteuser-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|string|No content.|
|204|None|No content.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
"string"
```

## HEAD Users

<a id="opIdUsers_GetUserHeader"></a>

Validate that a User exists. This endpoint is identical to the GET
            one, but it does not return an object in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}
```

<h3 id="users_getuserheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>

<h3 id="users_getuserheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for User.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User does not exist.|
|500|None|Internal server error.|

## GET Users

<a id="opIdUsers_GetUserStatus"></a>

Get invitation status for a User. It can be: InvitationAccepted (0),
            NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Status
```

<h3 id="users_getuserstatus-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>

<h3 id="users_getuserstatus-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserStatus](#schemauserstatus)|User Status for User specified.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "InvitationStatus": 0,
  "User": {
    "Id": "string",
    "GivenName": "string",
    "Surname": "string",
    "Name": "string",
    "Email": "string",
    "ContactEmail": "string",
    "ContactGivenName": "string",
    "ContactSurname": "string",
    "ExternalUserId": "string",
    "IdentityProviderId": "string",
    "RoleIds": [
      "string"
    ]
  }
}
```

## GET Users

<a id="opIdUsers_GetUserPreferences"></a>

Get preferences from a User. User preferences can be any valid
            JSON object. A common use case is to store UI preferences for the User.

### Request
```text 
GET /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_getuserpreferences-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>

<h3 id="users_getuserpreferences-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|User Preferences for specified User.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|422|[ErrorResponse](#schemaerrorresponse)|Unprocessable entity.|

### Example response body

> 200 Response

```json
null
```

## PUT Users

<a id="opIdUsers_UpdateUserPreferences"></a>

Update preferences for a User.

### Request
```text 
PUT /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

### Request Body

JSON object preferences.<br/>

```json
null
```

<h3 id="users_updateuserpreferences-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>

<h3 id="users_updateuserpreferences-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|Inline|Updated User Preferences.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing preferences.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|

### Example response body

> 200 Response

```json
null
```

## HEAD Users

<a id="opIdUsers_GetUserPreferencesHeader"></a>

Validate that there are preferences for a User. This endpoint is identical
            to the GET one but it does not return any objects in the body.

### Request
```text 
HEAD /api/v1/Tenants/{tenantId}/Users/{userId}/Preferences
```

<h3 id="users_getuserpreferencesheader-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of User.</br></br>

<h3 id="users_getuserpreferencesheader-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|None|Header for specified User's Preferences.|
|401|None|Unauthorized.|
|403|None|Forbidden.|
|404|None|User or Tenant not found.|
|500|None|Internal server error.|

## GET Users

<a id="opIdUsers_GetV1PreviewUsersByIds"></a>

Returns an ordered list of User objects based on userId for a given tenant or a MultiStatusResponse with a list of User objects and a list of errors.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Users/Ids
```

<h3 id="users_getv1previewusersbyids-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] userId`<br/>Unordered list of ids for all users to get.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Items to skip. Currently not supported.</br></br>`[optional] integer(int32) count`<br/>Maximum items to return. Currently not supported.</br></br>

<h3 id="users_getv1previewusersbyids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [User](#schemauser)|List of Users found.|
|207|[UserMultiStatusResponse](#schemausermultistatusresponse)|List of Users found.|
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
    "GivenName": "string",
    "Surname": "string",
    "Name": "string",
    "Email": "string",
    "ContactEmail": "string",
    "ContactGivenName": "string",
    "ContactSurname": "string",
    "ExternalUserId": "string",
    "IdentityProviderId": "string",
    "RoleIds": [
      "string"
    ]
  }
]
```

## GET Users

<a id="opIdUsers_GetV1PreviewUsersStatusByIds"></a>

Returns an ordered list of UserStatus objects for a given tenant or a MultiStatusResponse with a list of UserStatus objects and a list of errors.

### Request
```text 
GET /api/v1-preview/Tenants/{tenantId}/Users/Status/Ids
```

<h3 id="users_getv1previewusersstatusbyids-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>
`[optional] array[string] userId`<br/>Unordered list of ids for all users.</br></br>`[optional] string query`<br/>Query to execute. Currently not supported.</br></br>`[optional] integer(int32) skip`<br/>Items to skip. Currently not supported.</br></br>`[optional] integer(int32) count`<br/>Maximum number of items to retrieve. Currently not supported.</br></br>

<h3 id="users_getv1previewusersstatusbyids-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|List of [UserStatus](#schemauserstatus)|List of User Statuses found.|
|207|[UserStatusMultiStatusResponse](#schemauserstatusmultistatusresponse)|List of User Statuses found.|
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
    "InvitationStatus": 0,
    "User": {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "string",
      "ContactEmail": "string",
      "ContactGivenName": "string",
      "ContactSurname": "string",
      "ExternalUserId": "string",
      "IdentityProviderId": "string",
      "RoleIds": [
        "string"
      ]
    }
  }
]
```

## POST Users

<a id="opIdUsers_CreateV1PreviewUser"></a>

Creates a `User` .

### Request
```text 
POST /api/v1-preview/Tenants/{tenantId}/Users
```

### Request Body

User values to use during creating.<br/>

```json
{
  "UserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_createv1previewuser-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>

<h3 id="users_createv1previewuser-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|201|[User](#schemauser)|User created.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or User limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 201 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

## PUT Users

<a id="opIdUsers_UpdateV1PreviewUser"></a>

Create or Update a User.

### Request
```text 
PUT /api/v1-preview/Tenants/{tenantId}/Users/{userId}
```

### Request Body

A UserStatus object.<br/>

```json
{
  "UserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "RoleIds": [
    "string"
  ]
}
```

<h3 id="users_updatev1previewuser-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>Id of user.</br></br>

<h3 id="users_updatev1previewuser-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[User](#schemauser)|Updated User.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|User or Tenant not found.|
|408|[ErrorResponse](#schemaerrorresponse)|Operation timed out.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}
```

<h1 id="osisoft-identity-storage-controllers-userinformation">UserInformation</h1>

## GET UserInformation

<a id="opIdUserInformation_GetUserInformationForAuthentication"></a>

Get UserInformation for Authentication.

### Request
```text 
GET /api/v1/tenants/{tenantId}/identityproviders/{identityProviderId}/users/{identityProviderSpecificUserId}/UserInformation
```

<h3 id="userinformation_getuserinformationforauthentication-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) identityProviderId`<br/>Identity Provider Id.</br></br>`string identityProviderSpecificUserId`<br/>Identity Provider Specific User Id. Ex. ExternalUserId for AD, ObjectId for AAD.</br></br>`string claimTypes`<br/>Claim Types.</br></br>

<h3 id="userinformation_getuserinformationforauthentication-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserInformationResponse](#schemauserinformationresponse)|UserInformation or UserInformationMultiStatusResponse.|
|207|[UserInformationMultiStatusResponse](#schemauserinformationmultistatusresponse)|UserInformation or UserInformationMultiStatusResponse.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or Client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|

### Example response body

> 200 Response

```json
{
  "UserInformation": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}
```

## GET UserInformation

<a id="opIdUserInformation_GetUserInformationForTokenRefresh"></a>

Get UserInformation for Access Token Refresh.

### Request
```text 
GET /api/v1/tenants/{tenantId}/users/{userId}/UserInformation
```

<h3 id="userinformation_getuserinformationfortokenrefresh-parameters">Parameters</h3>

`string(guid) tenantId`<br/>Id of Tenant.</br></br>`string(guid) userId`<br/>User Id.</br></br>`string claimTypes`<br/>Claim Types.</br></br>

<h3 id="userinformation_getuserinformationfortokenrefresh-responses">Responses</h3>

|Status Code|Body Type|Description|
|---|---|---|
|200|[UserInformationResponse](#schemauserinformationresponse)|UserInformation or UserInformationMultiStatusResponse.|
|207|[UserInformationMultiStatusResponse](#schemauserinformationmultistatusresponse)|UserInformation or UserInformationMultiStatusResponse.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs, or Client limit exceeded.|
|401|[ErrorResponse](#schemaerrorresponse)|Unauthorized.|
|403|[ErrorResponse](#schemaerrorresponse)|Forbidden.|
|404|[ErrorResponse](#schemaerrorresponse)|Tenant not found.|
|500|[ErrorResponse](#schemaerrorresponse)|Internal server error.|
|503|[ErrorResponse](#schemaerrorresponse)|Dependency service not available.|

### Example response body

> 200 Response

```json
{
  "UserInformation": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}
```

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
      "SignIn": true,
      "Invitation": true,
      "Search": true
    },
    "Group": {
      "Authorize": true,
      "Search": true
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

<h2 id="tocS_AuthorizationCodeClient">AuthorizationCodeClient</h2>

<a id="schemaauthorizationcodeclient"></a>
<a id="schema_AuthorizationCodeClient"></a>
<a id="tocSauthorizationcodeclient"></a>
<a id="tocsauthorizationcodeclient"></a>

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
|*anonymous*|object|false|none|Object used during Authorization Code Client creation.|
|» AllowedCorsOrigins|[string]¦null|false|none|Gets or sets the values used by the default CORS policy service implementations to build a<br>CORS policy for JavaScript clients.|

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
|» RedirectUris|[string]¦null|false|none|Gets or sets the allowed URIs to which return tokens or authorization codes can be returned.<br>Wildcards are ignored. URIs must match exactly what you are redirecting to<br>after login. If URIs do not match, the authentication process will fail<br>with a bad_client error.<br>Maximum 10 per client.|
|» PostLogoutRedirectUris|[string]¦null|false|none|Gets or sets allowed URIs to redirect to after logout. Wildcards are ignored.<br>URIs must match exactly what you are redirecting to after logout.<br>Maximum 10 for client.|
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
|Enabled|boolean¦null|false|none|Gets or sets whether client is enabled. Client can be used for authentication<br>if set to true. Client cannot be used for authentication if set to false.|
|AccessTokenLifetime|integer(int32)¦null|false|none|Gets or sets lifetime of access token issued for this client after authentication.<br>Minimum 60 seconds. Maximum 3600 seconds. Defaults to 3600 seconds.|
|Tags|[string]¦null|false|none|Gets or sets for OSIsoft internal use only.|

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
|» RoleIds|[string]¦null|false|none|Gets or sets list of Roles to be assigned to this client. Member role is always required.<br>For security reasons we advise against assigning Admin roles to a client.|

<h2 id="tocS_AzureActiveDirectoryTenant">AzureActiveDirectoryTenant</h2>

<a id="schemaazureactivedirectorytenant"></a>
<a id="schema_AzureActiveDirectoryTenant"></a>
<a id="tocSazureactivedirectorytenant"></a>
<a id="tocsazureactivedirectorytenant"></a>

```json
{
  "Id": "string",
  "ConsentState": 0,
  "Domain": "string"
}

```

The model for an Azure Active Directory Tenant in Identity Storage.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string¦null|false|none|Gets or sets id of an Azure Active Directory Tenant.|
|ConsentState|[ConsentState](#schemaconsentstate)|false|none|Gets or sets Consent State of Azure Active Directory Tenant. Can be: NotConsented (0), Consented (1).|
|Domain|string¦null|false|none|Gets or sets Domain of Azure Active Directory Tenant.|

<h2 id="tocS_ConsentState">ConsentState</h2>

<a id="schemaconsentstate"></a>
<a id="schema_ConsentState"></a>
<a id="tocSconsentstate"></a>
<a id="tocsconsentstate"></a>

```json
0

```

AAD Tenant Consent State.
            

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer|false|none|AAD Tenant Consent State.|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|

<h2 id="tocS_ConsentInformation">ConsentInformation</h2>

<a id="schemaconsentinformation"></a>
<a id="schema_ConsentInformation"></a>
<a id="tocSconsentinformation"></a>
<a id="tocsconsentinformation"></a>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string"
}

```

Information about the recipient of the Azure Active Directory consent email.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|AzureActiveDirectoryConsentEmail|string(email)¦null|false|none|Gets or sets address to email consent.|
|AzureActiveDirectoryConsentGivenName|string¦null|false|none|Gets or sets preferred name to use in the consent email.|
|AzureActiveDirectoryConsentSurname|string¦null|false|none|Gets or sets preferred surname to use in the consent email.|
|AzureActiveDirectoryTenant|string¦null|false|none|Gets or sets Azure Active Directory Domain Name (e.g. mydomain.onmicrosoft.com).|
|AzureActiveDirectoryConsentTypes|string¦null|false|none|Gets or sets Azure Active Directory Consent Types.  <br>Valid Consent Type combinations include "SignIn" and "SignIn;ReadAllUsersGroups".|

<h2 id="tocS_ClientCredentialClientCreateResponse">ClientCredentialClientCreateResponse</h2>

<a id="schemaclientcredentialclientcreateresponse"></a>
<a id="schema_ClientCredentialClientCreateResponse"></a>
<a id="tocSclientcredentialclientcreateresponse"></a>
<a id="tocsclientcredentialclientcreateresponse"></a>

```json
{
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
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
}

```

Secret information returned after a Client Credential Client is created.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Secret|string¦null|false|none|Gets or sets client secret.|
|Id|integer(int32)|false|none|Gets or sets secret Id.|
|Description|string¦null|false|none|Gets or sets description for the initial secret for the client.|
|ExpirationDate|string(date-time)¦null|false|none|Gets or sets expiration date for the initial secret for the client.|
|Client|[ClientCredentialClient](#schemaclientcredentialclient)¦null|false|none|Gets or sets client Client Credential Client created.|

<h2 id="tocS_ClientCredentialClientCreate">ClientCredentialClientCreate</h2>

<a id="schemaclientcredentialclientcreate"></a>
<a id="schema_ClientCredentialClientCreate"></a>
<a id="tocSclientcredentialclientcreate"></a>
<a id="tocsclientcredentialclientcreate"></a>

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
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ClientCredentialClient](#schemaclientcredentialclient)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|Object used during Client creation.|
|» SecretDescription|string¦null|false|none|Gets or sets description for the initial secret for the client. Ensure that this is descriptive enough,<br>as it will be the only way to distinguish between multiple secrets and their usage for a<br>client.|
|» SecretExpirationDate|string(date-time)¦null|false|none|Gets or sets expiration date for the initial secret for the client. If set to null the secret will<br>never expire. We advise against such practice.|

<h2 id="tocS_ClientCredentialClientMultiStatusResponse">ClientCredentialClientMultiStatusResponse</h2>

<a id="schemaclientcredentialclientmultistatusresponse"></a>
<a id="schema_ClientCredentialClientMultiStatusResponse"></a>
<a id="tocSclientcredentialclientmultistatusresponse"></a>
<a id="tocsclientcredentialclientmultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
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
}

```

MultiStatusResponse objects returned in a 207 response.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|OperationId|string¦null|false|none|Gets or sets operationId that resulted in this error.|
|Error|string¦null|false|none|Gets or sets string message describing the error.|
|Reason|string¦null|false|none|Gets or sets reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]¦null|false|none|Gets or sets list of ChildErrors.|
|Data|[[ClientCredentialClient](#schemaclientcredentialclient)]¦null|false|none|Gets or sets data.|

<h2 id="tocS_MultiStatusResponseChildError">MultiStatusResponseChildError</h2>

<a id="schemamultistatusresponsechilderror"></a>
<a id="schema_MultiStatusResponseChildError"></a>
<a id="tocSmultistatusresponsechilderror"></a>
<a id="tocsmultistatusresponsechilderror"></a>

```json
{
  "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
  "Error": "Error message.",
  "Reason": "Reason that caused error.",
  "Resolution": "Possible solution for the error.",
  "StatusCode": 0,
  "ModelId": "string",
  "property1": null,
  "property2": null
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ErrorResponse](#schemaerrorresponse)|false|none|Object returned whenever there is an error.|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|ChildError objects returned in a 207 response.|
|» **additionalProperties**|any|false|none|none|
|» StatusCode|integer(int32)|false|none|Gets or sets hTTP status code.|
|» ModelId|string¦null|false|none|Gets or sets model ID.|

<h2 id="tocS_ClientCredentialClient2">ClientCredentialClient2</h2>

<a id="schemaclientcredentialclient2"></a>
<a id="schema_ClientCredentialClient2"></a>
<a id="tocSclientcredentialclient2"></a>
<a id="tocsclientcredentialclient2"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
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
|*anonymous*|[Client2](#schemaclient2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» RoleIds|[string]¦null|false|none|none|

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

<h2 id="tocS_ClientCredentialClientMultiStatusResponse2">ClientCredentialClientMultiStatusResponse2</h2>

<a id="schemaclientcredentialclientmultistatusresponse2"></a>
<a id="schema_ClientCredentialClientMultiStatusResponse2"></a>
<a id="tocSclientcredentialclientmultistatusresponse2"></a>
<a id="tocsclientcredentialclientmultistatusresponse2"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "ClientId": "string",
      "Id": "string",
      "Name": "string",
      "Enabled": true,
      "Tags": [
        "string"
      ],
      "RoleIds": [
        "string"
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|OperationId|string¦null|false|none|none|
|Error|string¦null|false|none|none|
|Reason|string¦null|false|none|none|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]¦null|false|none|none|
|Data|[[ClientCredentialClient2](#schemaclientcredentialclient2)]¦null|false|none|none|

<h2 id="tocS_ClientCredentialClientResponse">ClientCredentialClientResponse</h2>

<a id="schemaclientcredentialclientresponse"></a>
<a id="schema_ClientCredentialClientResponse"></a>
<a id="tocSclientcredentialclientresponse"></a>
<a id="tocsclientcredentialclientresponse"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z",
  "ClientSecret": "string",
  "SecretId": "string"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ClientCredentialClientCreate2](#schemaclientcredentialclientcreate2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» ClientSecret|string¦null|false|none|none|
|» SecretId|string¦null|false|none|none|

<h2 id="tocS_ClientCredentialClientCreate2">ClientCredentialClientCreate2</h2>

<a id="schemaclientcredentialclientcreate2"></a>
<a id="schema_ClientCredentialClientCreate2"></a>
<a id="tocSclientcredentialclientcreate2"></a>
<a id="tocsclientcredentialclientcreate2"></a>

```json
{
  "ClientId": "string",
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "Tags": [
    "string"
  ],
  "RoleIds": [
    "string"
  ],
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ClientCredentialClient2](#schemaclientcredentialclient2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» SecretDescription|string¦null|false|none|none|
|» SecretExpirationDate|string(date-time)¦null|false|none|none|

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
|Expires|boolean¦null|false|none|Gets or sets determines if the secret expires. Defaults to true.<br>If Expires is set to true (or null) and Expiration is not null, expiration of this secret will be enforced.<br>If Expires is set to true (or null) and Expiration is null, a 400 error will be returned.<br>If Expires is set to false and Expiration is not null, a 400 error will be returned.<br>If Expires is set to false and Expiration is null, there will be no expiration of this secret.|
|Description|string¦null|false|none|Gets or sets description for the client secret. We suggest being as descriptive as possible. This field will make identifying<br>secrets easier.|

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

<h2 id="tocS_DeviceCodeClient">DeviceCodeClient</h2>

<a id="schemadevicecodeclient"></a>
<a id="schema_DeviceCodeClient"></a>
<a id="tocSdevicecodeclient"></a>
<a id="tocsdevicecodeclient"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Enabled": true,
  "AccessTokenLifetime": 0,
  "Tags": [
    "string"
  ],
  "DeviceCodeLifetime": 0,
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
|*anonymous*|object|false|none|Object used for Device Code Clients.|
|» DeviceCodeLifetime|integer(int32)¦null|false|none|Gets or sets the lifetime of device codes in seconds.|
|» ClientUri|string¦null|false|none|Gets or sets URI to a page with information about client (used on consent screen).|
|» LogoUri|string¦null|false|none|Gets or sets URI to client logo (used on consent screen).|

<h2 id="tocS_HybridClientCreateResponse">HybridClientCreateResponse</h2>

<a id="schemahybridclientcreateresponse"></a>
<a id="schema_HybridClientCreateResponse"></a>
<a id="tocShybridclientcreateresponse"></a>
<a id="tocshybridclientcreateresponse"></a>

```json
{
  "Secret": "string",
  "Id": 0,
  "Description": "string",
  "ExpirationDate": "2019-08-24T14:15:22Z",
  "Client": {
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
    "AllowOfflineAccess": true,
    "AllowAccessTokensViaBrowser": true
  }
}

```

Secret information returned after a Hybrid Client is created.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Secret|string¦null|false|none|Gets or sets client secret.|
|Id|integer(int32)|false|none|Gets or sets secret Id.|
|Description|string¦null|false|none|Gets or sets description for the initial secret for the client.|
|ExpirationDate|string(date-time)¦null|false|none|Gets or sets expiration date for the initial secret for the client.|
|Client|[HybridClient](#schemahybridclient)¦null|false|none|Gets or sets Hybrid Client object created.|

<h2 id="tocS_HybridClient">HybridClient</h2>

<a id="schemahybridclient"></a>
<a id="schema_HybridClient"></a>
<a id="tocShybridclient"></a>
<a id="tocshybridclient"></a>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
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
|*anonymous*|object|false|none|Object used for Hybrid Clients.|
|» AllowOfflineAccess|boolean¦null|false|none|Gets or sets whether this client can request refresh tokens, by providing the *offline_access* scope.|
|» AllowAccessTokensViaBrowser|boolean¦null|false|none|Gets or sets whether this HybridClient is allowed to receive access tokens via the browser.<br>This is useful to harden flows that allow multiple response types (e.g. by disallowing a hybrid flow<br>client that is supposed to use code *id_token* to add the *token* response type, thus<br>leaking the token to the browser).|

<h2 id="tocS_HybridClientCreate">HybridClientCreate</h2>

<a id="schemahybridclientcreate"></a>
<a id="schema_HybridClientCreate"></a>
<a id="tocShybridclientcreate"></a>
<a id="tocshybridclientcreate"></a>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[HybridClient](#schemahybridclient)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|Object used during Hybrid Client creation.|
|» SecretDescription|string¦null|false|none|Gets or sets description for the initial secret for the client.|
|» SecretExpirationDate|string(date-time)¦null|false|none|Gets or sets expiration date for the initial secret for the client. If set to null the secret will<br>never expire. We advise against such practice.|

<h2 id="tocS_HybridClientResponse">HybridClientResponse</h2>

<a id="schemahybridclientresponse"></a>
<a id="schema_HybridClientResponse"></a>
<a id="tocShybridclientresponse"></a>
<a id="tocshybridclientresponse"></a>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z",
  "ClientSecret": "string",
  "SecretId": "string"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[HybridClientCreate2](#schemahybridclientcreate2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» ClientSecret|string¦null|false|none|none|
|» SecretId|string¦null|false|none|none|

<h2 id="tocS_HybridClientCreate2">HybridClientCreate2</h2>

<a id="schemahybridclientcreate2"></a>
<a id="schema_HybridClientCreate2"></a>
<a id="tocShybridclientcreate2"></a>
<a id="tocshybridclientcreate2"></a>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true,
  "SecretDescription": "string",
  "SecretExpirationDate": "2019-08-24T14:15:22Z"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[HybridClient2](#schemahybridclient2)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» SecretDescription|string¦null|false|none|none|
|» SecretExpirationDate|string(date-time)¦null|false|none|none|

<h2 id="tocS_HybridClient2">HybridClient2</h2>

<a id="schemahybridclient2"></a>
<a id="schema_HybridClient2"></a>
<a id="tocShybridclient2"></a>
<a id="tocshybridclient2"></a>

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
  "AllowOfflineAccess": true,
  "AllowAccessTokensViaBrowser": true
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
|» AllowOfflineAccess|boolean¦null|false|none|none|
|» AllowAccessTokensViaBrowser|boolean¦null|false|none|none|

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

<h2 id="tocS_IdentityProviderClaimCreate">IdentityProviderClaimCreate</h2>

<a id="schemaidentityproviderclaimcreate"></a>
<a id="schema_IdentityProviderClaimCreate"></a>
<a id="tocSidentityproviderclaimcreate"></a>
<a id="tocsidentityproviderclaimcreate"></a>

```json
{
  "Value": "string",
  "IdentityProviderClaimTypeNameId": "string",
  "RoleIds": [
    "string"
  ]
}

```

IdentityProvider Claim to Create.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Value|string¦null|false|none|Gets or sets the value for this IdentityProvider Claim.|
|IdentityProviderClaimTypeNameId|string(guid)|false|none|Gets or sets the Identity Provider Claim Type Name Id for this IdentityProvider Claim.|
|RoleIds|[string]¦null|false|none|Gets or sets the list of Role Ids associated with this IdentityProviderClaim.|

<h2 id="tocS_IdentityProviderClaimUpdate">IdentityProviderClaimUpdate</h2>

<a id="schemaidentityproviderclaimupdate"></a>
<a id="schema_IdentityProviderClaimUpdate"></a>
<a id="tocSidentityproviderclaimupdate"></a>
<a id="tocsidentityproviderclaimupdate"></a>

```json
{
  "Value": "string",
  "RoleIds": [
    "string"
  ]
}

```

Update information for an IdentityProvider Claim.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Value|string¦null|false|none|Gets or sets the value for this IdentityProvider Claim.|
|RoleIds|[string]¦null|false|none|Gets or sets the list of Role Ids associated with this IdentityProviderClaim.|

<h2 id="tocS_IdentityProviderConsent">IdentityProviderConsent</h2>

<a id="schemaidentityproviderconsent"></a>
<a id="schema_IdentityProviderConsent"></a>
<a id="tocSidentityproviderconsent"></a>
<a id="tocsidentityproviderconsent"></a>

```json
{
  "Scheme": "string",
  "property1": null,
  "property2": null
}

```

The model for an Identity Provider Consent in Identity Storage.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|any|false|none|none|
|Scheme|string¦null|false|none|Gets or sets the scheme of the Identity Provider.|

<h2 id="tocS_IdentityProviderAdd">IdentityProviderAdd</h2>

<a id="schemaidentityprovideradd"></a>
<a id="schema_IdentityProviderAdd"></a>
<a id="tocSidentityprovideradd"></a>
<a id="tocsidentityprovideradd"></a>

```json
{
  "AzureActiveDirectoryConsentEmail": "user@example.com",
  "AzureActiveDirectoryConsentGivenName": "string",
  "AzureActiveDirectoryConsentSurname": "string",
  "AzureActiveDirectoryTenant": "string",
  "AzureActiveDirectoryConsentTypes": "string",
  "IdentityProviderId": "string",
  "AzureActiveDirectorySendConsent": true
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ConsentInformation](#schemaconsentinformation)|false|none|Information about the recipient of the Azure Active Directory consent email.|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|Object for adding an Identity Provider.|
|» IdentityProviderId|string(guid)|false|none|Gets or sets Identity Provider Id to Add.|
|» AzureActiveDirectorySendConsent|boolean|false|none|Gets or sets a value indicating whether send consent email for Azure Active Directory.|

<h2 id="tocS_IdentityProviderResultsOfIdentityProviderUser">IdentityProviderResultsOfIdentityProviderUser</h2>

<a id="schemaidentityproviderresultsofidentityprovideruser"></a>
<a id="schema_IdentityProviderResultsOfIdentityProviderUser"></a>
<a id="tocSidentityproviderresultsofidentityprovideruser"></a>
<a id="tocsidentityproviderresultsofidentityprovideruser"></a>

```json
{
  "Results": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}

```

Result object for Identity Provider access users/groups.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Results|[[IdentityProviderUser](#schemaidentityprovideruser)]|false|none|List of users/groups.|
|SkipToken|string¦null|false|none|Skip token for paging.|

<h2 id="tocS_IdentityProviderUser">IdentityProviderUser</h2>

<a id="schemaidentityprovideruser"></a>
<a id="schema_IdentityProviderUser"></a>
<a id="tocSidentityprovideruser"></a>
<a id="tocsidentityprovideruser"></a>

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "user@example.com"
}

```

Base class for Identity provider access user.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string|false|none|Gets or sets Id of user.|
|GivenName|string¦null|false|none|Gets or sets given name of user.|
|Surname|string¦null|false|none|Gets or sets surname of user.|
|Name|string¦null|false|none|Gets or sets name of user.|
|Email|string(email)¦null|false|none|Gets or sets email of user.|

<h2 id="tocS_IdentityProviderResultsOfIdentityProviderGroup">IdentityProviderResultsOfIdentityProviderGroup</h2>

<a id="schemaidentityproviderresultsofidentityprovidergroup"></a>
<a id="schema_IdentityProviderResultsOfIdentityProviderGroup"></a>
<a id="tocSidentityproviderresultsofidentityprovidergroup"></a>
<a id="tocsidentityproviderresultsofidentityprovidergroup"></a>

```json
{
  "Results": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}

```

Result object for Identity Provider access users/groups.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Results|[[IdentityProviderGroup](#schemaidentityprovidergroup)]|false|none|List of users/groups.|
|SkipToken|string¦null|false|none|Skip token for paging.|

<h2 id="tocS_IdentityProviderGroup">IdentityProviderGroup</h2>

<a id="schemaidentityprovidergroup"></a>
<a id="schema_IdentityProviderGroup"></a>
<a id="tocSidentityprovidergroup"></a>
<a id="tocsidentityprovidergroup"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Email": "user@example.com"
}

```

Base class for Identity Provider access group.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string|false|none|Gets or sets the Object Id of IdentityProviderGroup.|
|Name|string¦null|false|none|Gets or sets group name of IdentityProviderGroup.|
|Email|string(email)¦null|false|none|Gets or sets the email address of the IdentityProviderGroup.|

<h2 id="tocS_IdentityProviderMembers">IdentityProviderMembers</h2>

<a id="schemaidentityprovidermembers"></a>
<a id="schema_IdentityProviderMembers"></a>
<a id="tocSidentityprovidermembers"></a>
<a id="tocsidentityprovidermembers"></a>

```json
{
  "Users": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "Groups": [
    {
      "Id": "string",
      "Name": "string",
      "Email": "user@example.com"
    }
  ],
  "SkipToken": "string"
}

```

Class to hold members in a group.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Users|[[IdentityProviderUser](#schemaidentityprovideruser)]|false|none|List of users.|
|Groups|[[IdentityProviderGroup](#schemaidentityprovidergroup)]|false|none|List of groups.|
|SkipToken|string¦null|false|none|Skip token for paging.|

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
|» AllowedCorsOrigins|[string]¦null|false|none|Gets or sets the values used by the default CORS policy service implementations to build a<br>CORS policy for JavaScript clients.<br>Maximum 10 for client.|

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

<h2 id="tocS_Role">Role</h2>

<a id="schemarole"></a>
<a id="schema_Role"></a>
<a id="tocSrole"></a>
<a id="tocsrole"></a>

```json
{
  "Id": "string",
  "Name": "string",
  "Description": "string",
  "RoleScope": 1,
  "TenantId": "string",
  "CommunityId": "string",
  "RoleTypeId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string(guid)¦null|false|none|none|
|Name|string¦null|false|none|none|
|Description|string¦null|false|none|none|
|RoleScope|[RoleScope](#schemarolescope)¦null|false|none|none|
|TenantId|string(guid)¦null|false|none|none|
|CommunityId|string(guid)¦null|false|none|none|
|RoleTypeId|string(guid)¦null|false|none|none|

<h2 id="tocS_RoleScope">RoleScope</h2>

<a id="schemarolescope"></a>
<a id="schema_RoleScope"></a>
<a id="tocSrolescope"></a>
<a id="tocsrolescope"></a>

```json
1

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|

<h2 id="tocS_User">User</h2>

<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "Id": "string",
  "GivenName": "string",
  "Surname": "string",
  "Name": "string",
  "Email": "string",
  "ContactEmail": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ExternalUserId": "string",
  "IdentityProviderId": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object for retrieving a User.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string(guid)|false|none|Gets or sets unique User ID.|
|GivenName|string¦null|false|none|Gets or sets given name of user.|
|Surname|string¦null|false|none|Gets or sets surname of user.|
|Name|string¦null|false|none|Gets or sets name of user.|
|Email|string¦null|false|none|Gets or sets email of user.|
|ContactEmail|string¦null|false|none|Gets or sets contact email for user. User will only be contacted<br>through this email.|
|ContactGivenName|string¦null|false|none|Gets or sets preferred contact name for user.|
|ContactSurname|string¦null|false|none|Gets or sets preferred contact surname for user.|
|ExternalUserId|string¦null|false|none|Gets or sets provider id for user. This is the unique ID we<br>get from the Identity Provider.|
|IdentityProviderId|string(guid)¦null|false|none|Gets or sets Identity Provider Id used to authenticate User.<br>Will be set once the User accepts an invitation.<br>If not specified when sending the invitation to<br>the User, it can be any of the Identity Provider<br>Ids configured for this Tenant.|
|RoleIds|[string]¦null|false|none|Gets or sets list of strings of RoleIds.|

<h2 id="tocS_UserMultiStatusResponse">UserMultiStatusResponse</h2>

<a id="schemausermultistatusresponse"></a>
<a id="schema_UserMultiStatusResponse"></a>
<a id="tocSusermultistatusresponse"></a>
<a id="tocsusermultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "Id": "string",
      "GivenName": "string",
      "Surname": "string",
      "Name": "string",
      "Email": "string",
      "ContactEmail": "string",
      "ContactGivenName": "string",
      "ContactSurname": "string",
      "ExternalUserId": "string",
      "IdentityProviderId": "string",
      "RoleIds": [
        "string"
      ]
    }
  ]
}

```

MultiStatusResponse objects returned in a 207 response.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|OperationId|string¦null|false|none|Gets or sets operationId that resulted in this error.|
|Error|string¦null|false|none|Gets or sets string message describing the error.|
|Reason|string¦null|false|none|Gets or sets reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]¦null|false|none|Gets or sets list of ChildErrors.|
|Data|[[User](#schemauser)]¦null|false|none|Gets or sets data.|

<h2 id="tocS_UserStatus">UserStatus</h2>

<a id="schemauserstatus"></a>
<a id="schema_UserStatus"></a>
<a id="tocSuserstatus"></a>
<a id="tocsuserstatus"></a>

```json
{
  "InvitationStatus": 0,
  "User": {
    "Id": "string",
    "GivenName": "string",
    "Surname": "string",
    "Name": "string",
    "Email": "string",
    "ContactEmail": "string",
    "ContactGivenName": "string",
    "ContactSurname": "string",
    "ExternalUserId": "string",
    "IdentityProviderId": "string",
    "RoleIds": [
      "string"
    ]
  }
}

```

Object used when getting User status.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|InvitationStatus|[UserInvitationStatus](#schemauserinvitationstatus)|false|none|Gets or sets status of user invitation. Can be: InvitationAccepted (0),  NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).|
|User|[User](#schemauser)¦null|false|none|Gets or sets user information.|

<h2 id="tocS_UserInvitationStatus">UserInvitationStatus</h2>

<a id="schemauserinvitationstatus"></a>
<a id="schema_UserInvitationStatus"></a>
<a id="tocSuserinvitationstatus"></a>
<a id="tocsuserinvitationstatus"></a>

```json
0

```

User Invitation Status.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer|false|none|User Invitation Status.|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|0|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|
|*anonymous*|4|

<h2 id="tocS_UserCreateOrUpdate">UserCreateOrUpdate</h2>

<a id="schemausercreateorupdate"></a>
<a id="schema_UserCreateOrUpdate"></a>
<a id="tocSusercreateorupdate"></a>
<a id="tocsusercreateorupdate"></a>

```json
{
  "Id": "string",
  "ExternalUserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "IdentityProviderId": "string",
  "IdentityProviderSpecificUserId": "string",
  "RoleIds": [
    "string"
  ]
}

```

Object when updating an User.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Id|string(guid)¦null|false|none|Gets or sets user Id for the user. When creating a user, if User ID is not specified, one will be generated.|
|ExternalUserId|string¦null|false|none|Gets or sets user ExternalUserId for the user. Must be specified if Identity Provider is Windows Active Directory.|
|ContactGivenName|string¦null|false|none|Gets or sets preferred name to be used when contacting user.|
|ContactSurname|string¦null|false|none|Gets or sets preferred surname to be used when contacting user.|
|ContactEmail|string(email)¦null|false|none|Gets or sets preferred contact email to be used. This does not have to be the same as the user's Identity Provider email.|
|IdentityProviderId|string(guid)¦null|false|none|Gets or sets Identity Provider this user will be required to use to login.  If null, the Identity Provider Id will<br>be set when creating the Invitation.|
|IdentityProviderSpecificUserId|string¦null|false|none|Identity Provider Specific User Id. Ex. ObjectId for AD and AAD.|
|RoleIds|[string]¦null|false|none|Gets or sets list of strings of RoleIds.|

<h2 id="tocS_UserStatusMultiStatusResponse">UserStatusMultiStatusResponse</h2>

<a id="schemauserstatusmultistatusresponse"></a>
<a id="schema_UserStatusMultiStatusResponse"></a>
<a id="tocSuserstatusmultistatusresponse"></a>
<a id="tocsuserstatusmultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": [
    {
      "InvitationStatus": 0,
      "User": {
        "Id": "string",
        "GivenName": "string",
        "Surname": "string",
        "Name": "string",
        "Email": "string",
        "ContactEmail": "string",
        "ContactGivenName": "string",
        "ContactSurname": "string",
        "ExternalUserId": "string",
        "IdentityProviderId": "string",
        "RoleIds": [
          "string"
        ]
      }
    }
  ]
}

```

MultiStatusResponse objects returned in a 207 response.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|OperationId|string¦null|false|none|Gets or sets operationId that resulted in this error.|
|Error|string¦null|false|none|Gets or sets string message describing the error.|
|Reason|string¦null|false|none|Gets or sets reason that caused the error.|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]¦null|false|none|Gets or sets list of ChildErrors.|
|Data|[[UserStatus](#schemauserstatus)]¦null|false|none|Gets or sets data.|

<h2 id="tocS_UserCreateOrUpdate2">UserCreateOrUpdate2</h2>

<a id="schemausercreateorupdate2"></a>
<a id="schema_UserCreateOrUpdate2"></a>
<a id="tocSusercreateorupdate2"></a>
<a id="tocsusercreateorupdate2"></a>

```json
{
  "UserId": "string",
  "ContactGivenName": "string",
  "ContactSurname": "string",
  "ContactEmail": "user@example.com",
  "RoleIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|UserId|string(guid)¦null|false|none|none|
|ContactGivenName|string¦null|false|none|none|
|ContactSurname|string¦null|false|none|none|
|ContactEmail|string(email)¦null|false|none|none|
|RoleIds|[string]¦null|false|none|none|

<h2 id="tocS_UserInformationResponse">UserInformationResponse</h2>

<a id="schemauserinformationresponse"></a>
<a id="schema_UserInformationResponse"></a>
<a id="tocSuserinformationresponse"></a>
<a id="tocsuserinformationresponse"></a>

```json
{
  "UserInformation": {
    "property1": [
      "string"
    ],
    "property2": [
      "string"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|UserInformation|object¦null|false|none|none|
|» **additionalProperties**|[string]|false|none|none|

<h2 id="tocS_UserInformationMultiStatusResponse">UserInformationMultiStatusResponse</h2>

<a id="schemauserinformationmultistatusresponse"></a>
<a id="schema_UserInformationMultiStatusResponse"></a>
<a id="tocSuserinformationmultistatusresponse"></a>
<a id="tocsuserinformationmultistatusresponse"></a>

```json
{
  "OperationId": "string",
  "Error": "string",
  "Reason": "string",
  "ChildErrors": [
    {
      "OperationId": "1b2af18e-8b27-4f86-93e0-6caa3e59b90c",
      "Error": "Error message.",
      "Reason": "Reason that caused error.",
      "Resolution": "Possible solution for the error.",
      "StatusCode": 0,
      "ModelId": "string",
      "property1": null,
      "property2": null
    }
  ],
  "Data": {
    "UserInformation": {
      "property1": [
        "string"
      ],
      "property2": [
        "string"
      ]
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|OperationId|string¦null|false|none|none|
|Error|string¦null|false|none|none|
|Reason|string¦null|false|none|none|
|ChildErrors|[[MultiStatusResponseChildError](#schemamultistatusresponsechilderror)]¦null|false|none|none|
|Data|[UserInformationResponse](#schemauserinformationresponse)¦null|false|none|none|

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

