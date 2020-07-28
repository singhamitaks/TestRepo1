# Org.OpenAPITools.Api.ParcelProtectionApi

All URIs are relative to *https://api-qa.pitneybowes.com/shippingservices*

Method | HTTP request | Description
------------- | ------------- | -------------
[**GetParcelProtectionReports**](ParcelProtectionApi.md#getparcelprotectionreports) | **GET** /v1/parcel-protection/{developerId}/policies | Parcel Protection Reports
[**ParcelProtectionCoverage**](ParcelProtectionApi.md#parcelprotectioncoverage) | **POST** /v1/parcel-protection/create | Parcel Protection Coverage
[**ParcelProtectionQuote**](ParcelProtectionApi.md#parcelprotectionquote) | **POST** /v1/parcel-protection/quote | Parcel Protection Quote
[**ParcelProtectionVoid**](ParcelProtectionApi.md#parcelprotectionvoid) | **POST** /v1/parcel-protection/void | Parcel Protection Coverage



## GetParcelProtectionReports

> ParcelProtectionPolicyResponse GetParcelProtectionReports (string acceptLanguage, string contentType, string xPBTransactionId, string developerId, string policyCreatedFromDate, string policyCreatedToDate, string policyReferenceId, string parcelTrackingNumber, string merchantId, string policyStatus, string size, string page, string sort, string xPBUnifiedErrorStructure = null)

Parcel Protection Reports

This operation retrieves the policy status and other information on the Parcel Protection policies you have purchased for your shipments. Further Details https://shipping.pitneybowes.com/api/get-parcel-protection-reports.html

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class GetParcelProtectionReportsExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ParcelProtectionApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var xPBTransactionId = xPBTransactionId_example;  // string | Required. A unique identifier for the transaction, up to 25 characters.
            var developerId = developerId_example;  // string | Required. Your Pitney Bowes developer ID.
            var policyCreatedFromDate = policyCreatedFromDate_example;  // string | The beginning of the date range. Specify this value in UTC using the ISO 8601 standard. You must include both date and time, and you must end the time with Z to indicate a zero offset.
            var policyCreatedToDate = policyCreatedToDate_example;  // string | The end of the date range. Specify this value in UTC using the ISO 8601 standard. You must include both date and time, and you must end the time with Z to indicate a zero offset.
            var policyReferenceId = policyReferenceId_example;  // string | The unique identifier for the PB Parcel Protection policy.].
            var parcelTrackingNumber = parcelTrackingNumber_example;  // string | The parcel tracking number of the shipment that the policy applies to.
            var merchantId = merchantId_example;  // string | The merchant's Shipper ID. This is the value of the postalReportingNumber element in the Merchant Object.
            var policyStatus = policyStatus_example;  // string | Whether the policy is active or voided.
            var size = size_example;  // string | The number of transactions to return per page in the result set.
            var page = page_example;  // string | The index number of the page to return. Page index numbering starts at 0. Specifying page=0 returns the first page of the result set.
            var sort = sort_example;  // string | Defines a property to sort on and the sort order. Sort order can be ascending (asc) or descending (desc).
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // Parcel Protection Reports
                ParcelProtectionPolicyResponse result = apiInstance.GetParcelProtectionReports(acceptLanguage, contentType, xPBTransactionId, developerId, policyCreatedFromDate, policyCreatedToDate, policyReferenceId, parcelTrackingNumber, merchantId, policyStatus, size, page, sort, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ParcelProtectionApi.GetParcelProtectionReports: " + e.Message );
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
 **developerId** | **string**| Required. Your Pitney Bowes developer ID. | 
 **policyCreatedFromDate** | **string**| The beginning of the date range. Specify this value in UTC using the ISO 8601 standard. You must include both date and time, and you must end the time with Z to indicate a zero offset. | 
 **policyCreatedToDate** | **string**| The end of the date range. Specify this value in UTC using the ISO 8601 standard. You must include both date and time, and you must end the time with Z to indicate a zero offset. | 
 **policyReferenceId** | **string**| The unique identifier for the PB Parcel Protection policy.]. | 
 **parcelTrackingNumber** | **string**| The parcel tracking number of the shipment that the policy applies to. | 
 **merchantId** | **string**| The merchant&#39;s Shipper ID. This is the value of the postalReportingNumber element in the Merchant Object. | 
 **policyStatus** | **string**| Whether the policy is active or voided. | 
 **size** | **string**| The number of transactions to return per page in the result set. | 
 **page** | **string**| The index number of the page to return. Page index numbering starts at 0. Specifying page&#x3D;0 returns the first page of the result set. | 
 **sort** | **string**| Defines a property to sort on and the sort order. Sort order can be ascending (asc) or descending (desc). | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**ParcelProtectionPolicyResponse**](ParcelProtectionPolicyResponse.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ParcelProtectionCoverage

> ParcelProtectionCreateResponse ParcelProtectionCoverage (string acceptLanguage, string contentType, string xPBTransactionId, ParcelProtectionCreateRequest parcelProtectionCreateRequest, string xPBUnifiedErrorStructure = null)

Parcel Protection Coverage

This API lets merchants request Pitney Bowes [Parcel Protection](https://shipping.pitneybowes.com/faqs/parcel-protection.html) coverage for shipments. Merchants can request coverage for shipments created with the Shipping APIs as well as for shipments created with other platforms.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class ParcelProtectionCoverageExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ParcelProtectionApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var xPBTransactionId = xPBTransactionId_example;  // string | Required. A unique identifier for the transaction, up to 25 characters.
            var parcelProtectionCreateRequest = new ParcelProtectionCreateRequest(); // ParcelProtectionCreateRequest | manifest
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // Parcel Protection Coverage
                ParcelProtectionCreateResponse result = apiInstance.ParcelProtectionCoverage(acceptLanguage, contentType, xPBTransactionId, parcelProtectionCreateRequest, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ParcelProtectionApi.ParcelProtectionCoverage: " + e.Message );
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
 **parcelProtectionCreateRequest** | [**ParcelProtectionCreateRequest**](ParcelProtectionCreateRequest.md)| manifest | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**ParcelProtectionCreateResponse**](ParcelProtectionCreateResponse.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ParcelProtectionQuote

> ParcelProtectionQuoteResponse ParcelProtectionQuote (string acceptLanguage, string contentType, string xPBTransactionId, ParcelProtectionQuoteRequest parcelProtectionQuoteRequest, string xPBUnifiedErrorStructure = null)

Parcel Protection Quote

This API provides a quote for covering a shipment through Pitney Bowes [Parcel Protection](https://www.pitneybowes.com/us/ecommerce-delivery-services/parcel-protection.html).

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class ParcelProtectionQuoteExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ParcelProtectionApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var xPBTransactionId = xPBTransactionId_example;  // string | Required. A unique identifier for the transaction, up to 25 characters.
            var parcelProtectionQuoteRequest = new ParcelProtectionQuoteRequest(); // ParcelProtectionQuoteRequest | manifest
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // Parcel Protection Quote
                ParcelProtectionQuoteResponse result = apiInstance.ParcelProtectionQuote(acceptLanguage, contentType, xPBTransactionId, parcelProtectionQuoteRequest, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ParcelProtectionApi.ParcelProtectionQuote: " + e.Message );
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
 **parcelProtectionQuoteRequest** | [**ParcelProtectionQuoteRequest**](ParcelProtectionQuoteRequest.md)| manifest | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**ParcelProtectionQuoteResponse**](ParcelProtectionQuoteResponse.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ParcelProtectionVoid

> VoidParcelProtectionResponse ParcelProtectionVoid (string acceptLanguage, string contentType, string xPBTransactionId, string parcelProtectionReferenceId, VoidParcelProtectionRequest voidParcelProtectionRequest, string xPBUnifiedErrorStructure = null)

Parcel Protection Coverage

This API lets merchants request Pitney Bowes [Parcel Protection](https://shipping.pitneybowes.com/faqs/parcel-protection.html) coverage for shipments. Merchants can request coverage for shipments created with the Shipping APIs as well as for shipments created with other platforms.

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class ParcelProtectionVoidExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ParcelProtectionApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var xPBTransactionId = xPBTransactionId_example;  // string | Required. A unique identifier for the transaction, up to 25 characters.
            var parcelProtectionReferenceId = parcelProtectionReferenceId_example;  // string | Required. The identifier for the PB Parcel Protection policy that is being voided.
            var voidParcelProtectionRequest = new VoidParcelProtectionRequest(); // VoidParcelProtectionRequest | manifest
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")

            try
            {
                // Parcel Protection Coverage
                VoidParcelProtectionResponse result = apiInstance.ParcelProtectionVoid(acceptLanguage, contentType, xPBTransactionId, parcelProtectionReferenceId, voidParcelProtectionRequest, xPBUnifiedErrorStructure);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ParcelProtectionApi.ParcelProtectionVoid: " + e.Message );
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
 **parcelProtectionReferenceId** | **string**| Required. The identifier for the PB Parcel Protection policy that is being voided. | 
 **voidParcelProtectionRequest** | [**VoidParcelProtectionRequest**](VoidParcelProtectionRequest.md)| manifest | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]

### Return type

[**VoidParcelProtectionResponse**](VoidParcelProtectionResponse.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

