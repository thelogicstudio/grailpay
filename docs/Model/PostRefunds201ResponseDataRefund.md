# # PostRefunds201ResponseDataRefund

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**transaction_uuid** | **string** | UUID of the transaction being refunded. | [optional]
**client_reference_id** | **string** |  | [optional]
**status** | **string** |  | [optional]
**amount** | **int** |  | [optional]
**batch** | **object** | Aggregated batch summary when is_batch is true; otherwise null | [optional]
**capture** | [**\TheLogicStudio\GrailPay\Model\PostRefunds201ResponseDataRefundCapture**](PostRefunds201ResponseDataRefundCapture.md) |  | [optional]
**payout** | [**\TheLogicStudio\GrailPay\Model\PostRefunds201ResponseDataRefundPayout**](PostRefunds201ResponseDataRefundPayout.md) |  | [optional]
**payor** | [**\TheLogicStudio\GrailPay\Model\GetRefunds200ResponseDataRefundsInnerPayor**](GetRefunds200ResponseDataRefundsInnerPayor.md) |  | [optional]
**payee** | [**\TheLogicStudio\GrailPay\Model\GetRefunds200ResponseDataRefundsInnerPayee**](GetRefunds200ResponseDataRefundsInnerPayee.md) |  | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
