---
title: Identity_Storage_Controllers_Api_Tenants_Users_Users v20210115.07
language_tabs: []
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins-osisoft v1.0.1

---

<h1 id="identity_storage_controllers_api_tenants_users_users-users">Users</h1>

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
|200|Inline|List of Users found.|
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

Get invitation statuses for multiple users. Optionally restrict it only to users of a specific invitation status. The User status can be: InvitationAccepted (0),  NoInvitation (1), InvitationNotSent (2), InvitationSent (3), InvitationExpired (4).

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
|200|Inline|List of User Statuses found.|
|400|[ErrorResponse](#schemaerrorresponse)|Missing or invalid inputs. Test|
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
|200|Inline|List of Users found.|
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
|200|Inline|List of User Statuses found.|
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

# Schemas

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
|ContactEmail|string¦null|false|none|Gets or sets contact email for user. User will only be contacted<br />through this email.|
|ContactGivenName|string¦null|false|none|Gets or sets preferred contact name for user.|
|ContactSurname|string¦null|false|none|Gets or sets preferred contact surname for user.|
|ExternalUserId|string¦null|false|none|Gets or sets provider id for user. This is the unique ID we<br />get from the Identity Provider.|
|IdentityProviderId|string(guid)¦null|false|none|Gets or sets Identity Provider Id used to authenticate User.<br />Will be set once the User accepts an invitation.<br />If not specified when sending the invitation to<br />the User, it can be any of the Identity Provider<br />Ids configured for this Tenant.|
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
|IdentityProviderId|string(guid)¦null|false|none|Gets or sets Identity Provider this user will be required to use to login.  If null, the Identity Provider Id will<br />be set when creating the Invitation.|
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
          null
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

