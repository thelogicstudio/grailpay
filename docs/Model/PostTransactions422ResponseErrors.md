# # PostTransactions422ResponseErrors

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**payor_uuid** | **string[]** |  | [optional]
**payee_uuid** | **string[]** |  | [optional]
**amount** | **string[]** |  | [optional]
**transaction_fee** | **string[]** |  | [optional]
**client_reference_id** | **string[]** |  | [optional]
**company_name** | **string[]** |  | [optional]
**description** | **string[]** |  | [optional]
**addenda** | **string[]** |  | [optional]
**source_bank_account_uuid** | **string[]** |  | [optional]
**destination_bank_account_uuid** | **string[]** |  | [optional]
**modality** | **string[]** |  | [optional]
**modality_transaction** | **string[]** |  | [optional]
**modality_transaction_payment_rail** | **string[]** |  | [optional]
**modality_transaction_speed** | **string[]** |  | [optional]
**modality_payout** | **string[]** | Business-rule failures for the payout modality object. Processor batch vendors always receive the processor message for any modality.payout. Instant/batch message applies only when the payee uses batch payouts and FedNow is requested. | [optional]
**modality_payout_payment_rail** | **string[]** |  | [optional]
**modality_payout_speed** | **string[]** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
