# # GetRefundsByUuid200ResponseDataTransaction

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**client_reference_id** | **string** |  | [optional]
**status** | **string** |  | [optional]
**currency** | **string** |  | [optional]
**trace_id** | **string** |  | [optional]
**amount** | **float** |  | [optional]
**transaction_fee** | **float** |  | [optional]
**payout_delay_days** | **int** |  | [optional]
**company_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**addenda** | **string** |  | [optional]
**type** | **string** |  | [optional]
**ach_return_code** | **string** |  | [optional]
**cancel_reason** | **string** |  | [optional]
**declined_reason** | **string** |  | [optional]
**payor** | [**\TheLogicStudio\GrailPay\Model\GetRefunds200ResponseDataRefundsInnerPayee**](GetRefunds200ResponseDataRefundsInnerPayee.md) |  | [optional]
**payee** | [**\TheLogicStudio\GrailPay\Model\GetRefunds200ResponseDataRefundsInnerPayor**](GetRefunds200ResponseDataRefundsInnerPayor.md) |  | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]
**ach_timestamps** | [**\TheLogicStudio\GrailPay\Model\GetRefundsByUuid200ResponseDataTransactionAchTimestamps**](GetRefundsByUuid200ResponseDataTransactionAchTimestamps.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
