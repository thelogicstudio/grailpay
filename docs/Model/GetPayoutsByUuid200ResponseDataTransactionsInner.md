# # GetPayoutsByUuid200ResponseDataTransactionsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**client_reference_id** | **string** |  | [optional]
**status** | **string** |  | [optional]
**currency** | **string** |  | [optional]
**trace_id** | **string** |  | [optional]
**bank_identifiers** | [**\TheLogicStudio\GrailPay\Model\GetPayoutsByUuid200ResponseDataTransactionsInnerBankIdentifiers**](GetPayoutsByUuid200ResponseDataTransactionsInnerBankIdentifiers.md) |  | [optional]
**amount** | **int** | Transaction amount in cents | [optional]
**transaction_fee** | **int** | Transaction fee in cents | [optional]
**payout_delay_days** | **int** |  | [optional]
**company_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**addenda** | **string** |  | [optional]
**type** | **string** |  | [optional]
**ach_return_code** | **string** |  | [optional]
**cancel_reason** | **string** |  | [optional]
**declined_reason** | **string** |  | [optional]
**payor** | [**\TheLogicStudio\GrailPay\Model\GetPayoutsByUuid200ResponseDataTransactionsInnerPayor**](GetPayoutsByUuid200ResponseDataTransactionsInnerPayor.md) |  | [optional]
**payee** | [**\TheLogicStudio\GrailPay\Model\GetPayoutsByUuid200ResponseDataTransactionsInnerPayee**](GetPayoutsByUuid200ResponseDataTransactionsInnerPayee.md) |  | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]
**ach_timestamps** | [**\TheLogicStudio\GrailPay\Model\V3AchTimestampsObject**](V3AchTimestampsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
