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



// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$aggregator_type = 'aggregator_type_example'; // string | The type of the bank aggregator
$account_uuid = 'account_uuid_example'; // string | The UUID of the bank account

try {
    $result = $apiInstance->deleteBankAccountsByAggregatorTypeByAccountUuid($aggregator_type, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->deleteBankAccountsByAggregatorTypeByAccountUuid: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.grailpay.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*BankAccountsApi* | [**deleteBankAccountsByAggregatorTypeByAccountUuid**](docs/Api/BankAccountsApi.md#deletebankaccountsbyaggregatortypebyaccountuuid) | **DELETE** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid} | Delete a bank account ( STABLE )
*BankAccountsApi* | [**getBankAccountByUserUuid**](docs/Api/BankAccountsApi.md#getbankaccountbyuseruuid) | **GET** /3p/api/v1/bank-account/{user_uuid} | Get bank account details ( STABLE )
*BankAccountsApi* | [**getBankAccountsByAggregatorTypeByAccountUuidHistory**](docs/Api/BankAccountsApi.md#getbankaccountsbyaggregatortypebyaccountuuidhistory) | **GET** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid}/history | Fetch the transaction history for a bank account. ( STABLE )
*BankAccountsApi* | [**getUsersByUuidBankAccounts**](docs/Api/BankAccountsApi.md#getusersbyuuidbankaccounts) | **GET** /3p/api/v2/users/{uuid}/bank-accounts | Get all bank accounts for a user ( STABLE )
*BankAccountsApi* | [**getUsersByUuidBankAccountsByAccountUuidBalance**](docs/Api/BankAccountsApi.md#getusersbyuuidbankaccountsbyaccountuuidbalance) | **GET** /3p/api/v2/users/{uuid}/bank-accounts/{account_uuid}/balance | Fetch the bank account balance ( STABLE )
*BankAccountsApi* | [**postBankAccountBalanceByUserUuid**](docs/Api/BankAccountsApi.md#postbankaccountbalancebyuseruuid) | **POST** /3p/api/v1/bank-account/balance/{user_uuid} | Get balance approval ( STABLE )
*BankAccountsApi* | [**postBankAccountUser**](docs/Api/BankAccountsApi.md#postbankaccountuser) | **POST** /3p/api/v1/bank-account/user | Get User Details by bank account ( STABLE )
*BankAccountsApi* | [**postBankAccountsValidate**](docs/Api/BankAccountsApi.md#postbankaccountsvalidate) | **POST** /3p/api/v2/bank-accounts/validate | Validate bank account and routing number ( STABLE )
*BankAccountsApi* | [**postPeopleByUuidBankAccounts**](docs/Api/BankAccountsApi.md#postpeoplebyuuidbankaccounts) | **POST** /api/v3/people/{uuid}/bank-accounts | Add a new bank account to a person. ( STABLE )
*BankAccountsApi* | [**putBankAccountSwitchDefaultByUserUuid**](docs/Api/BankAccountsApi.md#putbankaccountswitchdefaultbyuseruuid) | **PUT** /3p/api/v1/bank-account/switch/default/{user_uuid} | Switch default bank account ( STABLE )
*BillingApi* | [**getMerchantsByUuidBilling**](docs/Api/BillingApi.md#getmerchantsbyuuidbilling) | **GET** /3p/api/v2/merchants/{uuid}/billing | Get Billing by Merchant User UUID ( STABLE )
*PayoutsApi* | [**getBatchMerchantPayoutsByBatchMerchantPayoutUuid**](docs/Api/PayoutsApi.md#getbatchmerchantpayoutsbybatchmerchantpayoutuuid) | **GET** /3p/api/v2/batch-merchant-payouts/{batch_merchant_payout_uuid} | Get Batch Merchant Payout ( SUNSETTING )
*PayoutsApi* | [**getBatchPayouts**](docs/Api/PayoutsApi.md#getbatchpayouts) | **GET** /3p/api/v2/batch-payouts | Get All Batch Payouts ( SUNSETTING )
*PayoutsApi* | [**getBatchPayoutsBusinessByBusinessUserUuid**](docs/Api/PayoutsApi.md#getbatchpayoutsbusinessbybusinessuseruuid) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid} | List Business Batch Payouts ( STABLE )
*PayoutsApi* | [**getBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid**](docs/Api/PayoutsApi.md#getbatchpayoutsbusinessbybusinessuseruuidbybatchpayoutuuid) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid}/{batch_payout_uuid} | Get Business Batch Payout ( STABLE )
*PayoutsApi* | [**getBatchPayoutsByBatchPayoutUuid**](docs/Api/PayoutsApi.md#getbatchpayoutsbybatchpayoutuuid) | **GET** /3p/api/v2/batch-payouts/{batch_payout_uuid} | Get Batch Payout ( SUNSETTING )
*PayoutsApi* | [**getBatchPayoutsMerchantByMerchantUserUuid**](docs/Api/PayoutsApi.md#getbatchpayoutsmerchantbymerchantuseruuid) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid} | List Merchant Batch Payouts ( STABLE )
*PayoutsApi* | [**getBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid**](docs/Api/PayoutsApi.md#getbatchpayoutsmerchantbymerchantuseruuidbybatchpayoutuuid) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid}/{batch_payout_uuid} | Get Merchant Batch Payout ( STABLE )
*PayoutsApi* | [**getBatchPayoutsPersonByUserUuid**](docs/Api/PayoutsApi.md#getbatchpayoutspersonbyuseruuid) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid} | List Person Batch Payouts ( STABLE )
*PayoutsApi* | [**getBatchPayoutsPersonByUserUuidByBatchPayoutUuid**](docs/Api/PayoutsApi.md#getbatchpayoutspersonbyuseruuidbybatchpayoutuuid) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid}/{batch_payout_uuid} | Get Person Batch Payout ( STABLE )
*PayoutsApi* | [**getProcessorBatchPayouts**](docs/Api/PayoutsApi.md#getprocessorbatchpayouts) | **GET** /3p/api/v2/batch-payouts/processor | List Processor Batch Payouts ( STABLE )
*PayoutsApi* | [**getProcessorBatchPayoutsByBatchPayoutUuid**](docs/Api/PayoutsApi.md#getprocessorbatchpayoutsbybatchpayoutuuid) | **GET** /3p/api/v2/batch-payouts/processor/{batch_payout_uuid} | Get Processor Batch Payout ( STABLE )
*RefundsApi* | [**getBatchRefunds**](docs/Api/RefundsApi.md#getbatchrefunds) | **GET** /3p/api/v2/batch-refunds | Get All Batch Refunds ( STABLE )
*RefundsApi* | [**getBatchRefundsByBatchRefundUuid**](docs/Api/RefundsApi.md#getbatchrefundsbybatchrefunduuid) | **GET** /3p/api/v2/batch-refunds/{batch_refund_uuid} | Get Batch Refund ( STABLE )
*RefundsApi* | [**getRefundsByRefundUuid**](docs/Api/RefundsApi.md#getrefundsbyrefunduuid) | **GET** /3p/api/v1/refunds/{refund_uuid} | Get Refund Details ( Refunds )
*RefundsApi* | [**getTransactionsByTransactionUuidRefunds**](docs/Api/RefundsApi.md#gettransactionsbytransactionuuidrefunds) | **GET** /3p/api/v1/transactions/{transaction_uuid}/refunds | Get Transaction Refunds ( STABLE )
*RefundsApi* | [**postTransactionsByUuidRefund**](docs/Api/RefundsApi.md#posttransactionsbyuuidrefund) | **POST** /3p/api/v1/transactions/{uuid}/refund | Refund a transaction ( STABLE )
*TransactionsApi* | [**deleteTransactionsByUuidCancel**](docs/Api/TransactionsApi.md#deletetransactionsbyuuidcancel) | **DELETE** /api/v3/transactions/{uuid}/cancel | Cancel a transaction in the ACH application ( STABLE )
*TransactionsApi* | [**getTransactions**](docs/Api/TransactionsApi.md#gettransactions) | **GET** /3p/api/v2/transactions | Get Transactions ( STABLE )
*TransactionsApi* | [**getTransactionsByUuid**](docs/Api/TransactionsApi.md#gettransactionsbyuuid) | **GET** /3p/api/v2/transactions/{uuid} | Get Transaction by UUID ( STABLE )
*TransactionsApi* | [**postTransaction**](docs/Api/TransactionsApi.md#posttransaction) | **POST** /3p/api/v1/transaction | Create a new transaction ( STABLE )
*TransactionsApi* | [**postTransactionsByUuidPause**](docs/Api/TransactionsApi.md#posttransactionsbyuuidpause) | **POST** /api/v3/transactions/{uuid}/pause | Pause a transaction in the ACH application ( STABLE )
*TransactionsApi* | [**postTransactionsByUuidResume**](docs/Api/TransactionsApi.md#posttransactionsbyuuidresume) | **POST** /api/v3/transactions/{uuid}/resume | Resume a transaction in the ACH application ( STABLE )
*UsersApi* | [**deleteUsersByUuid**](docs/Api/UsersApi.md#deleteusersbyuuid) | **DELETE** /3p/api/v2/users/{uuid} | Deleting a User ( STABLE )
*UsersApi* | [**getBusinesses**](docs/Api/UsersApi.md#getbusinesses) | **GET** /api/v3/businesses | Get All Businesses ( STABLE )
*UsersApi* | [**getBusinessesByUuid**](docs/Api/UsersApi.md#getbusinessesbyuuid) | **GET** /api/v3/businesses/{uuid} | Get Business ( STABLE )
*UsersApi* | [**getMerchants**](docs/Api/UsersApi.md#getmerchants) | **GET** /api/v3/merchants | Get All Merchants ( STABLE )
*UsersApi* | [**getMerchantsByUuid**](docs/Api/UsersApi.md#getmerchantsbyuuid) | **GET** /api/v3/merchants/{uuid} | Get Merchant ( STABLE )
*UsersApi* | [**getPeople**](docs/Api/UsersApi.md#getpeople) | **GET** /api/v3/people | Get All People ( STABLE )
*UsersApi* | [**getPeopleByUuid**](docs/Api/UsersApi.md#getpeoplebyuuid) | **GET** /api/v3/people/{uuid} | Get Person ( STABLE )
*UsersApi* | [**patchBusinessesByUuid**](docs/Api/UsersApi.md#patchbusinessesbyuuid) | **PATCH** /api/v3/businesses/{uuid} | Update a Business into the ACH application ( STABLE )
*UsersApi* | [**patchMerchantsByUuid**](docs/Api/UsersApi.md#patchmerchantsbyuuid) | **PATCH** /api/v3/merchants/{uuid} | Update a Merchant into the ACH application ( STABLE )
*UsersApi* | [**patchPeopleByUuid**](docs/Api/UsersApi.md#patchpeoplebyuuid) | **PATCH** /api/v3/people/{uuid} | Update a Person into the ACH application ( STABLE )
*UsersApi* | [**postBusinesses**](docs/Api/UsersApi.md#postbusinesses) | **POST** /api/v3/businesses | Onboard a new Business into the ACH application ( STABLE )
*UsersApi* | [**postMerchants**](docs/Api/UsersApi.md#postmerchants) | **POST** /api/v3/merchants | Onboard a new Merchant into the ACH application ( STABLE )
*UsersApi* | [**postPeople**](docs/Api/UsersApi.md#postpeople) | **POST** /api/v3/people | Onboard a new Person into the ACH application ( STABLE )
*UsersApi* | [**postRegisterPerson**](docs/Api/UsersApi.md#postregisterperson) | **POST** /3p/api/v1/register/person | Onboard a new person ( DEPRECATED )
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
- [DeleteBankAccountsByAggregatorTypeByAccountUuid200Response](docs/Model/DeleteBankAccountsByAggregatorTypeByAccountUuid200Response.md)
- [DeleteBankAccountsByAggregatorTypeByAccountUuid403Response](docs/Model/DeleteBankAccountsByAggregatorTypeByAccountUuid403Response.md)
- [DeleteBankAccountsByAggregatorTypeByAccountUuid404Response](docs/Model/DeleteBankAccountsByAggregatorTypeByAccountUuid404Response.md)
- [DeleteTransactionsByUuidCancel200Response](docs/Model/DeleteTransactionsByUuidCancel200Response.md)
- [DeleteUsersByUuid200Response](docs/Model/DeleteUsersByUuid200Response.md)
- [DeleteUsersByUuid202Response](docs/Model/DeleteUsersByUuid202Response.md)
- [DeleteUsersByUuid404Response](docs/Model/DeleteUsersByUuid404Response.md)
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
- [GetBankAccountByUserUuid200Response](docs/Model/GetBankAccountByUserUuid200Response.md)
- [GetBankAccountByUserUuid200ResponseData](docs/Model/GetBankAccountByUserUuid200ResponseData.md)
- [GetBankAccountByUserUuid403Response](docs/Model/GetBankAccountByUserUuid403Response.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200Response](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200Response.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseData](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseData.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataPagination](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataPagination.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInner](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInner.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichment](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichment.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentCategory](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentCategory.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentMerchant](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentMerchant.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentProcessor](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentProcessor.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentRecurrence](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentRecurrence.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentSubcategory](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200ResponseDataTransactionsInnerEnrichmentSubcategory.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory403Response](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory403Response.md)
- [GetBankAccountsByAggregatorTypeByAccountUuidHistory404Response](docs/Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory404Response.md)
- [GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200Response](docs/Model/GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200Response.md)
- [GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200ResponseData](docs/Model/GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200ResponseData.md)
- [GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200ResponseDataTransactionsInner](docs/Model/GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200ResponseDataTransactionsInner.md)
- [GetBatchMerchantPayoutsByBatchMerchantPayoutUuid404Response](docs/Model/GetBatchMerchantPayoutsByBatchMerchantPayoutUuid404Response.md)
- [GetBatchPayouts200Response](docs/Model/GetBatchPayouts200Response.md)
- [GetBatchPayouts200ResponseData](docs/Model/GetBatchPayouts200ResponseData.md)
- [GetBatchPayouts200ResponseDataBatchPayoutsInner](docs/Model/GetBatchPayouts200ResponseDataBatchPayoutsInner.md)
- [GetBatchPayouts200ResponseDataPagination](docs/Model/GetBatchPayouts200ResponseDataPagination.md)
- [GetBatchPayouts400Response](docs/Model/GetBatchPayouts400Response.md)
- [GetBatchPayouts404Response](docs/Model/GetBatchPayouts404Response.md)
- [GetBatchPayoutsBusinessByBusinessUserUuid400Response](docs/Model/GetBatchPayoutsBusinessByBusinessUserUuid400Response.md)
- [GetBatchPayoutsBusinessByBusinessUserUuid404Response](docs/Model/GetBatchPayoutsBusinessByBusinessUserUuid404Response.md)
- [GetBatchPayoutsBusinessByBusinessUserUuid422Response](docs/Model/GetBatchPayoutsBusinessByBusinessUserUuid422Response.md)
- [GetBatchPayoutsBusinessByBusinessUserUuid422ResponseErrors](docs/Model/GetBatchPayoutsBusinessByBusinessUserUuid422ResponseErrors.md)
- [GetBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid404Response](docs/Model/GetBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid404Response.md)
- [GetBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid404ResponseOneOf](docs/Model/GetBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid404ResponseOneOf.md)
- [GetBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid404ResponseOneOf1](docs/Model/GetBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid404ResponseOneOf1.md)
- [GetBatchPayoutsByBatchPayoutUuid200Response](docs/Model/GetBatchPayoutsByBatchPayoutUuid200Response.md)
- [GetBatchPayoutsByBatchPayoutUuid404Response](docs/Model/GetBatchPayoutsByBatchPayoutUuid404Response.md)
- [GetBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid404Response](docs/Model/GetBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid404Response.md)
- [GetBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid404ResponseOneOf](docs/Model/GetBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid404ResponseOneOf.md)
- [GetBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid404ResponseOneOf1](docs/Model/GetBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid404ResponseOneOf1.md)
- [GetBatchPayoutsPersonByUserUuid404Response](docs/Model/GetBatchPayoutsPersonByUserUuid404Response.md)
- [GetBatchPayoutsPersonByUserUuidByBatchPayoutUuid404Response](docs/Model/GetBatchPayoutsPersonByUserUuidByBatchPayoutUuid404Response.md)
- [GetBatchPayoutsPersonByUserUuidByBatchPayoutUuid404ResponseOneOf](docs/Model/GetBatchPayoutsPersonByUserUuidByBatchPayoutUuid404ResponseOneOf.md)
- [GetBatchPayoutsPersonByUserUuidByBatchPayoutUuid404ResponseOneOf1](docs/Model/GetBatchPayoutsPersonByUserUuidByBatchPayoutUuid404ResponseOneOf1.md)
- [GetBatchRefundsByBatchRefundUuid200Response](docs/Model/GetBatchRefundsByBatchRefundUuid200Response.md)
- [GetBusinesses200Response](docs/Model/GetBusinesses200Response.md)
- [GetBusinesses200ResponseData](docs/Model/GetBusinesses200ResponseData.md)
- [GetBusinesses200ResponseDataBusinessesInner](docs/Model/GetBusinesses200ResponseDataBusinessesInner.md)
- [GetBusinesses422Response](docs/Model/GetBusinesses422Response.md)
- [GetBusinesses422ResponseErrors](docs/Model/GetBusinesses422ResponseErrors.md)
- [GetBusinessesByUuid200Response](docs/Model/GetBusinessesByUuid200Response.md)
- [GetBusinessesByUuid403Response](docs/Model/GetBusinessesByUuid403Response.md)
- [GetBusinessesByUuid404Response](docs/Model/GetBusinessesByUuid404Response.md)
- [GetMerchants200Response](docs/Model/GetMerchants200Response.md)
- [GetMerchants200ResponseData](docs/Model/GetMerchants200ResponseData.md)
- [GetMerchants200ResponseDataMerchantsInner](docs/Model/GetMerchants200ResponseDataMerchantsInner.md)
- [GetMerchants422Response](docs/Model/GetMerchants422Response.md)
- [GetMerchants422ResponseErrors](docs/Model/GetMerchants422ResponseErrors.md)
- [GetMerchantsByUuid200Response](docs/Model/GetMerchantsByUuid200Response.md)
- [GetMerchantsByUuid403Response](docs/Model/GetMerchantsByUuid403Response.md)
- [GetMerchantsByUuid404Response](docs/Model/GetMerchantsByUuid404Response.md)
- [GetMerchantsByUuidBilling200Response](docs/Model/GetMerchantsByUuidBilling200Response.md)
- [GetMerchantsByUuidBilling200ResponseData](docs/Model/GetMerchantsByUuidBilling200ResponseData.md)
- [GetMerchantsByUuidBilling200ResponseDataSummaryInner](docs/Model/GetMerchantsByUuidBilling200ResponseDataSummaryInner.md)
- [GetMerchantsByUuidBilling404Response](docs/Model/GetMerchantsByUuidBilling404Response.md)
- [GetPeople200Response](docs/Model/GetPeople200Response.md)
- [GetPeople200ResponseData](docs/Model/GetPeople200ResponseData.md)
- [GetPeople200ResponseDataPeopleInner](docs/Model/GetPeople200ResponseDataPeopleInner.md)
- [GetPeople200ResponseDataPeopleInnerRelations](docs/Model/GetPeople200ResponseDataPeopleInnerRelations.md)
- [GetPeople422Response](docs/Model/GetPeople422Response.md)
- [GetPeople422ResponseErrors](docs/Model/GetPeople422ResponseErrors.md)
- [GetPeopleByUuid200Response](docs/Model/GetPeopleByUuid200Response.md)
- [GetPeopleByUuid200ResponseData](docs/Model/GetPeopleByUuid200ResponseData.md)
- [GetPeopleByUuid200ResponseDataRelations](docs/Model/GetPeopleByUuid200ResponseDataRelations.md)
- [GetPeopleByUuid403Response](docs/Model/GetPeopleByUuid403Response.md)
- [GetProcessorBatchPayoutsByBatchPayoutUuid404Response](docs/Model/GetProcessorBatchPayoutsByBatchPayoutUuid404Response.md)
- [GetRefundsByRefundUuid200Response](docs/Model/GetRefundsByRefundUuid200Response.md)
- [GetRefundsByRefundUuid200ResponseData](docs/Model/GetRefundsByRefundUuid200ResponseData.md)
- [GetRefundsByRefundUuid404Response](docs/Model/GetRefundsByRefundUuid404Response.md)
- [GetTransactions200Response](docs/Model/GetTransactions200Response.md)
- [GetTransactions200ResponseData](docs/Model/GetTransactions200ResponseData.md)
- [GetTransactions400Response](docs/Model/GetTransactions400Response.md)
- [GetTransactionsByTransactionUuidRefunds404Response](docs/Model/GetTransactionsByTransactionUuidRefunds404Response.md)
- [GetTransactionsByUuid200Response](docs/Model/GetTransactionsByUuid200Response.md)
- [GetTransactionsByUuid404Response](docs/Model/GetTransactionsByUuid404Response.md)
- [GetUserDetailsRequest](docs/Model/GetUserDetailsRequest.md)
- [GetUserDetailsRequestBankAccount](docs/Model/GetUserDetailsRequestBankAccount.md)
- [GetUsersByUuidBankAccounts200Response](docs/Model/GetUsersByUuidBankAccounts200Response.md)
- [GetUsersByUuidBankAccounts404Response](docs/Model/GetUsersByUuidBankAccounts404Response.md)
- [GetUsersByUuidBankAccounts404ResponseErrorCode](docs/Model/GetUsersByUuidBankAccounts404ResponseErrorCode.md)
- [GetUsersByUuidBankAccountsByAccountUuidBalance200Response](docs/Model/GetUsersByUuidBankAccountsByAccountUuidBalance200Response.md)
- [GetUsersByUuidBankAccountsByAccountUuidBalance200ResponseData](docs/Model/GetUsersByUuidBankAccountsByAccountUuidBalance200ResponseData.md)
- [GetUsersByUuidBankAccountsByAccountUuidBalance403Response](docs/Model/GetUsersByUuidBankAccountsByAccountUuidBalance403Response.md)
- [GetUsersByUuidBankAccountsByAccountUuidBalance406Response](docs/Model/GetUsersByUuidBankAccountsByAccountUuidBalance406Response.md)
- [GetUsersByUuidBankAccountsByAccountUuidBalance503Response](docs/Model/GetUsersByUuidBankAccountsByAccountUuidBalance503Response.md)
- [GetWebhook200Response](docs/Model/GetWebhook200Response.md)
- [GetWebhook200ResponseDataInner](docs/Model/GetWebhook200ResponseDataInner.md)
- [HistoryDisabled](docs/Model/HistoryDisabled.md)
- [InvalidAggregatorType](docs/Model/InvalidAggregatorType.md)
- [PatchBusinessesByUuid200Response](docs/Model/PatchBusinessesByUuid200Response.md)
- [PatchBusinessesByUuid404Response](docs/Model/PatchBusinessesByUuid404Response.md)
- [PatchMerchantsByUuid200Response](docs/Model/PatchMerchantsByUuid200Response.md)
- [PatchMerchantsByUuid404Response](docs/Model/PatchMerchantsByUuid404Response.md)
- [PatchPeopleByUuid200Response](docs/Model/PatchPeopleByUuid200Response.md)
- [PatchPeopleByUuid404Response](docs/Model/PatchPeopleByUuid404Response.md)
- [PersonResponse](docs/Model/PersonResponse.md)
- [PersonResponseData](docs/Model/PersonResponseData.md)
- [PersonResponseDataAddress](docs/Model/PersonResponseDataAddress.md)
- [PlaidAccount](docs/Model/PlaidAccount.md)
- [PostBankAccountBalanceByUserUuid200Response](docs/Model/PostBankAccountBalanceByUserUuid200Response.md)
- [PostBankAccountBalanceByUserUuid200ResponseData](docs/Model/PostBankAccountBalanceByUserUuid200ResponseData.md)
- [PostBankAccountBalanceByUserUuid403Response](docs/Model/PostBankAccountBalanceByUserUuid403Response.md)
- [PostBankAccountBalanceByUserUuid422Response](docs/Model/PostBankAccountBalanceByUserUuid422Response.md)
- [PostBankAccountBalanceByUserUuid422ResponseErrors](docs/Model/PostBankAccountBalanceByUserUuid422ResponseErrors.md)
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
- [PostPeopleByUuidBankAccounts200Response](docs/Model/PostPeopleByUuidBankAccounts200Response.md)
- [PostPeopleByUuidBankAccounts201Response](docs/Model/PostPeopleByUuidBankAccounts201Response.md)
- [PostPeopleByUuidBankAccounts201ResponseData](docs/Model/PostPeopleByUuidBankAccounts201ResponseData.md)
- [PostPeopleByUuidBankAccounts201ResponseDataAccountIntelligence](docs/Model/PostPeopleByUuidBankAccounts201ResponseDataAccountIntelligence.md)
- [PostPeopleByUuidBankAccounts400Response](docs/Model/PostPeopleByUuidBankAccounts400Response.md)
- [PostPeopleByUuidBankAccounts401Response](docs/Model/PostPeopleByUuidBankAccounts401Response.md)
- [PostPeopleByUuidBankAccounts403Response](docs/Model/PostPeopleByUuidBankAccounts403Response.md)
- [PostPeopleByUuidBankAccounts404Response](docs/Model/PostPeopleByUuidBankAccounts404Response.md)
- [PostPeopleByUuidBankAccounts422Response](docs/Model/PostPeopleByUuidBankAccounts422Response.md)
- [PostPeopleByUuidBankAccounts422ResponseErrors](docs/Model/PostPeopleByUuidBankAccounts422ResponseErrors.md)
- [PostPeopleByUuidBankAccounts500Response](docs/Model/PostPeopleByUuidBankAccounts500Response.md)
- [PostPeopleByUuidBankAccountsRequest](docs/Model/PostPeopleByUuidBankAccountsRequest.md)
- [PostPeopleByUuidBankAccountsRequestActions](docs/Model/PostPeopleByUuidBankAccountsRequestActions.md)
- [PostPeopleByUuidBankAccountsRequestPerson](docs/Model/PostPeopleByUuidBankAccountsRequestPerson.md)
- [PostPeopleRequest](docs/Model/PostPeopleRequest.md)
- [PostRegisterPerson201Response](docs/Model/PostRegisterPerson201Response.md)
- [PostRegisterPerson201ResponseData](docs/Model/PostRegisterPerson201ResponseData.md)
- [PostRegisterPerson400Response](docs/Model/PostRegisterPerson400Response.md)
- [PostRegisterPerson422Response](docs/Model/PostRegisterPerson422Response.md)
- [PostRegisterPerson422ResponseErrors](docs/Model/PostRegisterPerson422ResponseErrors.md)
- [PostTransaction201Response](docs/Model/PostTransaction201Response.md)
- [PostTransaction403Response](docs/Model/PostTransaction403Response.md)
- [PostTransaction404Response](docs/Model/PostTransaction404Response.md)
- [PostTransaction422Response](docs/Model/PostTransaction422Response.md)
- [PostTransactionsByUuidPause200Response](docs/Model/PostTransactionsByUuidPause200Response.md)
- [PostTransactionsByUuidPause404Response](docs/Model/PostTransactionsByUuidPause404Response.md)
- [PostTransactionsByUuidRefund201Response](docs/Model/PostTransactionsByUuidRefund201Response.md)
- [PostTransactionsByUuidRefund404Response](docs/Model/PostTransactionsByUuidRefund404Response.md)
- [PostTransactionsByUuidResume200Response](docs/Model/PostTransactionsByUuidResume200Response.md)
- [PostTransactionsByUuidResume403Response](docs/Model/PostTransactionsByUuidResume403Response.md)
- [PostWebhook201Response](docs/Model/PostWebhook201Response.md)
- [PutBankAccountSwitchDefaultByUserUuid200Response](docs/Model/PutBankAccountSwitchDefaultByUserUuid200Response.md)
- [PutBankAccountSwitchDefaultByUserUuid404Response](docs/Model/PutBankAccountSwitchDefaultByUserUuid404Response.md)
- [PutBankAccountSwitchDefaultByUserUuid409Response](docs/Model/PutBankAccountSwitchDefaultByUserUuid409Response.md)
- [PutBankAccountSwitchDefaultByUserUuid409ResponseErrorCode](docs/Model/PutBankAccountSwitchDefaultByUserUuid409ResponseErrorCode.md)
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
- [V2BankAccountRequest](docs/Model/V2BankAccountRequest.md)
- [V2BankAccountRequestOneOf](docs/Model/V2BankAccountRequestOneOf.md)
- [V2BankAccountRequestOneOf1](docs/Model/V2BankAccountRequestOneOf1.md)
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
### APIToken

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

- API version: `2025.12.1.1`
    - Generator version: `7.17.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
