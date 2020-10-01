---
id: discountsapi
title: DiscountsApi
---

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**activateRandomYatCode**](DiscountsApi.md#activaterandomyatcode) | **POST** /codes/{code_id}/random_yat | Use random yat code
[**addPubkeyForCode**](DiscountsApi.md#addpubkeyforcode) | **POST** /codes/{code_id}/pubkeys/{pubkey} | Add pubkey for code
[**listCodes**](DiscountsApi.md#listcodes) | **GET** /codes | Fetch codes
[**revokePubkeyForCode**](DiscountsApi.md#revokepubkeyforcode) | **DELETE** /codes/{code_id}/pubkeys/{pubkey} | Revoke pubkey for code



### activateRandomYatCode

```js
/**
* @returns DisplayOrder
**/
async function activateRandomYatCode(codeId: String, body: RandomYatActivateBody)
```

Use random yat code

#### Notes:
Creates cart with random yat generated according to pattern with applied discount

#### Example

```javascript
const yat = require('yatjs');
const api = new yat.YatJs();

await api.login("your@email.com", "your_password");

let codeId = null; // String 
// populate codeId...

let body = new YatJs.RandomYatActivateBody(); // RandomYatActivateBody 
// populate body...

try {
  let res = await api.discounts().activateRandomYatCode(codeId, body);
  // res is of type DisplayOrder
  console.log('API called successfully. Result: ', res);
} catch (error) {
  console.error(error);
}

```

#### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**codeId** | [**String**](../sdk_nodejs_index#)
|  | 
**body** | [**RandomYatActivateBody**](../sdk_nodejs_index#randomyatactivatebody)
|  | 

#### Return type


[**DisplayOrder**](../sdk_nodejs_index#DisplayOrder)


#### Authorization

[JWT](../sdk_nodejs_index#JWT)

#### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*


### addPubkeyForCode

```js
/**
* @returns String
**/
async function addPubkeyForCode(codeId: String, pubkey: String)
```

Add pubkey for code

#### Notes:
NOTE: user should have scope `OrganizationCodeAdmin` or `CodeWrite`

#### Example

```javascript
const yat = require('yatjs');
const api = new yat.YatJs();


await api.login("your@email.com", "your_password");

let codeId = null; // String 
// populate codeId...

let pubkey = "pubkey_example"; // String | Public key to authorize usage of a code
// populate pubkey...

try {
  let res = await api.discounts().addPubkeyForCode(codeId, pubkey);
  // res is of type String
  console.log('API called successfully. Result: ', res);
} catch (error) {
  console.error(error);
}

```

#### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**codeId** | [**String**](../sdk_nodejs_index#)
|  | 
**pubkey** | **String**| Public key to authorize usage of a code | 

#### Return type

**String**


#### Authorization

[JWT](../sdk_nodejs_index#JWT), [two_factor](../sdk_nodejs_index#two_factor)

#### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*


### listCodes

```js
/**
* @returns ListOfCodeAvailability
**/
async function listCodes(opts)
```

Fetch codes

#### Notes:
Return codes with their usage and availability information NOTE: user should have scope `OrganizationCodeAdmin` or `CodeRead`

#### Example

```javascript
const yat = require('yatjs');
const api = new yat.YatJs();

await api.login("your@email.com", "your_password");

let opts = {
  'codeType': "codeType_example", // String | Optional: filter by code type
  'dir': "dir_example", // String | 
  'limit': 56, // Number | 
  'organizationId': null, // String | Optional: filter by organization id
  'page': 56, // Number | 
  'sort': "sort_example" // String | 
};
try {
  let res = await api.discounts().listCodes(opts);
  // res is of type ListOfCodeAvailability
  console.log('API called successfully. Result: ', res);
} catch (error) {
  console.error(error);
}

```

#### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**codeType** | **String**| Optional: filter by code type | [optional] 
**dir** | **String**|  | [optional] 
**limit** | **Number**|  | [optional] 
**organizationId** | [**String**](../sdk_nodejs_index#)
| Optional: filter by organization id | [optional] 
**page** | **Number**|  | [optional] 
**sort** | **String**|  | [optional] 

#### Return type


[**ListOfCodeAvailability**](../sdk_nodejs_index#ListOfCodeAvailability)


#### Authorization

[JWT](../sdk_nodejs_index#JWT)

#### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*


### revokePubkeyForCode

```js
/**
* @returns String
**/
async function revokePubkeyForCode(codeId: String, pubkey: String)
```

Revoke pubkey for code

#### Notes:
NOTE: user should have scope `OrganizationCodeAdmin` or `CodeWrite`

#### Example

```javascript
const yat = require('yatjs');
const api = new yat.YatJs();


await api.login("your@email.com", "your_password");

let codeId = null; // String 
// populate codeId...

let pubkey = "pubkey_example"; // String | Public key to authorize usage of a code
// populate pubkey...

try {
  let res = await api.discounts().revokePubkeyForCode(codeId, pubkey);
  // res is of type String
  console.log('API called successfully. Result: ', res);
} catch (error) {
  console.error(error);
}

```

#### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**codeId** | [**String**](../sdk_nodejs_index#)
|  | 
**pubkey** | **String**| Public key to authorize usage of a code | 

#### Return type

**String**


#### Authorization

[JWT](../sdk_nodejs_index#JWT), [two_factor](../sdk_nodejs_index#two_factor)

#### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: */*
