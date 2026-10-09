# # PostPayoutsStandaloneRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**entity_uuid** | **string** | UUID of the recipient entity (User or Merchant or Business). The default bank account will be used. |
**amount** | **int** | Payout amount in cents (e.g., 100 &#x3D; $1.00) |
**speed** | **string** | ACH processing speed. Standard &#x3D; 1-2 business days, Fast &#x3D; 2 hours, FedNow &#x3D; immediate (if supported). |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
