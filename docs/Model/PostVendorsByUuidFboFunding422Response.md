# # PostVendorsByUuidFboFunding422Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **bool** |  | [optional]
**message** | **string** | &#x60;No prefunded FBO account is configured for this vendor.&#x60; when the vendor has no prefunded FBO account; &#x60;No funding bank account exists for this vendor.&#x60; when &#x60;source_account&#x60; is omitted and the vendor has no default funding bank account; &#x60;The routing number is not valid.&#x60; when the routing number in &#x60;source_account&#x60; cannot be verified; &#x60;The bank account number or routing number is invalid.&#x60; when the bank rejects the account details in &#x60;source_account&#x60;. | [optional]
**data** | **object** |  | [optional]
**errors** | **object** |  | [optional]
**request_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
