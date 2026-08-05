# # PostBankAccountsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**entity_uuid** | **string** | UUID of the entity (person or business) to add the bank account to. |
**client_reference_id** | **string** | Optional client reference ID for tracking purposes. | [optional]
**billing_processor_mid** | **string** | Optional billing processor MID. | [optional]
**billing_merchant_uuid** | **string** | Optional billing merchant UUID. | [optional]
**person** | [**\TheLogicStudio\GrailPay\Model\PostBankAccountsRequestPerson**](PostBankAccountsRequestPerson.md) |  | [optional]
**bank_account** | [**\TheLogicStudio\GrailPay\Model\PostBankAccountsRequestBankAccount**](PostBankAccountsRequestBankAccount.md) |  |
**actions** | [**\TheLogicStudio\GrailPay\Model\PostBankAccountsRequestActions**](PostBankAccountsRequestActions.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
