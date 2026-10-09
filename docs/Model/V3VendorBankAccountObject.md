# # V3VendorBankAccountObject

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  | [optional]
**account_number** | **string** | Account number, masked except for the last four digits. | [optional]
**routing_number** | **string** | Unmasked routing number. | [optional]
**account_name** | **string** | Name on the account, with any characters other than letters, digits, spaces, hyphens, apostrophes, periods and commas removed. | [optional]
**account_type** | **string** |  | [optional]
**institution_name** | **string** | Name of the bank that owns the routing number, looked up when the account was added. Null when the lookup returned no bank name. | [optional]
**client_reference_id** | **string** |  | [optional]
**purposes** | [**\TheLogicStudio\GrailPay\Model\V3VendorBankAccountObjectPurposes**](V3VendorBankAccountObjectPurposes.md) |  | [optional]
**timestamps** | [**\TheLogicStudio\GrailPay\Model\V3TimestampsObject**](V3TimestampsObject.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
