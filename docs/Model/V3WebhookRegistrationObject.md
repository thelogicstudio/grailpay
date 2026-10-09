# # V3WebhookRegistrationObject

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**url** | **string** | The HTTPS URL that receives webhook events. | [optional]
**secret** | **string** | Signing secret for this registration. Every delivery carries a &#x60;Signature&#x60; header containing the hex-encoded HMAC-SHA256 of the raw JSON request body, keyed with this secret. | [optional]
**entity_type** | **string** | The type of entity that owns the registration. | [optional]
**entity_uuid** | **string** | UUID of the vendor or processor that owns the registration. | [optional]
**is_active** | **bool** | Whether events are delivered to this URL. Set to false automatically after repeated consecutive delivery failures. | [optional]
**failed_counter** | **int** | Number of consecutive events whose delivery attempts all failed. Resets to 0 after a successful delivery. | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
