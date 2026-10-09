# # ReversePayoutResource

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**status** | **string** |  | [optional]
**bank_identifiers** | [**\TheLogicStudio\GrailPay\Model\ProcessorPayoutResourceBankIdentifiers**](ProcessorPayoutResourceBankIdentifiers.md) |  | [optional]
**amount** | **int** | Reverse payout amount in cents | [optional]
**sec_code** | **string** |  | [optional]
**ach_return_code** | **string** |  | [optional]
**cancel_reason** | **string** |  | [optional]
**modality** | [**\TheLogicStudio\GrailPay\Model\ReversePayoutResourceModality**](ReversePayoutResourceModality.md) |  | [optional]
**payee** | [**\TheLogicStudio\GrailPay\Model\V3ReturnPartyObject**](V3ReturnPartyObject.md) |  | [optional]
**payor** | [**\TheLogicStudio\GrailPay\Model\V3ReturnPartyObject**](V3ReturnPartyObject.md) |  | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]
**ach_timestamps** | [**\TheLogicStudio\GrailPay\Model\V3AchTimestampsObject**](V3AchTimestampsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
