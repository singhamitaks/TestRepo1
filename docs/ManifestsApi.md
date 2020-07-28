# Org.OpenAPITools.Api.ManifestsApi

All URIs are relative to *https://api-qa.pitneybowes.com/shippingservices*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateManifestUsingPOST1**](ManifestsApi.md#createmanifestusingpost1) | **POST** /v1/manifests | This operation creates an end-of-day manifest
[**ReprintManifestUsingGET**](ManifestsApi.md#reprintmanifestusingget) | **GET** /v1/manifests/{manifestId} | reprintManifest
[**RetryManifestUsingGET**](ManifestsApi.md#retrymanifestusingget) | **GET** /v1/manifests | retryManifest



## CreateManifestUsingPOST1

> Manifest CreateManifestUsingPOST1 (string acceptLanguage, string contentType, string xPBTransactionId, Manifest manifest, string xPBUnifiedErrorStructure = null)

This operation creates an end-of-day manifest

This operation creates an end-of-day manifest that either combines all parcels into a single form or electronically closes the day, depending on the carrier. Use the instructions appropriate to the carrier. * Create a [USPS SCAN Form](https://shipping.pitneybowes.com/api/post-manifests-scan.html)  * Create a [Newgistics Closeout](https://shipping.pitneybowes.com/api/post-manifests-newgistics.html) * Create a [PB Presort Pickup Slip](https://shipping.pitneybowes.com/api/post-manifests-presort.html) * Create a [Manifest for PMOD Shipments](https://shipping.pitneybowes.com/api/post-manifests-pmod.html)

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class CreateManifestUsingPOST1Example
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ManifestsApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var xPBTransactionId = xPBTransactionId_example;  // string | Required. A unique identifier for the transaction, up to 25 characters.
            var manifest = new Manifest(); // Manifest | manifest
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // This operation creates an end-of-day manifest
                Manifest result = apiInstance.CreateManifestUsingPOST1(acceptLanguage, contentType, xPBTransactionId, manifest, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ManifestsApi.CreateManifestUsingPOST1: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **acceptLanguage** | **string**| This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. | [default to &quot;en-US&quot;]
 **contentType** | **string**| This mentions the content type getting passed in body of request. | [default to &quot;application/json&quot;]
 **xPBTransactionId** | **string**| Required. A unique identifier for the transaction, up to 25 characters. | 
 **manifest** | [**Manifest**](Manifest.md)| manifest | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**Manifest**](Manifest.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | OK |  -  |
| **0** | Error |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ReprintManifestUsingGET

> Manifest ReprintManifestUsingGET (string acceptLanguage, string contentType, string manifestId, string xPBUnifiedErrorStructure = null)

reprintManifest

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class ReprintManifestUsingGETExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ManifestsApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var manifestId = manifestId_example;  // string | manifestId
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // reprintManifest
                Manifest result = apiInstance.ReprintManifestUsingGET(acceptLanguage, contentType, manifestId, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ManifestsApi.ReprintManifestUsingGET: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **acceptLanguage** | **string**| This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. | [default to &quot;en-US&quot;]
 **contentType** | **string**| This mentions the content type getting passed in body of request. | [default to &quot;application/json&quot;]
 **manifestId** | **string**| manifestId | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**Manifest**](Manifest.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **201** | OK |  -  |
| **0** | Error |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RetryManifestUsingGET

> Manifest RetryManifestUsingGET (string acceptLanguage, string contentType, string originalTransactionId, string xPBUnifiedErrorStructure = null)

retryManifest

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class RetryManifestUsingGETExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ManifestsApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var originalTransactionId = originalTransactionId_example;  // string | 
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // retryManifest
                Manifest result = apiInstance.RetryManifestUsingGET(acceptLanguage, contentType, originalTransactionId, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ManifestsApi.RetryManifestUsingGET: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **acceptLanguage** | **string**| This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. | [default to &quot;en-US&quot;]
 **contentType** | **string**| This mentions the content type getting passed in body of request. | [default to &quot;application/json&quot;]
 **originalTransactionId** | **string**|  | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**Manifest**](Manifest.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **201** | OK |  -  |
| **0** | Error |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

