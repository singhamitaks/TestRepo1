# Org.OpenAPITools.Api.TrackingApi

All URIs are relative to *https://api-qa.pitneybowes.com/shippingservices*

Method | HTTP request | Description
------------- | ------------- | -------------
[**AddTrackingEvents**](TrackingApi.md#addtrackingevents) | **GET** /v2/track/events | getTrackingDetails
[**GetTrackingDetailsUsingGET**](TrackingApi.md#gettrackingdetailsusingget) | **GET** /v1/tracking/{trackingNumber} | getTrackingDetails



## AddTrackingEvents

> AddTrackingEvents AddTrackingEvents (string acceptLanguage, string contentType, string xPBUnifiedErrorStructure = null)

getTrackingDetails

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class AddTrackingEventsExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new TrackingApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // getTrackingDetails
                AddTrackingEvents result = apiInstance.AddTrackingEvents(acceptLanguage, contentType, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling TrackingApi.AddTrackingEvents: " + e.Message );
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
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**AddTrackingEvents**](AddTrackingEvents.md)

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


## GetTrackingDetailsUsingGET

> TrackingResponse GetTrackingDetailsUsingGET (string acceptLanguage, string contentType, string trackingNumber, string packageIdentifierType, string carrier, string xPBUnifiedErrorStructure = null)

getTrackingDetails

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class GetTrackingDetailsUsingGETExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new TrackingApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var trackingNumber = trackingNumber_example;  // string | The tracking number for the shipment.
            var packageIdentifierType = packageIdentifierType_example;  // string | packageIdentifierType (default to "TrackingNumber")
            var carrier = carrier_example;  // string | carrier
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // getTrackingDetails
                TrackingResponse result = apiInstance.GetTrackingDetailsUsingGET(acceptLanguage, contentType, trackingNumber, packageIdentifierType, carrier, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling TrackingApi.GetTrackingDetailsUsingGET: " + e.Message );
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
 **trackingNumber** | **string**| The tracking number for the shipment. | 
 **packageIdentifierType** | **string**| packageIdentifierType | [default to &quot;TrackingNumber&quot;]
 **carrier** | **string**| carrier | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**TrackingResponse**](TrackingResponse.md)

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

