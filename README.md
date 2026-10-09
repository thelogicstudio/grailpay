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



// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getMe();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getMe: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.grailpay.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountApi* | [**getMe**](docs/Api/AccountApi.md#getme) | **GET** /api/v3/me | Fetch Authenticated Account
*BankAccountsApi* | [**deleteBankAccountsByUuid**](docs/Api/BankAccountsApi.md#deletebankaccountsbyuuid) | **DELETE** /api/v3/bank-accounts/{uuid} | Delete a bank account.
*BankAccountsApi* | [**getBankAccounts**](docs/Api/BankAccountsApi.md#getbankaccounts) | **GET** /api/v3/bank-accounts | List bank accounts for an entity.
*BankAccountsApi* | [**getBankAccountsByUuid**](docs/Api/BankAccountsApi.md#getbankaccountsbyuuid) | **GET** /api/v3/bank-accounts/{uuid} | Show a bank account.
*BankAccountsApi* | [**getBankAccountsByUuidBalance**](docs/Api/BankAccountsApi.md#getbankaccountsbyuuidbalance) | **GET** /api/v3/bank-accounts/{uuid}/balance | Fetch a bank account balance.
*BankAccountsApi* | [**getBankAccountsByUuidHistory**](docs/Api/BankAccountsApi.md#getbankaccountsbyuuidhistory) | **GET** /api/v3/bank-accounts/{uuid}/history | Fetch bank account transaction history.
*BankAccountsApi* | [**getBankAccountsByUuidOwners**](docs/Api/BankAccountsApi.md#getbankaccountsbyuuidowners) | **GET** /api/v3/bank-accounts/{uuid}/owners | Get Bank Account Owners
*BankAccountsApi* | [**postBankAccounts**](docs/Api/BankAccountsApi.md#postbankaccounts) | **POST** /api/v3/bank-accounts | Add a bank account to an entity.
*BankAccountsApi* | [**postBankAccountsValidate**](docs/Api/BankAccountsApi.md#postbankaccountsvalidate) | **POST** /api/v3/bank-accounts/validate | Validate a bank account&#39;s routing and account number.
*BankAccountsApi* | [**postPeopleByUuidBankAccounts**](docs/Api/BankAccountsApi.md#postpeoplebyuuidbankaccounts) | **POST** /api/v3/people/{uuid}/bank-accounts | Add a new bank account to a person.
*BankAccountsApi* | [**putBankAccountsByUuidDefault**](docs/Api/BankAccountsApi.md#putbankaccountsbyuuiddefault) | **PUT** /api/v3/bank-accounts/{uuid}/default | Switch the default bank account.
*BillingApi* | [**getBillingItems**](docs/Api/BillingApi.md#getbillingitems) | **GET** /api/v3/billing/items | Get Billing Items
*BillingApi* | [**getBillingSummary**](docs/Api/BillingApi.md#getbillingsummary) | **GET** /api/v3/billing/summary | Get Billing Summary
*ClawbacksApi* | [**getClawbacks**](docs/Api/ClawbacksApi.md#getclawbacks) | **GET** /api/v3/clawbacks | Get All Clawbacks
*ClawbacksApi* | [**getClawbacksByUuid**](docs/Api/ClawbacksApi.md#getclawbacksbyuuid) | **GET** /api/v3/clawbacks/{uuid} | Get Clawback
*PayoutsApi* | [**getPayouts**](docs/Api/PayoutsApi.md#getpayouts) | **GET** /api/v3/payouts | Get All Payouts
*PayoutsApi* | [**getPayoutsByUuid**](docs/Api/PayoutsApi.md#getpayoutsbyuuid) | **GET** /api/v3/payouts/{uuid} | Get Payout
*PayoutsApi* | [**postPayoutsStandalone**](docs/Api/PayoutsApi.md#postpayoutsstandalone) | **POST** /api/v3/payouts/standalone | Create a standalone payout
*RefundsApi* | [**getRefunds**](docs/Api/RefundsApi.md#getrefunds) | **GET** /api/v3/refunds | Get All Refunds
*RefundsApi* | [**getRefundsByUuid**](docs/Api/RefundsApi.md#getrefundsbyuuid) | **GET** /api/v3/refunds/{uuid} | Get Refund
*RefundsApi* | [**postRefunds**](docs/Api/RefundsApi.md#postrefunds) | **POST** /api/v3/refunds | Create Refund
*ReturnsApi* | [**getReturns**](docs/Api/ReturnsApi.md#getreturns) | **GET** /api/v3/returns | Get All Returns
*ReversePayoutsApi* | [**getReversePayouts**](docs/Api/ReversePayoutsApi.md#getreversepayouts) | **GET** /api/v3/reverse-payouts | Get All Reverse Payouts
*ReversePayoutsApi* | [**getReversePayoutsByUuid**](docs/Api/ReversePayoutsApi.md#getreversepayoutsbyuuid) | **GET** /api/v3/reverse-payouts/{uuid} | Get Reverse Payout
*TransactionsApi* | [**deleteTransactionsByUuidCancel**](docs/Api/TransactionsApi.md#deletetransactionsbyuuidcancel) | **DELETE** /api/v3/transactions/{uuid}/cancel | Cancel a transaction in the ACH application
*TransactionsApi* | [**getTransactions**](docs/Api/TransactionsApi.md#gettransactions) | **GET** /api/v3/transactions | Get All Transactions
*TransactionsApi* | [**getTransactionsByUuid**](docs/Api/TransactionsApi.md#gettransactionsbyuuid) | **GET** /api/v3/transactions/{uuid} | Get Transaction
*TransactionsApi* | [**postTransactions**](docs/Api/TransactionsApi.md#posttransactions) | **POST** /api/v3/transactions | Create Transaction
*TransactionsApi* | [**postTransactionsByUuidPause**](docs/Api/TransactionsApi.md#posttransactionsbyuuidpause) | **POST** /api/v3/transactions/{uuid}/pause | Pause a transaction in the ACH application
*TransactionsApi* | [**postTransactionsByUuidResume**](docs/Api/TransactionsApi.md#posttransactionsbyuuidresume) | **POST** /api/v3/transactions/{uuid}/resume | Resume a transaction in the ACH application
*UsersApi* | [**deletePeopleByUuid**](docs/Api/UsersApi.md#deletepeoplebyuuid) | **DELETE** /api/v3/people/{uuid} | Delete Person
*UsersApi* | [**getBusinesses**](docs/Api/UsersApi.md#getbusinesses) | **GET** /api/v3/businesses | Get All Businesses
*UsersApi* | [**getBusinessesByUuid**](docs/Api/UsersApi.md#getbusinessesbyuuid) | **GET** /api/v3/businesses/{uuid} | Get Business
*UsersApi* | [**getMerchants**](docs/Api/UsersApi.md#getmerchants) | **GET** /api/v3/merchants | Get All Merchants
*UsersApi* | [**getMerchantsByUuid**](docs/Api/UsersApi.md#getmerchantsbyuuid) | **GET** /api/v3/merchants/{uuid} | Get Merchant
*UsersApi* | [**getPeople**](docs/Api/UsersApi.md#getpeople) | **GET** /api/v3/people | Get All People
*UsersApi* | [**getPeopleByUuid**](docs/Api/UsersApi.md#getpeoplebyuuid) | **GET** /api/v3/people/{uuid} | Get Person
*UsersApi* | [**patchBusinessesByUuid**](docs/Api/UsersApi.md#patchbusinessesbyuuid) | **PATCH** /api/v3/businesses/{uuid} | Update a Business into the ACH application
*UsersApi* | [**patchMerchantsByUuid**](docs/Api/UsersApi.md#patchmerchantsbyuuid) | **PATCH** /api/v3/merchants/{uuid} | Update a Merchant into the ACH application
*UsersApi* | [**patchPeopleByUuid**](docs/Api/UsersApi.md#patchpeoplebyuuid) | **PATCH** /api/v3/people/{uuid} | Update a Person into the ACH application
*UsersApi* | [**postBusinesses**](docs/Api/UsersApi.md#postbusinesses) | **POST** /api/v3/businesses | Onboard a new Business into the ACH application
*UsersApi* | [**postMerchants**](docs/Api/UsersApi.md#postmerchants) | **POST** /api/v3/merchants | Onboard a new Merchant into the ACH application
*UsersApi* | [**postMerchantsByUuidActivate**](docs/Api/UsersApi.md#postmerchantsbyuuidactivate) | **POST** /api/v3/merchants/{uuid}/activate | Activate a Merchant
*UsersApi* | [**postMerchantsByUuidDeactivate**](docs/Api/UsersApi.md#postmerchantsbyuuiddeactivate) | **POST** /api/v3/merchants/{uuid}/deactivate | Deactivate a Merchant
*UsersApi* | [**postPeople**](docs/Api/UsersApi.md#postpeople) | **POST** /api/v3/people | Onboard a new Person into the ACH application
*UsersApi* | [**postPeopleKyc**](docs/Api/UsersApi.md#postpeoplekyc) | **POST** /api/v3/people/kyc | Register Person KYC
*VendorsApi* | [**deleteVendorsByUuidBankAccountsByBankAccountUuid**](docs/Api/VendorsApi.md#deletevendorsbyuuidbankaccountsbybankaccountuuid) | **DELETE** /api/v3/vendors/{uuid}/bank-accounts/{bank_account_uuid} | Delete Vendor Bank Account
*VendorsApi* | [**deleteVendorsByUuidFboFundingByFundingUuid**](docs/Api/VendorsApi.md#deletevendorsbyuuidfbofundingbyfundinguuid) | **DELETE** /api/v3/vendors/{uuid}/fbo/funding/{funding_uuid} | Cancel FBO Funding
*VendorsApi* | [**getVendorsByUuid**](docs/Api/VendorsApi.md#getvendorsbyuuid) | **GET** /api/v3/vendors/{uuid} | Fetch Vendor Details
*VendorsApi* | [**getVendorsByUuidBankAccounts**](docs/Api/VendorsApi.md#getvendorsbyuuidbankaccounts) | **GET** /api/v3/vendors/{uuid}/bank-accounts | List Vendor Bank Accounts
*VendorsApi* | [**getVendorsByUuidFbo**](docs/Api/VendorsApi.md#getvendorsbyuuidfbo) | **GET** /api/v3/vendors/{uuid}/fbo | Fetch vendor prefunded FBO account details
*VendorsApi* | [**postVendorsByUuidBankAccounts**](docs/Api/VendorsApi.md#postvendorsbyuuidbankaccounts) | **POST** /api/v3/vendors/{uuid}/bank-accounts | Add Vendor Bank Account
*VendorsApi* | [**postVendorsByUuidFboFunding**](docs/Api/VendorsApi.md#postvendorsbyuuidfbofunding) | **POST** /api/v3/vendors/{uuid}/fbo/funding | Create FBO Funding
*VendorsApi* | [**putVendorsByUuidBankAccountsByBankAccountUuidDefault**](docs/Api/VendorsApi.md#putvendorsbyuuidbankaccountsbybankaccountuuiddefault) | **PUT** /api/v3/vendors/{uuid}/bank-accounts/{bank_account_uuid}/default | Set Default Funding Bank Account
*WebhooksApi* | [**deleteWebhooksByUuid**](docs/Api/WebhooksApi.md#deletewebhooksbyuuid) | **DELETE** /api/v3/webhooks/{uuid} | Delete Webhook
*WebhooksApi* | [**getWebhooks**](docs/Api/WebhooksApi.md#getwebhooks) | **GET** /api/v3/webhooks | Get All Webhooks
*WebhooksApi* | [**getWebhooksByUuid**](docs/Api/WebhooksApi.md#getwebhooksbyuuid) | **GET** /api/v3/webhooks/{uuid} | Get Webhook
*WebhooksApi* | [**postWebhooks**](docs/Api/WebhooksApi.md#postwebhooks) | **POST** /api/v3/webhooks | Register Webhook

## Models

- [BankAccountDetails](docs/Model/BankAccountDetails.md)
- [BankAccountRejected](docs/Model/BankAccountRejected.md)
- [DeleteBankAccountsByUuid200Response](docs/Model/DeleteBankAccountsByUuid200Response.md)
- [DeletePeopleByUuid202Response](docs/Model/DeletePeopleByUuid202Response.md)
- [DeleteVendorsByUuidBankAccountsByBankAccountUuid422Response](docs/Model/DeleteVendorsByUuidBankAccountsByBankAccountUuid422Response.md)
- [DeleteVendorsByUuidFboFundingByFundingUuid200Response](docs/Model/DeleteVendorsByUuidFboFundingByFundingUuid200Response.md)
- [DeleteVendorsByUuidFboFundingByFundingUuid400Response](docs/Model/DeleteVendorsByUuidFboFundingByFundingUuid400Response.md)
- [DeleteVendorsByUuidFboFundingByFundingUuid404Response](docs/Model/DeleteVendorsByUuidFboFundingByFundingUuid404Response.md)
- [DeleteVendorsByUuidFboFundingByFundingUuid422Response](docs/Model/DeleteVendorsByUuidFboFundingByFundingUuid422Response.md)
- [DeleteWebhooksByUuid200Response](docs/Model/DeleteWebhooksByUuid200Response.md)
- [ExistingFundingBankAccount](docs/Model/ExistingFundingBankAccount.md)
- [FundingRejected](docs/Model/FundingRejected.md)
- [GetBankAccounts200Response](docs/Model/GetBankAccounts200Response.md)
- [GetBankAccounts200ResponseData](docs/Model/GetBankAccounts200ResponseData.md)
- [GetBankAccounts200ResponseDataBankAccountsInner](docs/Model/GetBankAccounts200ResponseDataBankAccountsInner.md)
- [GetBankAccounts200ResponseDataBankAccountsInnerTimestamps](docs/Model/GetBankAccounts200ResponseDataBankAccountsInnerTimestamps.md)
- [GetBankAccounts200ResponseDataEntity](docs/Model/GetBankAccounts200ResponseDataEntity.md)
- [GetBankAccounts400Response](docs/Model/GetBankAccounts400Response.md)
- [GetBankAccounts401Response](docs/Model/GetBankAccounts401Response.md)
- [GetBankAccounts422Response](docs/Model/GetBankAccounts422Response.md)
- [GetBankAccounts500Response](docs/Model/GetBankAccounts500Response.md)
- [GetBankAccountsByUuid200Response](docs/Model/GetBankAccountsByUuid200Response.md)
- [GetBankAccountsByUuid200ResponseData](docs/Model/GetBankAccountsByUuid200ResponseData.md)
- [GetBankAccountsByUuid404Response](docs/Model/GetBankAccountsByUuid404Response.md)
- [GetBankAccountsByUuidBalance200Response](docs/Model/GetBankAccountsByUuidBalance200Response.md)
- [GetBankAccountsByUuidBalance200ResponseData](docs/Model/GetBankAccountsByUuidBalance200ResponseData.md)
- [GetBankAccountsByUuidBalance200ResponseDataBalance](docs/Model/GetBankAccountsByUuidBalance200ResponseDataBalance.md)
- [GetBankAccountsByUuidBalance422Response](docs/Model/GetBankAccountsByUuidBalance422Response.md)
- [GetBankAccountsByUuidOwners200Response](docs/Model/GetBankAccountsByUuidOwners200Response.md)
- [GetBankAccountsByUuidOwners200ResponseData](docs/Model/GetBankAccountsByUuidOwners200ResponseData.md)
- [GetBankAccountsByUuidOwners200ResponseDataOwnersInner](docs/Model/GetBankAccountsByUuidOwners200ResponseDataOwnersInner.md)
- [GetBankAccountsByUuidOwners200ResponseDataOwnersInnerAddress](docs/Model/GetBankAccountsByUuidOwners200ResponseDataOwnersInnerAddress.md)
- [GetBankAccountsByUuidOwners200ResponseDataOwnersInnerNames](docs/Model/GetBankAccountsByUuidOwners200ResponseDataOwnersInnerNames.md)
- [GetBankAccountsByUuidOwners403Response](docs/Model/GetBankAccountsByUuidOwners403Response.md)
- [GetBillingItems200Response](docs/Model/GetBillingItems200Response.md)
- [GetBillingItems200ResponseData](docs/Model/GetBillingItems200ResponseData.md)
- [GetBillingItems422Response](docs/Model/GetBillingItems422Response.md)
- [GetBillingSummary200Response](docs/Model/GetBillingSummary200Response.md)
- [GetBillingSummary200ResponseData](docs/Model/GetBillingSummary200ResponseData.md)
- [GetBillingSummary422Response](docs/Model/GetBillingSummary422Response.md)
- [GetBusinesses200Response](docs/Model/GetBusinesses200Response.md)
- [GetBusinesses200ResponseData](docs/Model/GetBusinesses200ResponseData.md)
- [GetBusinesses200ResponseDataBusinessesInner](docs/Model/GetBusinesses200ResponseDataBusinessesInner.md)
- [GetBusinesses422Response](docs/Model/GetBusinesses422Response.md)
- [GetBusinesses422ResponseErrors](docs/Model/GetBusinesses422ResponseErrors.md)
- [GetBusinessesByUuid200Response](docs/Model/GetBusinessesByUuid200Response.md)
- [GetBusinessesByUuid403Response](docs/Model/GetBusinessesByUuid403Response.md)
- [GetBusinessesByUuid404Response](docs/Model/GetBusinessesByUuid404Response.md)
- [GetClawbacks200Response](docs/Model/GetClawbacks200Response.md)
- [GetClawbacks200ResponseData](docs/Model/GetClawbacks200ResponseData.md)
- [GetClawbacks422Response](docs/Model/GetClawbacks422Response.md)
- [GetClawbacks422ResponseErrors](docs/Model/GetClawbacks422ResponseErrors.md)
- [GetClawbacksByUuid200Response](docs/Model/GetClawbacksByUuid200Response.md)
- [GetClawbacksByUuid404Response](docs/Model/GetClawbacksByUuid404Response.md)
- [GetMe200Response](docs/Model/GetMe200Response.md)
- [GetMe200ResponseData](docs/Model/GetMe200ResponseData.md)
- [GetMe200ResponseDataEntity](docs/Model/GetMe200ResponseDataEntity.md)
- [GetMerchants200Response](docs/Model/GetMerchants200Response.md)
- [GetMerchants200ResponseData](docs/Model/GetMerchants200ResponseData.md)
- [GetMerchants200ResponseDataMerchantsInner](docs/Model/GetMerchants200ResponseDataMerchantsInner.md)
- [GetMerchants422Response](docs/Model/GetMerchants422Response.md)
- [GetMerchants422ResponseErrors](docs/Model/GetMerchants422ResponseErrors.md)
- [GetMerchantsByUuid200Response](docs/Model/GetMerchantsByUuid200Response.md)
- [GetMerchantsByUuid403Response](docs/Model/GetMerchantsByUuid403Response.md)
- [GetMerchantsByUuid404Response](docs/Model/GetMerchantsByUuid404Response.md)
- [GetPayouts200Response](docs/Model/GetPayouts200Response.md)
- [GetPayouts200ResponseData](docs/Model/GetPayouts200ResponseData.md)
- [GetPayouts200ResponseDataPayoutsInner](docs/Model/GetPayouts200ResponseDataPayoutsInner.md)
- [GetPayouts422Response](docs/Model/GetPayouts422Response.md)
- [GetPayouts422ResponseErrors](docs/Model/GetPayouts422ResponseErrors.md)
- [GetPayoutsByUuid200Response](docs/Model/GetPayoutsByUuid200Response.md)
- [GetPayoutsByUuid404Response](docs/Model/GetPayoutsByUuid404Response.md)
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
- [GetRefunds200Response](docs/Model/GetRefunds200Response.md)
- [GetRefunds200ResponseData](docs/Model/GetRefunds200ResponseData.md)
- [GetRefunds200ResponseDataRefundsInner](docs/Model/GetRefunds200ResponseDataRefundsInner.md)
- [GetRefunds200ResponseDataRefundsInnerBatch](docs/Model/GetRefunds200ResponseDataRefundsInnerBatch.md)
- [GetRefunds200ResponseDataRefundsInnerCapture](docs/Model/GetRefunds200ResponseDataRefundsInnerCapture.md)
- [GetRefunds200ResponseDataRefundsInnerCaptureBankIdentifiers](docs/Model/GetRefunds200ResponseDataRefundsInnerCaptureBankIdentifiers.md)
- [GetRefunds200ResponseDataRefundsInnerPayee](docs/Model/GetRefunds200ResponseDataRefundsInnerPayee.md)
- [GetRefunds200ResponseDataRefundsInnerPayor](docs/Model/GetRefunds200ResponseDataRefundsInnerPayor.md)
- [GetRefunds200ResponseDataRefundsInnerPayout](docs/Model/GetRefunds200ResponseDataRefundsInnerPayout.md)
- [GetRefunds200ResponseDataRefundsInnerPayoutBankIdentifiers](docs/Model/GetRefunds200ResponseDataRefundsInnerPayoutBankIdentifiers.md)
- [GetRefunds422Response](docs/Model/GetRefunds422Response.md)
- [GetRefunds422ResponseErrors](docs/Model/GetRefunds422ResponseErrors.md)
- [GetRefundsByUuid200Response](docs/Model/GetRefundsByUuid200Response.md)
- [GetRefundsByUuid200ResponseData](docs/Model/GetRefundsByUuid200ResponseData.md)
- [GetRefundsByUuid200ResponseDataRefund](docs/Model/GetRefundsByUuid200ResponseDataRefund.md)
- [GetRefundsByUuid200ResponseDataTransaction](docs/Model/GetRefundsByUuid200ResponseDataTransaction.md)
- [GetRefundsByUuid200ResponseDataTransactionBankIdentifiers](docs/Model/GetRefundsByUuid200ResponseDataTransactionBankIdentifiers.md)
- [GetRefundsByUuid404Response](docs/Model/GetRefundsByUuid404Response.md)
- [GetReturns200Response](docs/Model/GetReturns200Response.md)
- [GetReturns200ResponseData](docs/Model/GetReturns200ResponseData.md)
- [GetReturns422Response](docs/Model/GetReturns422Response.md)
- [GetReturns422ResponseErrors](docs/Model/GetReturns422ResponseErrors.md)
- [GetReversePayouts200Response](docs/Model/GetReversePayouts200Response.md)
- [GetReversePayouts200ResponseData](docs/Model/GetReversePayouts200ResponseData.md)
- [GetReversePayouts422Response](docs/Model/GetReversePayouts422Response.md)
- [GetReversePayouts422ResponseErrors](docs/Model/GetReversePayouts422ResponseErrors.md)
- [GetReversePayoutsByUuid200Response](docs/Model/GetReversePayoutsByUuid200Response.md)
- [GetReversePayoutsByUuid404Response](docs/Model/GetReversePayoutsByUuid404Response.md)
- [GetTransactions200Response](docs/Model/GetTransactions200Response.md)
- [GetTransactions200ResponseData](docs/Model/GetTransactions200ResponseData.md)
- [GetTransactions422Response](docs/Model/GetTransactions422Response.md)
- [GetTransactions422ResponseErrors](docs/Model/GetTransactions422ResponseErrors.md)
- [GetTransactionsByUuid200Response](docs/Model/GetTransactionsByUuid200Response.md)
- [GetTransactionsByUuid200ResponseData](docs/Model/GetTransactionsByUuid200ResponseData.md)
- [GetTransactionsByUuid200ResponseDataClawback](docs/Model/GetTransactionsByUuid200ResponseDataClawback.md)
- [GetTransactionsByUuid200ResponseDataClawbackBankIdentifiers](docs/Model/GetTransactionsByUuid200ResponseDataClawbackBankIdentifiers.md)
- [GetTransactionsByUuid200ResponseDataRefundsInner](docs/Model/GetTransactionsByUuid200ResponseDataRefundsInner.md)
- [GetTransactionsByUuid200ResponseDataRefundsInnerCapture](docs/Model/GetTransactionsByUuid200ResponseDataRefundsInnerCapture.md)
- [GetTransactionsByUuid200ResponseDataRefundsInnerPayee](docs/Model/GetTransactionsByUuid200ResponseDataRefundsInnerPayee.md)
- [GetTransactionsByUuid200ResponseDataRefundsInnerPayor](docs/Model/GetTransactionsByUuid200ResponseDataRefundsInnerPayor.md)
- [GetTransactionsByUuid200ResponseDataRefundsInnerPayout](docs/Model/GetTransactionsByUuid200ResponseDataRefundsInnerPayout.md)
- [GetTransactionsByUuid404Response](docs/Model/GetTransactionsByUuid404Response.md)
- [GetVendorsByUuid200Response](docs/Model/GetVendorsByUuid200Response.md)
- [GetVendorsByUuid200ResponseData](docs/Model/GetVendorsByUuid200ResponseData.md)
- [GetVendorsByUuid200ResponseDataFboAccount](docs/Model/GetVendorsByUuid200ResponseDataFboAccount.md)
- [GetVendorsByUuid404Response](docs/Model/GetVendorsByUuid404Response.md)
- [GetVendorsByUuidBankAccounts200Response](docs/Model/GetVendorsByUuidBankAccounts200Response.md)
- [GetVendorsByUuidFbo200Response](docs/Model/GetVendorsByUuidFbo200Response.md)
- [GetVendorsByUuidFbo200ResponseData](docs/Model/GetVendorsByUuidFbo200ResponseData.md)
- [GetVendorsByUuidFbo422Response](docs/Model/GetVendorsByUuidFbo422Response.md)
- [GetVendorsByUuidFbo503Response](docs/Model/GetVendorsByUuidFbo503Response.md)
- [GetWebhooks200Response](docs/Model/GetWebhooks200Response.md)
- [GetWebhooks200ResponseData](docs/Model/GetWebhooks200ResponseData.md)
- [GetWebhooks422Response](docs/Model/GetWebhooks422Response.md)
- [GetWebhooks422ResponseErrors](docs/Model/GetWebhooks422ResponseErrors.md)
- [GetWebhooksByUuid200Response](docs/Model/GetWebhooksByUuid200Response.md)
- [GetWebhooksByUuid404Response](docs/Model/GetWebhooksByUuid404Response.md)
- [InvalidPathParameter](docs/Model/InvalidPathParameter.md)
- [InvalidProvider](docs/Model/InvalidProvider.md)
- [ManualMode](docs/Model/ManualMode.md)
- [PatchBusinessesByUuid200Response](docs/Model/PatchBusinessesByUuid200Response.md)
- [PatchBusinessesByUuid404Response](docs/Model/PatchBusinessesByUuid404Response.md)
- [PatchMerchantsByUuid200Response](docs/Model/PatchMerchantsByUuid200Response.md)
- [PatchMerchantsByUuid404Response](docs/Model/PatchMerchantsByUuid404Response.md)
- [PatchMerchantsByUuid422Response](docs/Model/PatchMerchantsByUuid422Response.md)
- [PatchMerchantsByUuid422ResponseErrors](docs/Model/PatchMerchantsByUuid422ResponseErrors.md)
- [PatchPeopleByUuid200Response](docs/Model/PatchPeopleByUuid200Response.md)
- [PatchPeopleByUuid404Response](docs/Model/PatchPeopleByUuid404Response.md)
- [PayoutResource](docs/Model/PayoutResource.md)
- [PayoutResourceBankIdentifiers](docs/Model/PayoutResourceBankIdentifiers.md)
- [PayoutResourceEntity](docs/Model/PayoutResourceEntity.md)
- [PayoutResourceFailover](docs/Model/PayoutResourceFailover.md)
- [PayoutResourceFailoverOneOf](docs/Model/PayoutResourceFailoverOneOf.md)
- [PayoutResourceFailoverOneOf1](docs/Model/PayoutResourceFailoverOneOf1.md)
- [PayoutResourceModality](docs/Model/PayoutResourceModality.md)
- [PayoutResourcePayee](docs/Model/PayoutResourcePayee.md)
- [PlaidMode](docs/Model/PlaidMode.md)
- [PostBankAccounts200Response](docs/Model/PostBankAccounts200Response.md)
- [PostBankAccounts200ResponseData](docs/Model/PostBankAccounts200ResponseData.md)
- [PostBankAccounts200ResponseDataEntity](docs/Model/PostBankAccounts200ResponseDataEntity.md)
- [PostBankAccounts201Response](docs/Model/PostBankAccounts201Response.md)
- [PostBankAccounts201ResponseData](docs/Model/PostBankAccounts201ResponseData.md)
- [PostBankAccounts201ResponseDataAccountIntelligence](docs/Model/PostBankAccounts201ResponseDataAccountIntelligence.md)
- [PostBankAccounts201ResponseDataEntity](docs/Model/PostBankAccounts201ResponseDataEntity.md)
- [PostBankAccounts403Response](docs/Model/PostBankAccounts403Response.md)
- [PostBankAccounts422Response](docs/Model/PostBankAccounts422Response.md)
- [PostBankAccounts422ResponseErrors](docs/Model/PostBankAccounts422ResponseErrors.md)
- [PostBankAccountsRequest](docs/Model/PostBankAccountsRequest.md)
- [PostBankAccountsRequestActions](docs/Model/PostBankAccountsRequestActions.md)
- [PostBankAccountsRequestActionsAccountIntelligence](docs/Model/PostBankAccountsRequestActionsAccountIntelligence.md)
- [PostBankAccountsRequestBankAccount](docs/Model/PostBankAccountsRequestBankAccount.md)
- [PostBankAccountsRequestPerson](docs/Model/PostBankAccountsRequestPerson.md)
- [PostBankAccountsValidate200Response](docs/Model/PostBankAccountsValidate200Response.md)
- [PostBankAccountsValidate200ResponseData](docs/Model/PostBankAccountsValidate200ResponseData.md)
- [PostBankAccountsValidate422Response](docs/Model/PostBankAccountsValidate422Response.md)
- [PostBankAccountsValidate422ResponseErrors](docs/Model/PostBankAccountsValidate422ResponseErrors.md)
- [PostBankAccountsValidateRequest](docs/Model/PostBankAccountsValidateRequest.md)
- [PostBankAccountsValidateRequestBankAccount](docs/Model/PostBankAccountsValidateRequestBankAccount.md)
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
- [PostMerchantsByUuidActivate200Response](docs/Model/PostMerchantsByUuidActivate200Response.md)
- [PostMerchantsByUuidDeactivate200Response](docs/Model/PostMerchantsByUuidDeactivate200Response.md)
- [PostMerchantsByUuidDeactivate422Response](docs/Model/PostMerchantsByUuidDeactivate422Response.md)
- [PostMerchantsByUuidDeactivateRequest](docs/Model/PostMerchantsByUuidDeactivateRequest.md)
- [PostMerchantsRequest](docs/Model/PostMerchantsRequest.md)
- [PostPayoutsStandalone201Response](docs/Model/PostPayoutsStandalone201Response.md)
- [PostPayoutsStandalone201ResponseData](docs/Model/PostPayoutsStandalone201ResponseData.md)
- [PostPayoutsStandalone403Response](docs/Model/PostPayoutsStandalone403Response.md)
- [PostPayoutsStandalone422Response](docs/Model/PostPayoutsStandalone422Response.md)
- [PostPayoutsStandalone422ResponseErrors](docs/Model/PostPayoutsStandalone422ResponseErrors.md)
- [PostPayoutsStandaloneRequest](docs/Model/PostPayoutsStandaloneRequest.md)
- [PostPeople201Response](docs/Model/PostPeople201Response.md)
- [PostPeople201ResponseData](docs/Model/PostPeople201ResponseData.md)
- [PostPeople422Response](docs/Model/PostPeople422Response.md)
- [PostPeople422ResponseErrors](docs/Model/PostPeople422ResponseErrors.md)
- [PostPeopleByUuidBankAccounts200Response](docs/Model/PostPeopleByUuidBankAccounts200Response.md)
- [PostPeopleByUuidBankAccounts201Response](docs/Model/PostPeopleByUuidBankAccounts201Response.md)
- [PostPeopleByUuidBankAccounts201ResponseData](docs/Model/PostPeopleByUuidBankAccounts201ResponseData.md)
- [PostPeopleByUuidBankAccounts404Response](docs/Model/PostPeopleByUuidBankAccounts404Response.md)
- [PostPeopleByUuidBankAccounts422Response](docs/Model/PostPeopleByUuidBankAccounts422Response.md)
- [PostPeopleByUuidBankAccounts422ResponseErrors](docs/Model/PostPeopleByUuidBankAccounts422ResponseErrors.md)
- [PostPeopleByUuidBankAccountsRequest](docs/Model/PostPeopleByUuidBankAccountsRequest.md)
- [PostPeopleByUuidBankAccountsRequestActions](docs/Model/PostPeopleByUuidBankAccountsRequestActions.md)
- [PostPeopleByUuidBankAccountsRequestPerson](docs/Model/PostPeopleByUuidBankAccountsRequestPerson.md)
- [PostPeopleKyc200Response](docs/Model/PostPeopleKyc200Response.md)
- [PostPeopleKyc200ResponseData](docs/Model/PostPeopleKyc200ResponseData.md)
- [PostPeopleKyc200ResponseDataComplianceStatus](docs/Model/PostPeopleKyc200ResponseDataComplianceStatus.md)
- [PostPeopleKyc200ResponseDataComplianceStatusKycInner](docs/Model/PostPeopleKyc200ResponseDataComplianceStatusKycInner.md)
- [PostPeopleKyc200ResponseDataKycData](docs/Model/PostPeopleKyc200ResponseDataKycData.md)
- [PostPeopleKyc200ResponseDataKycDataAddress](docs/Model/PostPeopleKyc200ResponseDataKycDataAddress.md)
- [PostPeopleKyc200ResponseDataPerson](docs/Model/PostPeopleKyc200ResponseDataPerson.md)
- [PostPeopleKyc200ResponseDataPersonTimestamps](docs/Model/PostPeopleKyc200ResponseDataPersonTimestamps.md)
- [PostPeopleKyc422Response](docs/Model/PostPeopleKyc422Response.md)
- [PostPeopleKyc422ResponseOneOf](docs/Model/PostPeopleKyc422ResponseOneOf.md)
- [PostPeopleKyc422ResponseOneOf1](docs/Model/PostPeopleKyc422ResponseOneOf1.md)
- [PostPeopleKyc422ResponseOneOfErrors](docs/Model/PostPeopleKyc422ResponseOneOfErrors.md)
- [PostPeopleKycRequest](docs/Model/PostPeopleKycRequest.md)
- [PostPeopleRequest](docs/Model/PostPeopleRequest.md)
- [PostRefunds201Response](docs/Model/PostRefunds201Response.md)
- [PostRefunds201ResponseData](docs/Model/PostRefunds201ResponseData.md)
- [PostRefunds201ResponseDataRefund](docs/Model/PostRefunds201ResponseDataRefund.md)
- [PostRefunds201ResponseDataRefundCapture](docs/Model/PostRefunds201ResponseDataRefundCapture.md)
- [PostRefunds201ResponseDataRefundPayout](docs/Model/PostRefunds201ResponseDataRefundPayout.md)
- [PostRefunds422Response](docs/Model/PostRefunds422Response.md)
- [PostRefunds422ResponseErrors](docs/Model/PostRefunds422ResponseErrors.md)
- [PostRefundsRequest](docs/Model/PostRefundsRequest.md)
- [PostTransactions201Response](docs/Model/PostTransactions201Response.md)
- [PostTransactions201ResponseData](docs/Model/PostTransactions201ResponseData.md)
- [PostTransactions400Response](docs/Model/PostTransactions400Response.md)
- [PostTransactions400ResponseOneOf](docs/Model/PostTransactions400ResponseOneOf.md)
- [PostTransactions422Response](docs/Model/PostTransactions422Response.md)
- [PostTransactions422ResponseErrors](docs/Model/PostTransactions422ResponseErrors.md)
- [PostTransactions503Response](docs/Model/PostTransactions503Response.md)
- [PostTransactionsByUuidPause200Response](docs/Model/PostTransactionsByUuidPause200Response.md)
- [PostTransactionsByUuidResume200Response](docs/Model/PostTransactionsByUuidResume200Response.md)
- [PostTransactionsByUuidResume403Response](docs/Model/PostTransactionsByUuidResume403Response.md)
- [PostTransactionsRequest](docs/Model/PostTransactionsRequest.md)
- [PostTransactionsRequestModality](docs/Model/PostTransactionsRequestModality.md)
- [PostTransactionsRequestModalityPayout](docs/Model/PostTransactionsRequestModalityPayout.md)
- [PostTransactionsRequestModalityTransaction](docs/Model/PostTransactionsRequestModalityTransaction.md)
- [PostVendorsByUuidBankAccounts200Response](docs/Model/PostVendorsByUuidBankAccounts200Response.md)
- [PostVendorsByUuidBankAccounts201Response](docs/Model/PostVendorsByUuidBankAccounts201Response.md)
- [PostVendorsByUuidBankAccounts422Response](docs/Model/PostVendorsByUuidBankAccounts422Response.md)
- [PostVendorsByUuidBankAccountsRequest](docs/Model/PostVendorsByUuidBankAccountsRequest.md)
- [PostVendorsByUuidBankAccountsRequestPurposes](docs/Model/PostVendorsByUuidBankAccountsRequestPurposes.md)
- [PostVendorsByUuidBankAccountsRequestPurposesFunding](docs/Model/PostVendorsByUuidBankAccountsRequestPurposesFunding.md)
- [PostVendorsByUuidFboFunding201Response](docs/Model/PostVendorsByUuidFboFunding201Response.md)
- [PostVendorsByUuidFboFunding201ResponseData](docs/Model/PostVendorsByUuidFboFunding201ResponseData.md)
- [PostVendorsByUuidFboFunding404Response](docs/Model/PostVendorsByUuidFboFunding404Response.md)
- [PostVendorsByUuidFboFunding422Response](docs/Model/PostVendorsByUuidFboFunding422Response.md)
- [PostVendorsByUuidFboFundingRequest](docs/Model/PostVendorsByUuidFboFundingRequest.md)
- [PostVendorsByUuidFboFundingRequestSourceAccount](docs/Model/PostVendorsByUuidFboFundingRequestSourceAccount.md)
- [PostWebhooks201Response](docs/Model/PostWebhooks201Response.md)
- [PostWebhooks403Response](docs/Model/PostWebhooks403Response.md)
- [PostWebhooks422Response](docs/Model/PostWebhooks422Response.md)
- [PostWebhooks422ResponseErrors](docs/Model/PostWebhooks422ResponseErrors.md)
- [PostWebhooksRequest](docs/Model/PostWebhooksRequest.md)
- [ProcessorPayoutResource](docs/Model/ProcessorPayoutResource.md)
- [ProcessorPayoutResourceBankIdentifiers](docs/Model/ProcessorPayoutResourceBankIdentifiers.md)
- [PutBankAccountsByUuidDefault200Response](docs/Model/PutBankAccountsByUuidDefault200Response.md)
- [PutBankAccountsByUuidDefault422Response](docs/Model/PutBankAccountsByUuidDefault422Response.md)
- [PutVendorsByUuidBankAccountsByBankAccountUuidDefault200Response](docs/Model/PutVendorsByUuidBankAccountsByBankAccountUuidDefault200Response.md)
- [PutVendorsByUuidBankAccountsByBankAccountUuidDefault200ResponseData](docs/Model/PutVendorsByUuidBankAccountsByBankAccountUuidDefault200ResponseData.md)
- [PutVendorsByUuidBankAccountsByBankAccountUuidDefault400Response](docs/Model/PutVendorsByUuidBankAccountsByBankAccountUuidDefault400Response.md)
- [PutVendorsByUuidBankAccountsByBankAccountUuidDefault404Response](docs/Model/PutVendorsByUuidBankAccountsByBankAccountUuidDefault404Response.md)
- [QuilttProviderResponse](docs/Model/QuilttProviderResponse.md)
- [QuilttProviderResponseData](docs/Model/QuilttProviderResponseData.md)
- [QuilttProviderResponseDataPagination](docs/Model/QuilttProviderResponseDataPagination.md)
- [QuilttProviderResponseDataTransactionsInner](docs/Model/QuilttProviderResponseDataTransactionsInner.md)
- [ReversePayoutResource](docs/Model/ReversePayoutResource.md)
- [ReversePayoutResourceModality](docs/Model/ReversePayoutResourceModality.md)
- [TransactionResource](docs/Model/TransactionResource.md)
- [TransactionResourceBankIdentifiers](docs/Model/TransactionResourceBankIdentifiers.md)
- [TransactionResourceModality](docs/Model/TransactionResourceModality.md)
- [TransactionResourceModalityPayout](docs/Model/TransactionResourceModalityPayout.md)
- [TransactionResourceModalityTransaction](docs/Model/TransactionResourceModalityTransaction.md)
- [V3AccountIntelligenceRequestObject](docs/Model/V3AccountIntelligenceRequestObject.md)
- [V3AccountIntelligenceThresholdResponse](docs/Model/V3AccountIntelligenceThresholdResponse.md)
- [V3AccountIntelligenceV1Response](docs/Model/V3AccountIntelligenceV1Response.md)
- [V3AccountIntelligenceV2Response](docs/Model/V3AccountIntelligenceV2Response.md)
- [V3AccountIntelligenceV3Response](docs/Model/V3AccountIntelligenceV3Response.md)
- [V3AccountIntelligenceV3ResponseDecisioningInsights](docs/Model/V3AccountIntelligenceV3ResponseDecisioningInsights.md)
- [V3AchTimestampsObject](docs/Model/V3AchTimestampsObject.md)
- [V3AddressObject](docs/Model/V3AddressObject.md)
- [V3BankAccountObject](docs/Model/V3BankAccountObject.md)
- [V3BankAccountResponse](docs/Model/V3BankAccountResponse.md)
- [V3BankAccountValidationError](docs/Model/V3BankAccountValidationError.md)
- [V3BatchPayoutEnvelope](docs/Model/V3BatchPayoutEnvelope.md)
- [V3BeneficialOwnerRequestObject](docs/Model/V3BeneficialOwnerRequestObject.md)
- [V3BeneficialOwnerResponseObject](docs/Model/V3BeneficialOwnerResponseObject.md)
- [V3BeneficialOwnerValidationError](docs/Model/V3BeneficialOwnerValidationError.md)
- [V3BillableEventName](docs/Model/V3BillableEventName.md)
- [V3BillingEntityObject](docs/Model/V3BillingEntityObject.md)
- [V3BillingItemResource](docs/Model/V3BillingItemResource.md)
- [V3BillingItemsValidationErrors](docs/Model/V3BillingItemsValidationErrors.md)
- [V3BillingSourceObject](docs/Model/V3BillingSourceObject.md)
- [V3BillingSummaryEntityObject](docs/Model/V3BillingSummaryEntityObject.md)
- [V3BillingSummaryEventResource](docs/Model/V3BillingSummaryEventResource.md)
- [V3BillingSummaryResource](docs/Model/V3BillingSummaryResource.md)
- [V3BillingSummaryValidationErrors](docs/Model/V3BillingSummaryValidationErrors.md)
- [V3BusinessRelationResponseObject](docs/Model/V3BusinessRelationResponseObject.md)
- [V3BusinessRelationResponseObjectBusiness](docs/Model/V3BusinessRelationResponseObjectBusiness.md)
- [V3BusinessRequestObject](docs/Model/V3BusinessRequestObject.md)
- [V3BusinessResponseObject](docs/Model/V3BusinessResponseObject.md)
- [V3BusinessValidationError](docs/Model/V3BusinessValidationError.md)
- [V3ClawbackDetailEnvelope](docs/Model/V3ClawbackDetailEnvelope.md)
- [V3ClawbackObject](docs/Model/V3ClawbackObject.md)
- [V3ClawbackObjectPayee](docs/Model/V3ClawbackObjectPayee.md)
- [V3ClawbackRelationsObject](docs/Model/V3ClawbackRelationsObject.md)
- [V3DeactivateMerchantValidationErrors](docs/Model/V3DeactivateMerchantValidationErrors.md)
- [V3ErrorIdempotency409](docs/Model/V3ErrorIdempotency409.md)
- [V3ErrorInvalidAcceptHeader400](docs/Model/V3ErrorInvalidAcceptHeader400.md)
- [V3ErrorInvalidParameters400](docs/Model/V3ErrorInvalidParameters400.md)
- [V3ErrorInvalidToken401](docs/Model/V3ErrorInvalidToken401.md)
- [V3ErrorUnauthorized401](docs/Model/V3ErrorUnauthorized401.md)
- [V3ListingPaginationResponse](docs/Model/V3ListingPaginationResponse.md)
- [V3MaskedBankAccountResponse](docs/Model/V3MaskedBankAccountResponse.md)
- [V3MerchantRelationResponseObject](docs/Model/V3MerchantRelationResponseObject.md)
- [V3MerchantRelationResponseObjectMerchant](docs/Model/V3MerchantRelationResponseObjectMerchant.md)
- [V3MerchantRequestObject](docs/Model/V3MerchantRequestObject.md)
- [V3MerchantResponseObject](docs/Model/V3MerchantResponseObject.md)
- [V3MerchantValidationError](docs/Model/V3MerchantValidationError.md)
- [V3OnboardingValidationErrors](docs/Model/V3OnboardingValidationErrors.md)
- [V3PayoutDetailEnvelope](docs/Model/V3PayoutDetailEnvelope.md)
- [V3PayoutRelationsObject](docs/Model/V3PayoutRelationsObject.md)
- [V3PersonRelationResponseObject](docs/Model/V3PersonRelationResponseObject.md)
- [V3PersonRelationResponseObjectPerson](docs/Model/V3PersonRelationResponseObjectPerson.md)
- [V3PersonRequestObject](docs/Model/V3PersonRequestObject.md)
- [V3PersonResponseObject](docs/Model/V3PersonResponseObject.md)
- [V3PersonValidationError](docs/Model/V3PersonValidationError.md)
- [V3RefundAchTimestampsObject](docs/Model/V3RefundAchTimestampsObject.md)
- [V3RelationUuidPointer](docs/Model/V3RelationUuidPointer.md)
- [V3ReturnEntityObject](docs/Model/V3ReturnEntityObject.md)
- [V3ReturnLegEnum](docs/Model/V3ReturnLegEnum.md)
- [V3ReturnPartyObject](docs/Model/V3ReturnPartyObject.md)
- [V3ReturnResource](docs/Model/V3ReturnResource.md)
- [V3ReturnResourceClawback](docs/Model/V3ReturnResourceClawback.md)
- [V3ReturnResourceClawbackBankIdentifiers](docs/Model/V3ReturnResourceClawbackBankIdentifiers.md)
- [V3ReturnResourcePayout](docs/Model/V3ReturnResourcePayout.md)
- [V3ReturnResourcePayoutBankIdentifiers](docs/Model/V3ReturnResourcePayoutBankIdentifiers.md)
- [V3ReturnResourceReversePayout](docs/Model/V3ReturnResourceReversePayout.md)
- [V3ReturnResourceReversePayoutBankIdentifiers](docs/Model/V3ReturnResourceReversePayoutBankIdentifiers.md)
- [V3ReturnResourceTransaction](docs/Model/V3ReturnResourceTransaction.md)
- [V3ReturnResourceTransactionBankIdentifiers](docs/Model/V3ReturnResourceTransactionBankIdentifiers.md)
- [V3ReversePayoutListEnvelope](docs/Model/V3ReversePayoutListEnvelope.md)
- [V3ReversePayoutRelationsObject](docs/Model/V3ReversePayoutRelationsObject.md)
- [V3ReversePayoutShowEnvelope](docs/Model/V3ReversePayoutShowEnvelope.md)
- [V3TimestampsObject](docs/Model/V3TimestampsObject.md)
- [V3VendorBankAccountObject](docs/Model/V3VendorBankAccountObject.md)
- [V3VendorBankAccountObjectPurposes](docs/Model/V3VendorBankAccountObjectPurposes.md)
- [V3VendorBankAccountObjectPurposesFunding](docs/Model/V3VendorBankAccountObjectPurposesFunding.md)
- [V3VendorBankAccountObjectPurposesPayout](docs/Model/V3VendorBankAccountObjectPurposesPayout.md)
- [V3WebhookRegistrationObject](docs/Model/V3WebhookRegistrationObject.md)
- [ValidationErrors](docs/Model/ValidationErrors.md)
- [ValidationErrors1](docs/Model/ValidationErrors1.md)
- [ValidationErrors1Errors](docs/Model/ValidationErrors1Errors.md)
- [ValidationErrors2](docs/Model/ValidationErrors2.md)
- [ValidationErrors2Errors](docs/Model/ValidationErrors2Errors.md)
- [ValidationErrorsErrors](docs/Model/ValidationErrorsErrors.md)

## Authorization

Authentication schemes defined for the API:
### ApiToken

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

- API version: `2026.9.30.1`
    - Generator version: `7.17.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
