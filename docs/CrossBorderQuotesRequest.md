
# Org.OpenAPITools.Model.CrossBorderQuotesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**QuoteCurrency** | **string** | The currency to return the quote in. Use three uppercase letters, per the ISO currency code (ISO 4217). For example- USD, CAD, or EUR | 
**BasketCurrency** | **string** | The default currency of the basket. Use three uppercase letters, per the ISO currency code (ISO 4217). For example- USD, CAD, or EUR | 
**FromAddress** | [**Address**](Address.md) |  | [optional] 
**ToAddress** | [**Address**](Address.md) |  | 
**BasketItems** | [**List&lt;CrossBorderQuotesRequestBasketItems&gt;**](CrossBorderQuotesRequestBasketItems.md) | The items in the buyer&#39;s shopping basket. | 
**Rates** | [**List&lt;CrossBorderQuotesRequestRates&gt;**](CrossBorderQuotesRequestRates.md) | Specifies the carrier, service, parcel, and other information. In a response, this field also contains the service charges. Importatn- In a request, the rates array can contain only one rates object. | 
**ShipmentOptions** | [**List&lt;CarrierFacilityResponseCarrierFacilityOptions&gt;**](CarrierFacilityResponseCarrierFacilityOptions.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models)
[[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to README]](../README.md)

