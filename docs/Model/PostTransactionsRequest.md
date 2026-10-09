# # PostTransactionsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**payor_uuid** | **string** | UUID of the payor (person user or merchant) under the authenticated vendor. |
**payee_uuid** | **string** | UUID of the payee (person user or merchant) under the authenticated vendor. |
**amount** | **int** | Transaction amount in cents (e.g. 1000 &#x3D; $10.00). Platform default minimum is 10 cents; a higher minimum may apply when configured on the vendor. |
**transaction_fee** | **int** | Optional transaction fee in cents. Must not exceed amount. | [optional]
**client_reference_id** | **string** | Optional client-supplied reference ID. | [optional]
**company_name** | **string** | Optional ACH company name (max 16 characters). | [optional]
**description** | **string** | Optional ACH description (max 10 characters). | [optional]
**addenda** | **string** | Optional ACH addenda (max 80 characters). | [optional]
**source_bank_account_uuid** | **string** | Optional unified bank account UUID for the payor. Omit the key to use the payor default connected account; do not send null. | [optional]
**destination_bank_account_uuid** | **string** | Optional unified bank account UUID for the payee. Omit the key to use the payee default connected account when required; do not send null. | [optional]
**modality** | [**\TheLogicStudio\GrailPay\Model\PostTransactionsRequestModality**](PostTransactionsRequestModality.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
