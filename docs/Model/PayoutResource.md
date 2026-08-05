# # PayoutResource

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**client_reference_id** | **string** |  | [optional]
**entity** | [**\TheLogicStudio\GrailPay\Model\PayoutResourceEntity**](PayoutResourceEntity.md) |  | [optional]
**type** | **string** |  | [optional]
**status** | **string** |  | [optional]
**trace_id** | **string** |  | [optional]
**bank_identifiers** | [**\TheLogicStudio\GrailPay\Model\GetBatchPayouts200ResponseDataBatchPayoutsInnerBankIdentifiers**](GetBatchPayouts200ResponseDataBatchPayoutsInnerBankIdentifiers.md) |  | [optional]
**speed** | **string** |  | [optional]
**amount** | **int** | Payout amount in cents | [optional]
**ach_return_code** | **string** |  | [optional]
**payout_failure_reason** | **string** |  | [optional]
**modality** | [**\TheLogicStudio\GrailPay\Model\PayoutResourceModality**](PayoutResourceModality.md) |  | [optional]
**payee** | [**\TheLogicStudio\GrailPay\Model\PayoutResourcePayee**](PayoutResourcePayee.md) |  | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]
**ach_timestamps** | [**\TheLogicStudio\GrailPay\Model\V3AchTimestampsObject**](V3AchTimestampsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
