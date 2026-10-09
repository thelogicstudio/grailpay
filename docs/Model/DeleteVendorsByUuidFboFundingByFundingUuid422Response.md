# # DeleteVendorsByUuidFboFundingByFundingUuid422Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **bool** |  | [optional]
**message** | **string** | &#x60;This funding transaction cannot be canceled because it has already been canceled.&#x60;; &#x60;This funding transaction cannot be canceled because it has failed.&#x60;; or &#x60;This funding transaction cannot be canceled because the ACH is already in progress.&#x60; when the ACH has been processed, sent or settled, or canceling it with the bank failed. | [optional]
**data** | **object** |  | [optional]
**errors** | **object** |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
