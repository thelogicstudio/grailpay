# # PostRefundsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**transaction_uuid** | **string** | UUID of the parent transaction to refund |
**amount** | **int** | Refund amount in cents (must be greater than 0 and not exceed remaining refundable balance) |
**client_reference_id** | **string** | Optional client-supplied reference for tracking | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
