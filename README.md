# GrailPay PHP SDK

API Documentation for moving funds via ACH using the GrailPay ACH API


## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/GrailPay PHP SDK/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');




$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$aggregator_type = 'aggregator_type_example'; // string | The type of the bank aggregator
$account_uuid = 'account_uuid_example'; // string | The UUID of the bank account

try {
    $result = $apiInstance->deleteBankAccounts($aggregator_type, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->deleteBankAccounts: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.grailpay.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*BankAccountsApi* | [**deleteBankAccounts**](docs/Api/BankAccountsApi.md#deletebankaccounts) | **DELETE** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid} | Delete a bank account ( STABLE )
*BankAccountsApi* | [**getBankAccount**](docs/Api/BankAccountsApi.md#getbankaccount) | **GET** /3p/api/v1/bank-account/{user_uuid} | Get bank account details ( STABLE )
*BankAccountsApi* | [**getBankAccountsHistory**](docs/Api/BankAccountsApi.md#getbankaccountshistory) | **GET** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid}/history | Fetch the transaction history for a bank account. ( STABLE )
*BankAccountsApi* | [**getUsersBankAccounts**](docs/Api/BankAccountsApi.md#getusersbankaccounts) | **GET** /3p/api/v2/users/{uuid}/bank-accounts | Get all bank accounts for a user ( STABLE )
*BankAccountsApi* | [**getUsersBankAccountsBalance**](docs/Api/BankAccountsApi.md#getusersbankaccountsbalance) | **GET** /3p/api/v2/users/{uuid}/bank-accounts/{account_uuid}/balance | Fetch the bank account balance ( STABLE )
*BankAccountsApi* | [**postBankAccountBalance**](docs/Api/BankAccountsApi.md#postbankaccountbalance) | **POST** /3p/api/v1/bank-account/balance/{user_uuid} | Get balance approval ( STABLE )
*BankAccountsApi* | [**postBankAccountUser**](docs/Api/BankAccountsApi.md#postbankaccountuser) | **POST** /3p/api/v1/bank-account/user | Get User Details by bank account ( STABLE )
*BankAccountsApi* | [**postBankAccountsValidate**](docs/Api/BankAccountsApi.md#postbankaccountsvalidate) | **POST** /3p/api/v2/bank-accounts/validate | Validate bank account and routing number ( STABLE )
*BankAccountsApi* | [**postPeopleBankAccounts**](docs/Api/BankAccountsApi.md#postpeoplebankaccounts) | **POST** /api/v3/people/{uuid}/bank-accounts | Onboard a new Person into the ACH application ( STABLE )
*BankAccountsApi* | [**putBankAccountSwitchDefault**](docs/Api/BankAccountsApi.md#putbankaccountswitchdefault) | **PUT** /3p/api/v1/bank-account/switch/default/{user_uuid} | Switch default bank account ( STABLE )
*BillingApi* | [**getMerchantsBilling**](docs/Api/BillingApi.md#getmerchantsbilling) | **GET** /3p/api/v2/merchants/{uuid}/billing | Get Billing by Merchant User UUID ( STABLE )
*PayoutsApi* | [**getBatchPayoutsBusiness**](docs/Api/PayoutsApi.md#getbatchpayoutsbusiness) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid}/{batch_payout_uuid} | Get Business Batch Payout ( STABLE )
*PayoutsApi* | [**getBatchPayoutsMerchant**](docs/Api/PayoutsApi.md#getbatchpayoutsmerchant) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid}/{batch_payout_uuid} | Get Merchant Batch Payout ( STABLE )
*PayoutsApi* | [**getBatchPayoutsPerson**](docs/Api/PayoutsApi.md#getbatchpayoutsperson) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid}/{batch_payout_uuid} | Get Person Batch Payout ( STABLE )
*PayoutsApi* | [**getBatchPayoutsProcessor**](docs/Api/PayoutsApi.md#getbatchpayoutsprocessor) | **GET** /3p/api/v2/batch-payouts/processor/{batch_payout_uuid} | Get Processor Batch Payout ( STABLE )
*RefundsApi* | [**getBatchRefunds**](docs/Api/RefundsApi.md#getbatchrefunds) | **GET** /3p/api/v2/batch-refunds | Get All Batch Refunds ( STABLE )
*RefundsApi* | [**getTransactionsRefunds**](docs/Api/RefundsApi.md#gettransactionsrefunds) | **GET** /3p/api/v1/transactions/{transaction_uuid}/refunds | Get Transaction Refunds ( STABLE )
*RefundsApi* | [**postTransactionsRefund**](docs/Api/RefundsApi.md#posttransactionsrefund) | **POST** /3p/api/v1/transactions/{uuid}/refund | Refund a transaction ( STABLE )
*StableApi* | [**deleteBankAccounts**](docs/Api/StableApi.md#deletebankaccounts) | **DELETE** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid} | Delete a bank account ( STABLE )
*StableApi* | [**deleteTransactions**](docs/Api/StableApi.md#deletetransactions) | **DELETE** /3p/api/v2/transactions/{uuid} | Cancel a transaction ( STABLE )
*StableApi* | [**deleteUsers**](docs/Api/StableApi.md#deleteusers) | **DELETE** /3p/api/v2/users/{uuid} | Deleting a User ( STABLE )
*StableApi* | [**deleteWebhook**](docs/Api/StableApi.md#deletewebhook) | **DELETE** /3p/api/v1/webhook | De-register Webhook ( STABLE )
*StableApi* | [**getBankAccount**](docs/Api/StableApi.md#getbankaccount) | **GET** /3p/api/v1/bank-account/{user_uuid} | Get bank account details ( STABLE )
*StableApi* | [**getBankAccountsHistory**](docs/Api/StableApi.md#getbankaccountshistory) | **GET** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid}/history | Fetch the transaction history for a bank account. ( STABLE )
*StableApi* | [**getBatchPayoutsBusiness**](docs/Api/StableApi.md#getbatchpayoutsbusiness) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid}/{batch_payout_uuid} | Get Business Batch Payout ( STABLE )
*StableApi* | [**getBatchPayoutsMerchant**](docs/Api/StableApi.md#getbatchpayoutsmerchant) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid}/{batch_payout_uuid} | Get Merchant Batch Payout ( STABLE )
*StableApi* | [**getBatchPayoutsPerson**](docs/Api/StableApi.md#getbatchpayoutsperson) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid}/{batch_payout_uuid} | Get Person Batch Payout ( STABLE )
*StableApi* | [**getBatchPayoutsProcessor**](docs/Api/StableApi.md#getbatchpayoutsprocessor) | **GET** /3p/api/v2/batch-payouts/processor/{batch_payout_uuid} | Get Processor Batch Payout ( STABLE )
*StableApi* | [**getBatchRefunds**](docs/Api/StableApi.md#getbatchrefunds) | **GET** /3p/api/v2/batch-refunds | Get All Batch Refunds ( STABLE )
*StableApi* | [**getBusinesses**](docs/Api/StableApi.md#getbusinesses) | **GET** /api/v3/businesses | Get All Businesses ( STABLE )
*StableApi* | [**getMerchants**](docs/Api/StableApi.md#getmerchants) | **GET** /api/v3/merchants | Get All Merchants ( STABLE )
*StableApi* | [**getMerchantsBilling**](docs/Api/StableApi.md#getmerchantsbilling) | **GET** /3p/api/v2/merchants/{uuid}/billing | Get Billing by Merchant User UUID ( STABLE )
*StableApi* | [**getPeople**](docs/Api/StableApi.md#getpeople) | **GET** /api/v3/people | Get All People ( STABLE )
*StableApi* | [**getTransactions**](docs/Api/StableApi.md#gettransactions) | **GET** /3p/api/v2/transactions | Get Transactions ( STABLE )
*StableApi* | [**getTransactionsRefunds**](docs/Api/StableApi.md#gettransactionsrefunds) | **GET** /3p/api/v1/transactions/{transaction_uuid}/refunds | Get Transaction Refunds ( STABLE )
*StableApi* | [**getUsersBankAccounts**](docs/Api/StableApi.md#getusersbankaccounts) | **GET** /3p/api/v2/users/{uuid}/bank-accounts | Get all bank accounts for a user ( STABLE )
*StableApi* | [**getUsersBankAccountsBalance**](docs/Api/StableApi.md#getusersbankaccountsbalance) | **GET** /3p/api/v2/users/{uuid}/bank-accounts/{account_uuid}/balance | Fetch the bank account balance ( STABLE )
*StableApi* | [**getWebhook**](docs/Api/StableApi.md#getwebhook) | **GET** /3p/api/v1/webhook | Get registered webhooks ( STABLE )
*StableApi* | [**patchBusinesses**](docs/Api/StableApi.md#patchbusinesses) | **PATCH** /api/v3/businesses/{uuid} | Update a Business into the ACH application ( STABLE )
*StableApi* | [**patchMerchants**](docs/Api/StableApi.md#patchmerchants) | **PATCH** /api/v3/merchants/{uuid} | Update a Merchant into the ACH application ( STABLE )
*StableApi* | [**patchPeople**](docs/Api/StableApi.md#patchpeople) | **PATCH** /api/v3/people/{uuid} | Update a Person into the ACH application ( STABLE )
*StableApi* | [**postBankAccountBalance**](docs/Api/StableApi.md#postbankaccountbalance) | **POST** /3p/api/v1/bank-account/balance/{user_uuid} | Get balance approval ( STABLE )
*StableApi* | [**postBankAccountUser**](docs/Api/StableApi.md#postbankaccountuser) | **POST** /3p/api/v1/bank-account/user | Get User Details by bank account ( STABLE )
*StableApi* | [**postBankAccountsValidate**](docs/Api/StableApi.md#postbankaccountsvalidate) | **POST** /3p/api/v2/bank-accounts/validate | Validate bank account and routing number ( STABLE )
*StableApi* | [**postBusinesses**](docs/Api/StableApi.md#postbusinesses) | **POST** /api/v3/businesses | Onboard a new Business into the ACH application ( STABLE )
*StableApi* | [**postMerchants**](docs/Api/StableApi.md#postmerchants) | **POST** /api/v3/merchants | Onboard a new Merchant into the ACH application ( STABLE )
*StableApi* | [**postPeople**](docs/Api/StableApi.md#postpeople) | **POST** /api/v3/people | Onboard a new Person into the ACH application ( STABLE )
*StableApi* | [**postPeopleBankAccounts**](docs/Api/StableApi.md#postpeoplebankaccounts) | **POST** /api/v3/people/{uuid}/bank-accounts | Onboard a new Person into the ACH application ( STABLE )
*StableApi* | [**postTransaction**](docs/Api/StableApi.md#posttransaction) | **POST** /3p/api/v1/transaction | Create a new transaction ( STABLE )
*StableApi* | [**postTransactionsRefund**](docs/Api/StableApi.md#posttransactionsrefund) | **POST** /3p/api/v1/transactions/{uuid}/refund | Refund a transaction ( STABLE )
*StableApi* | [**postWebhook**](docs/Api/StableApi.md#postwebhook) | **POST** /3p/api/v1/webhook | Register Webhook ( STABLE )
*StableApi* | [**putBankAccountSwitchDefault**](docs/Api/StableApi.md#putbankaccountswitchdefault) | **PUT** /3p/api/v1/bank-account/switch/default/{user_uuid} | Switch default bank account ( STABLE )
*TransactionsApi* | [**deleteTransactions**](docs/Api/TransactionsApi.md#deletetransactions) | **DELETE** /3p/api/v2/transactions/{uuid} | Cancel a transaction ( STABLE )
*TransactionsApi* | [**getTransactions**](docs/Api/TransactionsApi.md#gettransactions) | **GET** /3p/api/v2/transactions | Get Transactions ( STABLE )
*TransactionsApi* | [**postTransaction**](docs/Api/TransactionsApi.md#posttransaction) | **POST** /3p/api/v1/transaction | Create a new transaction ( STABLE )
*UsersApi* | [**deleteUsers**](docs/Api/UsersApi.md#deleteusers) | **DELETE** /3p/api/v2/users/{uuid} | Deleting a User ( STABLE )
*UsersApi* | [**getBusinesses**](docs/Api/UsersApi.md#getbusinesses) | **GET** /api/v3/businesses | Get All Businesses ( STABLE )
*UsersApi* | [**getMerchants**](docs/Api/UsersApi.md#getmerchants) | **GET** /api/v3/merchants | Get All Merchants ( STABLE )
*UsersApi* | [**getPeople**](docs/Api/UsersApi.md#getpeople) | **GET** /api/v3/people | Get All People ( STABLE )
*UsersApi* | [**patchBusinesses**](docs/Api/UsersApi.md#patchbusinesses) | **PATCH** /api/v3/businesses/{uuid} | Update a Business into the ACH application ( STABLE )
*UsersApi* | [**patchMerchants**](docs/Api/UsersApi.md#patchmerchants) | **PATCH** /api/v3/merchants/{uuid} | Update a Merchant into the ACH application ( STABLE )
*UsersApi* | [**patchPeople**](docs/Api/UsersApi.md#patchpeople) | **PATCH** /api/v3/people/{uuid} | Update a Person into the ACH application ( STABLE )
*UsersApi* | [**postBusinesses**](docs/Api/UsersApi.md#postbusinesses) | **POST** /api/v3/businesses | Onboard a new Business into the ACH application ( STABLE )
*UsersApi* | [**postMerchants**](docs/Api/UsersApi.md#postmerchants) | **POST** /api/v3/merchants | Onboard a new Merchant into the ACH application ( STABLE )
*UsersApi* | [**postPeople**](docs/Api/UsersApi.md#postpeople) | **POST** /api/v3/people | Onboard a new Person into the ACH application ( STABLE )
*WebhooksApi* | [**deleteWebhook**](docs/Api/WebhooksApi.md#deletewebhook) | **DELETE** /3p/api/v1/webhook | De-register Webhook ( STABLE )
*WebhooksApi* | [**getWebhook**](docs/Api/WebhooksApi.md#getwebhook) | **GET** /3p/api/v1/webhook | Get registered webhooks ( STABLE )
*WebhooksApi* | [**postWebhook**](docs/Api/WebhooksApi.md#postwebhook) | **POST** /3p/api/v1/webhook | Register Webhook ( STABLE )

## Models

- [Address](docs/Model/Address.md)
- [BalanceWithAmount](docs/Model/BalanceWithAmount.md)
- [BalanceWithApproval](docs/Model/BalanceWithApproval.md)
- [BankUserNotFound](docs/Model/BankUserNotFound.md)
- [BatchPayoutResponse](docs/Model/BatchPayoutResponse.md)
- [BatchPayoutResponseData](docs/Model/BatchPayoutResponseData.md)
- [BatchPayoutResponseDataPayeeIdInner](docs/Model/BatchPayoutResponseDataPayeeIdInner.md)
- [BatchPayoutResponseDataPayeeIdInnerTransactionsInner](docs/Model/BatchPayoutResponseDataPayeeIdInnerTransactionsInner.md)
- [BatchRefundListResponse](docs/Model/BatchRefundListResponse.md)
- [BatchRefundListResponseData](docs/Model/BatchRefundListResponseData.md)
- [BatchRefundListResponseDataBatchRefundsInner](docs/Model/BatchRefundListResponseDataBatchRefundsInner.md)
- [BatchRefundListResponseDataPagination](docs/Model/BatchRefundListResponseDataPagination.md)
- [BatchRefundNotFound](docs/Model/BatchRefundNotFound.md)
- [BatchRefundResponse](docs/Model/BatchRefundResponse.md)
- [BatchRefundResponseRefundUuidInner](docs/Model/BatchRefundResponseRefundUuidInner.md)
- [Business](docs/Model/Business.md)
- [BusinessIndustryClassification](docs/Model/BusinessIndustryClassification.md)
- [BusinessOwner](docs/Model/BusinessOwner.md)
- [BusinessResponse](docs/Model/BusinessResponse.md)
- [BusinessResponseBusiness](docs/Model/BusinessResponseBusiness.md)
- [BusinessResponseBusinessAddress](docs/Model/BusinessResponseBusinessAddress.md)
- [BusinessResponseBusinessOwnersInner](docs/Model/BusinessResponseBusinessOwnersInner.md)
- [BusinessValidationError](docs/Model/BusinessValidationError.md)
- [CreateTransaction](docs/Model/CreateTransaction.md)
- [CreateTransactionSourceBankAccount](docs/Model/CreateTransactionSourceBankAccount.md)
- [CustomBankAccount](docs/Model/CustomBankAccount.md)
- [DeleteBankAccounts200Response](docs/Model/DeleteBankAccounts200Response.md)
- [DeleteBankAccounts403Response](docs/Model/DeleteBankAccounts403Response.md)
- [DeleteBankAccounts404Response](docs/Model/DeleteBankAccounts404Response.md)
- [DeleteTransactions204Response](docs/Model/DeleteTransactions204Response.md)
- [DeleteTransactions403Response](docs/Model/DeleteTransactions403Response.md)
- [DeleteTransactions404Response](docs/Model/DeleteTransactions404Response.md)
- [DeleteUsers200Response](docs/Model/DeleteUsers200Response.md)
- [DeleteUsers202Response](docs/Model/DeleteUsers202Response.md)
- [DeleteUsers404Response](docs/Model/DeleteUsers404Response.md)
- [DeleteWebhook200Response](docs/Model/DeleteWebhook200Response.md)
- [Error400](docs/Model/Error400.md)
- [Error400InvalidAcceptHeader](docs/Model/Error400InvalidAcceptHeader.md)
- [Error400InvalidPlaidAccount](docs/Model/Error400InvalidPlaidAccount.md)
- [Error400InvalidRoutingNumber](docs/Model/Error400InvalidRoutingNumber.md)
- [Error400UnverifiedPlaidAccount](docs/Model/Error400UnverifiedPlaidAccount.md)
- [Error401InvalidTokenData](docs/Model/Error401InvalidTokenData.md)
- [Error401InvalidTokenStructure](docs/Model/Error401InvalidTokenStructure.md)
- [Error401Unauthorized](docs/Model/Error401Unauthorized.md)
- [Error401UnauthorizedProcessor](docs/Model/Error401UnauthorizedProcessor.md)
- [Error403ForbiddenResponse](docs/Model/Error403ForbiddenResponse.md)
- [Error409](docs/Model/Error409.md)
- [Error500](docs/Model/Error500.md)
- [GetBankAccount200Response](docs/Model/GetBankAccount200Response.md)
- [GetBankAccount200ResponseData](docs/Model/GetBankAccount200ResponseData.md)
- [GetBankAccount403Response](docs/Model/GetBankAccount403Response.md)
- [GetBankAccountsHistory200Response](docs/Model/GetBankAccountsHistory200Response.md)
- [GetBankAccountsHistory200ResponseData](docs/Model/GetBankAccountsHistory200ResponseData.md)
- [GetBankAccountsHistory200ResponseDataPagination](docs/Model/GetBankAccountsHistory200ResponseDataPagination.md)
- [GetBankAccountsHistory200ResponseDataTransactionsInner](docs/Model/GetBankAccountsHistory200ResponseDataTransactionsInner.md)
- [GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichment](docs/Model/GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichment.md)
- [GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentCategory](docs/Model/GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentCategory.md)
- [GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentMerchant](docs/Model/GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentMerchant.md)
- [GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentProcessor](docs/Model/GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentProcessor.md)
- [GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentRecurrence](docs/Model/GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentRecurrence.md)
- [GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentSubcategory](docs/Model/GetBankAccountsHistory200ResponseDataTransactionsInnerEnrichmentSubcategory.md)
- [GetBankAccountsHistory403Response](docs/Model/GetBankAccountsHistory403Response.md)
- [GetBankAccountsHistory404Response](docs/Model/GetBankAccountsHistory404Response.md)
- [GetBatchPayoutsBusiness404Response](docs/Model/GetBatchPayoutsBusiness404Response.md)
- [GetBatchPayoutsBusiness404ResponseOneOf](docs/Model/GetBatchPayoutsBusiness404ResponseOneOf.md)
- [GetBatchPayoutsBusiness404ResponseOneOf1](docs/Model/GetBatchPayoutsBusiness404ResponseOneOf1.md)
- [GetBatchPayoutsMerchant404Response](docs/Model/GetBatchPayoutsMerchant404Response.md)
- [GetBatchPayoutsMerchant404ResponseOneOf](docs/Model/GetBatchPayoutsMerchant404ResponseOneOf.md)
- [GetBatchPayoutsMerchant404ResponseOneOf1](docs/Model/GetBatchPayoutsMerchant404ResponseOneOf1.md)
- [GetBatchPayoutsPerson404Response](docs/Model/GetBatchPayoutsPerson404Response.md)
- [GetBatchPayoutsPerson404ResponseOneOf](docs/Model/GetBatchPayoutsPerson404ResponseOneOf.md)
- [GetBatchPayoutsPerson404ResponseOneOf1](docs/Model/GetBatchPayoutsPerson404ResponseOneOf1.md)
- [GetBatchPayoutsProcessor404Response](docs/Model/GetBatchPayoutsProcessor404Response.md)
- [GetBusinesses200Response](docs/Model/GetBusinesses200Response.md)
- [GetBusinesses200ResponseData](docs/Model/GetBusinesses200ResponseData.md)
- [GetBusinesses200ResponseDataBusinessesInner](docs/Model/GetBusinesses200ResponseDataBusinessesInner.md)
- [GetBusinesses422Response](docs/Model/GetBusinesses422Response.md)
- [GetBusinesses422ResponseErrors](docs/Model/GetBusinesses422ResponseErrors.md)
- [GetMerchants200Response](docs/Model/GetMerchants200Response.md)
- [GetMerchants200ResponseData](docs/Model/GetMerchants200ResponseData.md)
- [GetMerchants200ResponseDataMerchantsInner](docs/Model/GetMerchants200ResponseDataMerchantsInner.md)
- [GetMerchants422Response](docs/Model/GetMerchants422Response.md)
- [GetMerchants422ResponseErrors](docs/Model/GetMerchants422ResponseErrors.md)
- [GetMerchantsBilling200Response](docs/Model/GetMerchantsBilling200Response.md)
- [GetMerchantsBilling200ResponseData](docs/Model/GetMerchantsBilling200ResponseData.md)
- [GetMerchantsBilling200ResponseDataSummaryInner](docs/Model/GetMerchantsBilling200ResponseDataSummaryInner.md)
- [GetMerchantsBilling404Response](docs/Model/GetMerchantsBilling404Response.md)
- [GetPeople200Response](docs/Model/GetPeople200Response.md)
- [GetPeople200ResponseData](docs/Model/GetPeople200ResponseData.md)
- [GetPeople200ResponseDataPeopleInner](docs/Model/GetPeople200ResponseDataPeopleInner.md)
- [GetPeople200ResponseDataPeopleInnerRelations](docs/Model/GetPeople200ResponseDataPeopleInnerRelations.md)
- [GetPeople422Response](docs/Model/GetPeople422Response.md)
- [GetPeople422ResponseErrors](docs/Model/GetPeople422ResponseErrors.md)
- [GetTransactions200Response](docs/Model/GetTransactions200Response.md)
- [GetTransactions200ResponseData](docs/Model/GetTransactions200ResponseData.md)
- [GetTransactions400Response](docs/Model/GetTransactions400Response.md)
- [GetTransactionsRefunds404Response](docs/Model/GetTransactionsRefunds404Response.md)
- [GetUserDetailsRequest](docs/Model/GetUserDetailsRequest.md)
- [GetUserDetailsRequestBankAccount](docs/Model/GetUserDetailsRequestBankAccount.md)
- [GetUsersBankAccounts200Response](docs/Model/GetUsersBankAccounts200Response.md)
- [GetUsersBankAccounts404Response](docs/Model/GetUsersBankAccounts404Response.md)
- [GetUsersBankAccounts404ResponseErrorCode](docs/Model/GetUsersBankAccounts404ResponseErrorCode.md)
- [GetUsersBankAccountsBalance200Response](docs/Model/GetUsersBankAccountsBalance200Response.md)
- [GetUsersBankAccountsBalance200ResponseData](docs/Model/GetUsersBankAccountsBalance200ResponseData.md)
- [GetUsersBankAccountsBalance403Response](docs/Model/GetUsersBankAccountsBalance403Response.md)
- [GetUsersBankAccountsBalance406Response](docs/Model/GetUsersBankAccountsBalance406Response.md)
- [GetUsersBankAccountsBalance503Response](docs/Model/GetUsersBankAccountsBalance503Response.md)
- [GetWebhook200Response](docs/Model/GetWebhook200Response.md)
- [GetWebhook200ResponseDataInner](docs/Model/GetWebhook200ResponseDataInner.md)
- [HistoryDisabled](docs/Model/HistoryDisabled.md)
- [InvalidAggregatorType](docs/Model/InvalidAggregatorType.md)
- [PatchBusinesses200Response](docs/Model/PatchBusinesses200Response.md)
- [PatchBusinesses403Response](docs/Model/PatchBusinesses403Response.md)
- [PatchBusinesses404Response](docs/Model/PatchBusinesses404Response.md)
- [PatchMerchants200Response](docs/Model/PatchMerchants200Response.md)
- [PatchMerchants403Response](docs/Model/PatchMerchants403Response.md)
- [PatchMerchants404Response](docs/Model/PatchMerchants404Response.md)
- [PatchPeople200Response](docs/Model/PatchPeople200Response.md)
- [PatchPeople403Response](docs/Model/PatchPeople403Response.md)
- [PatchPeople404Response](docs/Model/PatchPeople404Response.md)
- [PersonResponse](docs/Model/PersonResponse.md)
- [PersonResponseData](docs/Model/PersonResponseData.md)
- [PersonResponseDataAddress](docs/Model/PersonResponseDataAddress.md)
- [PlaidAccount](docs/Model/PlaidAccount.md)
- [PostBankAccountBalance200Response](docs/Model/PostBankAccountBalance200Response.md)
- [PostBankAccountBalance200ResponseData](docs/Model/PostBankAccountBalance200ResponseData.md)
- [PostBankAccountBalance403Response](docs/Model/PostBankAccountBalance403Response.md)
- [PostBankAccountBalance422Response](docs/Model/PostBankAccountBalance422Response.md)
- [PostBankAccountBalance422ResponseErrors](docs/Model/PostBankAccountBalance422ResponseErrors.md)
- [PostBankAccountUser200Response](docs/Model/PostBankAccountUser200Response.md)
- [PostBankAccountUser200ResponseData](docs/Model/PostBankAccountUser200ResponseData.md)
- [PostBankAccountUser403Response](docs/Model/PostBankAccountUser403Response.md)
- [PostBankAccountUser404Response](docs/Model/PostBankAccountUser404Response.md)
- [PostBankAccountUser404ResponseErrorCode](docs/Model/PostBankAccountUser404ResponseErrorCode.md)
- [PostBankAccountUserRequest](docs/Model/PostBankAccountUserRequest.md)
- [PostBankAccountsValidate200Response](docs/Model/PostBankAccountsValidate200Response.md)
- [PostBankAccountsValidate200ResponseData](docs/Model/PostBankAccountsValidate200ResponseData.md)
- [PostBankAccountsValidate401Response](docs/Model/PostBankAccountsValidate401Response.md)
- [PostBusinesses201Response](docs/Model/PostBusinesses201Response.md)
- [PostBusinesses201ResponseData](docs/Model/PostBusinesses201ResponseData.md)
- [PostBusinesses201ResponseDataRelations](docs/Model/PostBusinesses201ResponseDataRelations.md)
- [PostBusinesses201ResponseDataRelationsPerson](docs/Model/PostBusinesses201ResponseDataRelationsPerson.md)
- [PostBusinesses422Response](docs/Model/PostBusinesses422Response.md)
- [PostBusinesses422ResponseErrors](docs/Model/PostBusinesses422ResponseErrors.md)
- [PostBusinesses500Response](docs/Model/PostBusinesses500Response.md)
- [PostBusinessesRequest](docs/Model/PostBusinessesRequest.md)
- [PostMerchants201Response](docs/Model/PostMerchants201Response.md)
- [PostMerchants201ResponseData](docs/Model/PostMerchants201ResponseData.md)
- [PostMerchants422Response](docs/Model/PostMerchants422Response.md)
- [PostMerchants422ResponseErrors](docs/Model/PostMerchants422ResponseErrors.md)
- [PostMerchantsRequest](docs/Model/PostMerchantsRequest.md)
- [PostPeople201Response](docs/Model/PostPeople201Response.md)
- [PostPeople201ResponseData](docs/Model/PostPeople201ResponseData.md)
- [PostPeople422Response](docs/Model/PostPeople422Response.md)
- [PostPeople422ResponseErrors](docs/Model/PostPeople422ResponseErrors.md)
- [PostPeopleBankAccounts200Response](docs/Model/PostPeopleBankAccounts200Response.md)
- [PostPeopleBankAccounts201Response](docs/Model/PostPeopleBankAccounts201Response.md)
- [PostPeopleBankAccounts201ResponseData](docs/Model/PostPeopleBankAccounts201ResponseData.md)
- [PostPeopleBankAccounts201ResponseDataAccountIntelligence](docs/Model/PostPeopleBankAccounts201ResponseDataAccountIntelligence.md)
- [PostPeopleBankAccounts400Response](docs/Model/PostPeopleBankAccounts400Response.md)
- [PostPeopleBankAccounts401Response](docs/Model/PostPeopleBankAccounts401Response.md)
- [PostPeopleBankAccounts403Response](docs/Model/PostPeopleBankAccounts403Response.md)
- [PostPeopleBankAccounts404Response](docs/Model/PostPeopleBankAccounts404Response.md)
- [PostPeopleBankAccounts422Response](docs/Model/PostPeopleBankAccounts422Response.md)
- [PostPeopleBankAccounts422ResponseErrors](docs/Model/PostPeopleBankAccounts422ResponseErrors.md)
- [PostPeopleBankAccounts500Response](docs/Model/PostPeopleBankAccounts500Response.md)
- [PostPeopleBankAccountsRequest](docs/Model/PostPeopleBankAccountsRequest.md)
- [PostPeopleBankAccountsRequestActions](docs/Model/PostPeopleBankAccountsRequestActions.md)
- [PostPeopleBankAccountsRequestPerson](docs/Model/PostPeopleBankAccountsRequestPerson.md)
- [PostPeopleRequest](docs/Model/PostPeopleRequest.md)
- [PostTransaction201Response](docs/Model/PostTransaction201Response.md)
- [PostTransaction403Response](docs/Model/PostTransaction403Response.md)
- [PostTransaction404Response](docs/Model/PostTransaction404Response.md)
- [PostTransaction422Response](docs/Model/PostTransaction422Response.md)
- [PostTransactionsRefund201Response](docs/Model/PostTransactionsRefund201Response.md)
- [PostTransactionsRefund404Response](docs/Model/PostTransactionsRefund404Response.md)
- [PostWebhook201Response](docs/Model/PostWebhook201Response.md)
- [PutBankAccountSwitchDefault200Response](docs/Model/PutBankAccountSwitchDefault200Response.md)
- [PutBankAccountSwitchDefault404Response](docs/Model/PutBankAccountSwitchDefault404Response.md)
- [PutBankAccountSwitchDefault409Response](docs/Model/PutBankAccountSwitchDefault409Response.md)
- [PutBankAccountSwitchDefault409ResponseErrorCode](docs/Model/PutBankAccountSwitchDefault409ResponseErrorCode.md)
- [Refund](docs/Model/Refund.md)
- [RefundListResponse](docs/Model/RefundListResponse.md)
- [RefundListResponseData](docs/Model/RefundListResponseData.md)
- [StoreAccountValidationRequest](docs/Model/StoreAccountValidationRequest.md)
- [UnableToFetchHistory](docs/Model/UnableToFetchHistory.md)
- [UpdateBusinessKybRequest](docs/Model/UpdateBusinessKybRequest.md)
- [UpdateBusinessKybRequestBusiness](docs/Model/UpdateBusinessKybRequestBusiness.md)
- [UpdateBusinessKybRequestBusinessAddress](docs/Model/UpdateBusinessKybRequestBusinessAddress.md)
- [UpdateBusinessKybRequestBusinessIndustryClassification](docs/Model/UpdateBusinessKybRequestBusinessIndustryClassification.md)
- [UserNotFound](docs/Model/UserNotFound.md)
- [V1AddBankAccountRequest](docs/Model/V1AddBankAccountRequest.md)
- [V1BankAccountListSchema](docs/Model/V1BankAccountListSchema.md)
- [V1BusinessResponse](docs/Model/V1BusinessResponse.md)
- [V1BusinessResponseAddress](docs/Model/V1BusinessResponseAddress.md)
- [V1BusinessResponseBusinessOwners](docs/Model/V1BusinessResponseBusinessOwners.md)
- [V1DeRegisterWebhookRequest](docs/Model/V1DeRegisterWebhookRequest.md)
- [V1GetBankAccountBalanceRequest](docs/Model/V1GetBankAccountBalanceRequest.md)
- [V1RefundTransactionRequest](docs/Model/V1RefundTransactionRequest.md)
- [V1RefundTransactionResponse](docs/Model/V1RefundTransactionResponse.md)
- [V1RegisterBusiness](docs/Model/V1RegisterBusiness.md)
- [V1RegisterBusinessAddress](docs/Model/V1RegisterBusinessAddress.md)
- [V1RegisterBusinessBankAccount](docs/Model/V1RegisterBusinessBankAccount.md)
- [V1RegisterBusinessBankAccountCustom](docs/Model/V1RegisterBusinessBankAccountCustom.md)
- [V1RegisterBusinessBankAccountPlaid](docs/Model/V1RegisterBusinessBankAccountPlaid.md)
- [V1RegisterBusinessBusiness](docs/Model/V1RegisterBusinessBusiness.md)
- [V1RegisterBusinessBusinessOwners](docs/Model/V1RegisterBusinessBusinessOwners.md)
- [V1RegisterPersonRequest](docs/Model/V1RegisterPersonRequest.md)
- [V1RegisterPersonRequestBankAccount](docs/Model/V1RegisterPersonRequestBankAccount.md)
- [V1RegisterPersonRequestBankAccountCustom](docs/Model/V1RegisterPersonRequestBankAccountCustom.md)
- [V1RegisterPersonResponse](docs/Model/V1RegisterPersonResponse.md)
- [V1RegisterWebhookRequest](docs/Model/V1RegisterWebhookRequest.md)
- [V1SwitchBankAccountRequest](docs/Model/V1SwitchBankAccountRequest.md)
- [V1TransactionResponse](docs/Model/V1TransactionResponse.md)
- [V1TransactionResponsePayeeBankAccount](docs/Model/V1TransactionResponsePayeeBankAccount.md)
- [V1TransactionResponsePayerBankAccount](docs/Model/V1TransactionResponsePayerBankAccount.md)
- [V1TransactionResponseTraceIds](docs/Model/V1TransactionResponseTraceIds.md)
- [V1TransactionResponseTraceIdsRefundsInner](docs/Model/V1TransactionResponseTraceIdsRefundsInner.md)
- [V1UpdateBusinessKybRequest](docs/Model/V1UpdateBusinessKybRequest.md)
- [V1UpdateBusinessKybRequestBusiness](docs/Model/V1UpdateBusinessKybRequestBusiness.md)
- [V2AddBankAccountRequest](docs/Model/V2AddBankAccountRequest.md)
- [V2AddBankAccountRequestCustom](docs/Model/V2AddBankAccountRequestCustom.md)
- [V2AddBankAccountRequestPlaid](docs/Model/V2AddBankAccountRequestPlaid.md)
- [V2BankAccountResponse](docs/Model/V2BankAccountResponse.md)
- [V2GetBankAccountBalanceRequest](docs/Model/V2GetBankAccountBalanceRequest.md)
- [V2OnboardBusinessResponse](docs/Model/V2OnboardBusinessResponse.md)
- [V2OnboardBusinessResponseData](docs/Model/V2OnboardBusinessResponseData.md)
- [V2OnboardBusinessResponseDataBankAccount](docs/Model/V2OnboardBusinessResponseDataBankAccount.md)
- [V2OnboardBusinessResponseDataBankAccountRisk](docs/Model/V2OnboardBusinessResponseDataBankAccountRisk.md)
- [V2OnboardBusinessResponseDataBusiness](docs/Model/V2OnboardBusinessResponseDataBusiness.md)
- [V2OnboardBusinessResponseDataBusinessAddress](docs/Model/V2OnboardBusinessResponseDataBusinessAddress.md)
- [V2OnboardBusinessResponseDataBusinessIndustryClassification](docs/Model/V2OnboardBusinessResponseDataBusinessIndustryClassification.md)
- [V2OnboardBusinessResponseDataBusinessOwnersInner](docs/Model/V2OnboardBusinessResponseDataBusinessOwnersInner.md)
- [V2OnboardPersonResponse](docs/Model/V2OnboardPersonResponse.md)
- [V2OnboardPersonResponseData](docs/Model/V2OnboardPersonResponseData.md)
- [V2OnboardPersonResponseDataAddress](docs/Model/V2OnboardPersonResponseDataAddress.md)
- [V2PayeeBatchPayoutResponse](docs/Model/V2PayeeBatchPayoutResponse.md)
- [V2PayeeBatchPayoutResponseData](docs/Model/V2PayeeBatchPayoutResponseData.md)
- [V2PayeeBatchPayoutResponseDataTransactionsInner](docs/Model/V2PayeeBatchPayoutResponseDataTransactionsInner.md)
- [V2PayeeBatchPayoutsResponse](docs/Model/V2PayeeBatchPayoutsResponse.md)
- [V2PayeeBatchPayoutsResponseData](docs/Model/V2PayeeBatchPayoutsResponseData.md)
- [V2PayeeBatchPayoutsResponseDataBatchPayoutsInner](docs/Model/V2PayeeBatchPayoutsResponseDataBatchPayoutsInner.md)
- [V2PayeeBatchPayoutsResponseDataPagination](docs/Model/V2PayeeBatchPayoutsResponseDataPagination.md)
- [V2ProcessorBatchPayoutResponse](docs/Model/V2ProcessorBatchPayoutResponse.md)
- [V2ProcessorBatchPayoutsResponse](docs/Model/V2ProcessorBatchPayoutsResponse.md)
- [V2TransactionResponse](docs/Model/V2TransactionResponse.md)
- [V3AccountIntelligenceRequestObject](docs/Model/V3AccountIntelligenceRequestObject.md)
- [V3AccountIntelligenceThresholdResponse](docs/Model/V3AccountIntelligenceThresholdResponse.md)
- [V3AccountIntelligenceV1Response](docs/Model/V3AccountIntelligenceV1Response.md)
- [V3AccountIntelligenceV2Response](docs/Model/V3AccountIntelligenceV2Response.md)
- [V3AccountIntelligenceV3Response](docs/Model/V3AccountIntelligenceV3Response.md)
- [V3AccountIntelligenceV3ResponseDecisioningInsights](docs/Model/V3AccountIntelligenceV3ResponseDecisioningInsights.md)
- [V3AddressObject](docs/Model/V3AddressObject.md)
- [V3BankAccountObject](docs/Model/V3BankAccountObject.md)
- [V3BankAccountResponse](docs/Model/V3BankAccountResponse.md)
- [V3BeneficialOwnerRequestObject](docs/Model/V3BeneficialOwnerRequestObject.md)
- [V3BeneficialOwnerResponseObject](docs/Model/V3BeneficialOwnerResponseObject.md)
- [V3BeneficialOwnerValidationError](docs/Model/V3BeneficialOwnerValidationError.md)
- [V3BusinessRelationResponseObject](docs/Model/V3BusinessRelationResponseObject.md)
- [V3BusinessRelationResponseObjectBusiness](docs/Model/V3BusinessRelationResponseObjectBusiness.md)
- [V3BusinessRequestObject](docs/Model/V3BusinessRequestObject.md)
- [V3BusinessResponseObject](docs/Model/V3BusinessResponseObject.md)
- [V3BusinessValidationError](docs/Model/V3BusinessValidationError.md)
- [V3ErrorIdempotency409](docs/Model/V3ErrorIdempotency409.md)
- [V3ErrorInvalidAcceptHeader400](docs/Model/V3ErrorInvalidAcceptHeader400.md)
- [V3ErrorInvalidParameters400](docs/Model/V3ErrorInvalidParameters400.md)
- [V3ErrorInvalidToken401](docs/Model/V3ErrorInvalidToken401.md)
- [V3ErrorUnauthorized401](docs/Model/V3ErrorUnauthorized401.md)
- [V3ListingPaginationResponse](docs/Model/V3ListingPaginationResponse.md)
- [V3MerchantRelationResponseObject](docs/Model/V3MerchantRelationResponseObject.md)
- [V3MerchantRelationResponseObjectMerchant](docs/Model/V3MerchantRelationResponseObjectMerchant.md)
- [V3MerchantRequestObject](docs/Model/V3MerchantRequestObject.md)
- [V3MerchantResponseObject](docs/Model/V3MerchantResponseObject.md)
- [V3MerchantValidationError](docs/Model/V3MerchantValidationError.md)
- [V3OnboardingValidationErrors](docs/Model/V3OnboardingValidationErrors.md)
- [V3PersonRelationResponseObject](docs/Model/V3PersonRelationResponseObject.md)
- [V3PersonRelationResponseObjectPerson](docs/Model/V3PersonRelationResponseObjectPerson.md)
- [V3PersonRequestObject](docs/Model/V3PersonRequestObject.md)
- [V3PersonResponseObject](docs/Model/V3PersonResponseObject.md)
- [V3PersonValidationError](docs/Model/V3PersonValidationError.md)
- [V3TimestampsObject](docs/Model/V3TimestampsObject.md)
- [WebhookValidationErrorResponse](docs/Model/WebhookValidationErrorResponse.md)
- [WebhookValidationErrorResponseErrors](docs/Model/WebhookValidationErrorResponseErrors.md)

## Authorization

Authentication schemes defined for the API:
### API_Token

- **Type**: Bearer authentication (Token)

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `2025.11.10.1`
    - Generator version: `7.17.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
