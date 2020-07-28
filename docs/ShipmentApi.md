# Org.OpenAPITools.Api.ShipmentApi

All URIs are relative to *https://api-qa.pitneybowes.com/shippingservices*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CancelShipmentUsingDELETE1**](ShipmentApi.md#cancelshipmentusingdelete1) | **DELETE** /v1/shipments/{shipmentId} | cancelShipment
[**CreateShipmentUsingPOST1**](ShipmentApi.md#createshipmentusingpost1) | **POST** /v1/shipments | This operation creates a shipment and purchases a shipment label.
[**ReprintShipmentUsingGET**](ShipmentApi.md#reprintshipmentusingget) | **GET** /v1/shipments/{shipmentId} | reprintShipment
[**RetryShipmentUsingGET**](ShipmentApi.md#retryshipmentusingget) | **GET** /v1/shipments | retryShipment



## CancelShipmentUsingDELETE1

> CancelShipment CancelShipmentUsingDELETE1 (string xPBTransactionId, string shipmentId, string xPBUnifiedErrorStructure = null, string xPBShipperCarrierAccountId = null, string cancelInitiator = null, Carrier? carrier = null)

cancelShipment

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class CancelShipmentUsingDELETE1Example
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ShipmentApi(Configuration.Default);
            var xPBTransactionId = xPBTransactionId_example;  // string | Required. A unique identifier for the transaction, up to 25 characters.
            var shipmentId = shipmentId_example;  // string | shipmentId
            var xPBUnifiedErrorStructure = xPBUnifiedErrorStructure_example;  // string | Recommended. Set this to true to use the standard error object if an error occurs. (optional)  (default to "true")
            var xPBShipperCarrierAccountId = xPBShipperCarrierAccountId_example;  // string | UPS Only. The unique identifier returned in the shipperCarrierAccountId field by the [Register an Existing Carrier Account API.(https://shipping.pitneybowes.com/api/post-carrier-accounts-register.html) (optional) 
            var cancelInitiator = SHIPPER;  // string | Indicates that this refund request is initiated by the shipper. Set this to: SHIPPER (optional) 
            var carrier = USPS;  // Carrier? | Conditional. The carrier. This is required if the carrier is not USPS (optional) 

            try
            {
                // cancelShipment
                CancelShipment result = apiInstance.CancelShipmentUsingDELETE1(xPBTransactionId, shipmentId, xPBUnifiedErrorStructure, xPBShipperCarrierAccountId, cancelInitiator, carrier);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ShipmentApi.CancelShipmentUsingDELETE1: " + e.Message );
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
 **xPBTransactionId** | **string**| Required. A unique identifier for the transaction, up to 25 characters. | 
 **shipmentId** | **string**| shipmentId | 
 **xPBUnifiedErrorStructure** | **string**| Recommended. Set this to true to use the standard error object if an error occurs. | [optional] [default to &quot;true&quot;]
 **xPBShipperCarrierAccountId** | **string**| UPS Only. The unique identifier returned in the shipperCarrierAccountId field by the [Register an Existing Carrier Account API.(https://shipping.pitneybowes.com/api/post-carrier-accounts-register.html) | [optional] 
 **cancelInitiator** | **string**| Indicates that this refund request is initiated by the shipper. Set this to: SHIPPER | [optional] 
 **carrier** | **Carrier?**| Conditional. The carrier. This is required if the carrier is not USPS | [optional] 

### Return type

[**CancelShipment**](CancelShipment.md)

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


## CreateShipmentUsingPOST1

> Shipment CreateShipmentUsingPOST1 (string xPBTransactionId, Shipment shipment, string xPBUnifiedErrorStructure = null, string xPBIntegratorCarrierId = null, string xPBShipperRatePlan = null, string xPBShipmentGroupId = null, string xPBShipperCarrierAccountId = null, string includeDeliveryCommitment = null)

This operation creates a shipment and purchases a shipment label.

The API returns the label as either a Base64 string or a link to a PDF. For more information visit [Create Shipment Documents](https://shipping.pitneybowes.com/api/post-shipments.html). Following are samples of different carriers -  * [Create a USPS (U.S. Postal Service) Label](https://shipping.pitneybowes.com/api/post-shipments-usps.html)  * [Create a USPS PMOD Label](https://shipping.pitneybowes.com/api/post-shipments-pmod.html) * [Create a USPS Scan-Based Return Label](https://shipping.pitneybowes.com/api/post-shipments-returns.html) * [Create a Pure Post Return Label](https://shipping.pitneybowes.com/api/post-shipments-pure-post-return.html) * [Create a Newgistics Label](https://shipping.pitneybowes.com/api/post-shipments-newgistics.html) * [Create a PB Presort Label](https://shipping.pitneybowes.com/api/post-shipments-presort.html) * [Create a PB Cross-Border Shipment](https://shipping.pitneybowes.com/api/post-shipments-cbds.html) * [Create a UPS (United Parcel Service) Label](https://shipping.pitneybowes.com/api/post-shipments-ups.html)

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class CreateShipmentUsingPOST1Example
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ShipmentApi(Configuration.Default);
            var xPBTransactionId = ship - zkLiDvFSCfyIS7rg1t;  // string | Required. A unique identifier for the transaction, up to 25 characters.
            var shipment = new Shipment(); // Shipment | request
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")
            var xPBIntegratorCarrierId = xPBIntegratorCarrierId_example;  // string | USPS Only. Negotiated services rate, if applicable. (optional) 
            var xPBShipperRatePlan = xPBShipperRatePlan_example;  // string | USPS Only. Shipper rate plan, if applicable. For more information, see [this FAQ](https://shipping.pitneybowes.com/faqs/rates.html#rate-plans-faq). (optional) 
            var xPBShipmentGroupId = xPBShipmentGroupId_example;  // string |  **[Required parameter for PBPresort service](https://shipping.pitneybowes.com/api/post-shipments-presort.html)**.The job number that represents the agreement between the merchant and PB Presort. This was provided by Pitney Bowes during [merchant onboarding for PB Presort](https://shipping.pitneybowes.com/carriers/pb-presort.html). (optional) 
            var xPBShipperCarrierAccountId = xPBShipperCarrierAccountId_example;  // string | **[Required parameter for PBPresort service](https://shipping.pitneybowes.com/api/post-shipments-presort.html)**. The merchant's Mailer ID (MID), as provided by Pitney Bowes during merchant onboarding for PB Presort. (optional) 
            var includeDeliveryCommitment = includeDeliveryCommitment_example;  // string | If set to true, returns estimated transit times in days. Only for USPS Create Shipment. See also [Pitney Bowes Delivery Guarantee](https://shipping.pitneybowes.com/faqs/delivery-guarantee.html) [Do all USPS services return transit times?](https://shipping.pitneybowes.com/faqs/shipments.html#transit-times-faq) (optional) 

            try
            {
                // This operation creates a shipment and purchases a shipment label.
                Shipment result = apiInstance.CreateShipmentUsingPOST1(xPBTransactionId, shipment, xPBUnifiedErrorStructure, xPBIntegratorCarrierId, xPBShipperRatePlan, xPBShipmentGroupId, xPBShipperCarrierAccountId, includeDeliveryCommitment);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ShipmentApi.CreateShipmentUsingPOST1: " + e.Message );
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
 **xPBTransactionId** | **string**| Required. A unique identifier for the transaction, up to 25 characters. | 
 **shipment** | [**Shipment**](Shipment.md)| request | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]
 **xPBIntegratorCarrierId** | **string**| USPS Only. Negotiated services rate, if applicable. | [optional] 
 **xPBShipperRatePlan** | **string**| USPS Only. Shipper rate plan, if applicable. For more information, see [this FAQ](https://shipping.pitneybowes.com/faqs/rates.html#rate-plans-faq). | [optional] 
 **xPBShipmentGroupId** | **string**|  **[Required parameter for PBPresort service](https://shipping.pitneybowes.com/api/post-shipments-presort.html)**.The job number that represents the agreement between the merchant and PB Presort. This was provided by Pitney Bowes during [merchant onboarding for PB Presort](https://shipping.pitneybowes.com/carriers/pb-presort.html). | [optional] 
 **xPBShipperCarrierAccountId** | **string**| **[Required parameter for PBPresort service](https://shipping.pitneybowes.com/api/post-shipments-presort.html)**. The merchant&#39;s Mailer ID (MID), as provided by Pitney Bowes during merchant onboarding for PB Presort. | [optional] 
 **includeDeliveryCommitment** | **string**| If set to true, returns estimated transit times in days. Only for USPS Create Shipment. See also [Pitney Bowes Delivery Guarantee](https://shipping.pitneybowes.com/faqs/delivery-guarantee.html) [Do all USPS services return transit times?](https://shipping.pitneybowes.com/faqs/shipments.html#transit-times-faq) | [optional] 

### Return type

[**Shipment**](Shipment.md)

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


## ReprintShipmentUsingGET

> Shipment ReprintShipmentUsingGET (string acceptLanguage, string contentType, string shipmentId, string xPBUnifiedErrorStructure = null, Carrier? carrier = null)

reprintShipment

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class ReprintShipmentUsingGETExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ShipmentApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var shipmentId = shipmentId_example;  // string | Required. The shipment ID that was issued when shipment label was generated.
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")
            var carrier = USPS;  // Carrier? |  (optional) 

            try
            {
                // reprintShipment
                Shipment result = apiInstance.ReprintShipmentUsingGET(acceptLanguage, contentType, shipmentId, xPBUnifiedErrorStructure, carrier);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ShipmentApi.ReprintShipmentUsingGET: " + e.Message );
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
 **shipmentId** | **string**| Required. The shipment ID that was issued when shipment label was generated. | 
 **xPBUnifiedErrorStructure** | **string**| Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. | [optional] [default to &quot;true&quot;]
 **carrier** | **Carrier?**|  | [optional] 

### Return type

[**Shipment**](Shipment.md)

### Authorization

[oAuth2ClientCredentials](../README.md#oAuth2ClientCredentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **0** | Error |  -  |

[[Back to top]](#)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RetryShipmentUsingGET

> Shipment RetryShipmentUsingGET (string acceptLanguage, string contentType, string originalTransactionId, string xPBUnifiedErrorStructure = null, Carrier? carrier = null)

retryShipment

### Example

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using Org.OpenAPITools.Api;
using Org.OpenAPITools.Client;
using Org.OpenAPITools.Model;

namespace Example
{
    public class RetryShipmentUsingGETExample
    {
        public static void Main()
        {
            Configuration.Default.BasePath = "https://api-qa.pitneybowes.com/shippingservices";
            // Configure OAuth2 access token for authorization: oAuth2ClientCredentials
            Configuration.Default.AccessToken = "YOUR_ACCESS_TOKEN";

            var apiInstance = new ShipmentApi(Configuration.Default);
            var acceptLanguage = en-US;  // string | This HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (default to "en-US")
            var contentType = application/json;  // string | This mentions the content type getting passed in body of request. (default to "application/json")
            var originalTransactionId = 12344;  // string | 
            var xPBUnifiedErrorStructure = true;  // string | Set this to true to use the standard [error object](https://shipping.pitneybowes.com/reference/error-object.html#standard-error-object) if an error occurs. (optional)  (default to "true")
            var carrier = USPS;  // Carrier? |  (optional) 

            try
            {
                // retryShipment
                Shipment result = apiInstance.RetryShipmentUsingGET(acceptLanguage, contentType, originalTransactionId, xPBUnifiedErrorStructure, carrier);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling ShipmentApi.RetryShipmentUsingGET: " + e.Message );
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
 **carrier** | **Carrier?**|  | [optional] 

### Return type

[**Shipment**](Shipment.md)

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

