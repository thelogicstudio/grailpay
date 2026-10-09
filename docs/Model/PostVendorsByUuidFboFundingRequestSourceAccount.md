# # PostVendorsByUuidFboFundingRequestSourceAccount

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** | UUID of one of the vendor&#39;s funding bank accounts. |
**account_number** | **string** | Account number, 4 to 17 digits. |
**routing_number** | **string** | 9-digit ABA routing number. |
**account_type** | **string** |  |
**account_name** | **string** | Name on the account. Characters other than letters, digits, spaces, hyphens, apostrophes, periods and commas are removed before the account is stored. |
**default** | **bool** | When true, this account also becomes the vendor&#39;s default funding bank account. The vendor&#39;s first funding bank account becomes the default regardless. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
