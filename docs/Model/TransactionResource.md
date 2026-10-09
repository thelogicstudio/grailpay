# # TransactionResource

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**client_reference_id** | **string** |  | [optional]
**status** | **string** |  | [optional]
**currency** | **string** |  | [optional]
**trace_id** | **string** |  | [optional]
**bank_identifiers** | [**\TheLogicStudio\GrailPay\Model\TransactionResourceBankIdentifiers**](TransactionResourceBankIdentifiers.md) |  | [optional]
**amount** | **int** | Amount in cents (e.g. 1000 &#x3D; $10.00) | [optional]
**transaction_fee** | **int** | Fee in cents | [optional]
**payout_delay_days** | **int** |  | [optional]
**company_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**addenda** | **string** |  | [optional]
**type** | **string** |  | [optional]
**modality** | [**\TheLogicStudio\GrailPay\Model\TransactionResourceModality**](TransactionResourceModality.md) |  | [optional]
**ach_return_code** | **string** |  | [optional]
**cancel_reason** | **string** |  | [optional]
**declined_reason** | **string** |  | [optional]
**payor** | [**\TheLogicStudio\GrailPay\Model\V3ReturnPartyObject**](V3ReturnPartyObject.md) |  | [optional]
**payee** | [**\TheLogicStudio\GrailPay\Model\V3ReturnPartyObject**](V3ReturnPartyObject.md) |  | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]
**ach_timestamps** | [**\TheLogicStudio\GrailPay\Model\V3AchTimestampsObject**](V3AchTimestampsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
