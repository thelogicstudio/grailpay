# # V2TransactionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**payer_uuid** | **string** |  | [optional]
**payee_uuid** | **string** |  | [optional]
**processor_mid** | **string** |  | [optional]
**batch_payout_id** | **string** |  | [optional]
**transaction_status** | **string** |  | [optional]
**capture_status** | **string** |  | [optional]
**payout_status** | **string** |  | [optional]
**clawback_status** | **string** |  | [optional]
**reverse_payout_status** | **string** |  | [optional]
**currency** | **string** |  | [optional]
**amount** | **int** |  | [optional]
**transaction_fee** | **int** |  | [optional]
**client_reference_id** | **string** |  | [optional]
**payout_delay_days** | **int** |  | [optional]
**company_name** | **string** |  | [optional]
**description** | **string** |  | [optional]
**addenda** | **string** |  | [optional]
**type** | **string** |  | [optional]
**ach_return_code** | **string** |  | [optional]
**cancel_reason** | **string** |  | [optional]
**spped** | **string** |  | [optional]
**failure_code** | **string** |  | [optional]
**failure_reason** | **string** |  | [optional]
**payer_bank_account** | [**\TheLogicStudio\GrailPay\Model\V1TransactionResponsePayerBankAccount**](V1TransactionResponsePayerBankAccount.md) |  | [optional]
**payee_bank_account** | [**\TheLogicStudio\GrailPay\Model\V1TransactionResponsePayeeBankAccount**](V1TransactionResponsePayeeBankAccount.md) |  | [optional]
**payout_ach_return_code** | **\DateTime** |  | [optional]
**payout_failure_reason** | **\DateTime** |  | [optional]
**vendor_name** | **string** |  | [optional]
**trace_ids** | [**\TheLogicStudio\GrailPay\Model\V1TransactionResponseTraceIds**](V1TransactionResponseTraceIds.md) |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**updated_at** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
