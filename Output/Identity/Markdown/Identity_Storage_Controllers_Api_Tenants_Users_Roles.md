---
title: Identity_Storage_Controllers_Api_Tenants_Users_Roles v20210115.08
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_controllers_api_tenants_users_roles-roles">Roles</h1>

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
|200|Inline|List of Roles found.|
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
|200|Inline|No content.|
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

# Schemas

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

