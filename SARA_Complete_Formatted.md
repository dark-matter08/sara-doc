
# SARA V2 API Documentation 

This document describes the available API endpoints in the SARA V2 mobile system.   
The collection is organized into three main categories:

-   **OPERATIONS**: APIs related to transaction flows and financial activities, including **wallet** and **bank** operations.
    
-   **AUTH**: Authentication and security-related endpoints to manage user access, tokens, and session flows.
    
-   **OTHERS**: Additional supporting APIs that don't fall under the main operation or auth flows but are essential to the overall application functionality.

## Available Base URLs (use as `{{baseUrl}}`)
- `http://10.0.102.22`
- `http://172.26.5.28`
- `http://{{preprod}}`
- `https://41.205.80.37`
- `https://{{preprod}}`


## OPERATIONS

### Endpoint: Get Wallet Agent Balance

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms-interne/api/agencyBanking/agentWalletBalance`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Validate Customer

**Method:** `POST`

**URL:** `{{baseUrl}}//agentms-interne/api/walletTransfers/validateCustomer`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "type": "BANK",
    "bankCustomerId": "0026858",
    "phoneNumber": "699991224",
    "idDocumentType": "ID Card",
    "idDocumentNumber": "NID 0026856"
}
```

---


### Endpoint: Get Customer Account By ID

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms/api/agencyBanking/customerAccounts/0542410`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Agent Wallet Balance

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms/api/agencyBanking/agentWalletBalance`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Wallet History

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms-interne/api/agencyBanking/agentWalletHistory`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Query Parameters

| Key | Value |
|-----|-------|
| fromDate | 2022-10-05 |
| toDate | 2022-11-15 |
| page | 0 |
| size | 10 |


---


### Endpoint: Get Bank Account History

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms-interne/api/agencyBanking/agentAccountStatement`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |


### Query Parameters

| Key | Value |
|-----|-------|
| accountNumber | 10005-00001-05424101051-38 |
| fromDate | 2022-06-05 |
| toDate | 2022-07-15 |
| pageNumber | 0 |
| size | 10 |


---


### Endpoint: Get Bank Account Transactions Details

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms-interne/api/agencyBanking/agentAccountStatement`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Query Parameters

| Key | Value |
|-----|-------|
| accountNumber | 10005-00001-05424101051-38 |
| fromDate | 2022-07-09 |
| toDate | 2022-07-19 |
| pageNumber | 0 |
| size | 1000 |


---


### Endpoint: Get Bank Account Details

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms-interneapi/agencyBanking/accountDetails/10005-00001-05424101051-38`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Wallet Cash In

**Method:** `POST`

**URL:** `{{baseUrl}}/agentms-interne/api/walletTransfers/walletCashIn`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
  "bankCustomerId": "0542410",
  "debtorBankAccountNumber": "10005-00001-05424101051-38",
  "amount": "500",
  "reason": "Wallet Cash In",
  "mfaToken": "123456",
  "currencyName": "XAF",
  "fee": "10",
  "feeId": "101",
  "type": "CASH_IN"
}
```

---


### Endpoint: Get Wallet Customer Details

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms-interne/api/walletTransfers/walletCustomerDetails/655807870`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Bank Customer Details

**Method:** `POST`

**URL:** `{{baseUrl}}/agentms-interne/api/walletTransfers/validateCustomer`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
"accountType": "BANK", 
"bankCustomerId": "0026358",
"phoneNumber": "678105456", 
"idDocumentType": "ID Card", 
"idDocumentNumber": "1234567"
}
```

---


### Endpoint: Get Agent Bank Accounts

**Method:** `GET`

**URL:** `{{baseUrl}}/agentms-interne/api/agencyBanking/customerAccounts/0026358`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Banks

**Method:** `GET`

**URL:** `{{baseUrl}}/bam-interne/common/bank`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Wallet Account

**Method:** `GET`

**URL:** `{{baseUrl}}/wallet-management/api/wallets/balance`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Proceed Cash In

**Method:** `POST`

**URL:** `{{baseUrl}}/wallet-management-interne/api/wallets/topUp/afriland`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "bankAccount": "10005-00056-07605371051-12",
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "description": "Top up through bank",
    "walletTopupReq": {
        "countryCode": "CM",
        "currencyCode": "XAF",
        "amount": 10000
    },
    "complementInfoDTO": {
        "paymentMethodCode": "WALLET_CASH_IN_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "CASHIN_SM",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANK_ACCOUNT"
    },
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    }
}
```

---


### Endpoint: Proceed Cash Out

**Method:** `POST`

**URL:** `{{baseUrl}}/wallet-management-interne/api/transactions/cashOut`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "toAccountNumber": "10005-00056-07605371051-12",
    "beneficiaryName": "N/A",
    "amount": "500",
    "currencyCode": "XAF",
    "reason": "Sample",
    "mfaToken": "111111",
    "complementInfoDTO": {
        "paymentMethodCode": "WALLET_CASH_IN_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "CASHIN_SM",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANK_ACCOUNT"
    },
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "feeIds": [
            183
        ],
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    }
}
```

---


### Endpoint: Export Bank Transactions

**Method:** `POST`

**URL:** `{{baseUrl}}{{BANK_MANAGEMENT}}/txn/export`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Bank Transactions

**Method:** `GET`

**URL:** `{{baseUrl}}{{BANK_MANAGEMENT}}/txn/search`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Bank Account Details

**Method:** `GET`

**URL:** `{{baseUrl}}{{BANK_MANAGEMENT}}/account/${bnkAccNbr}`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Customer Bank Account Details

**Method:** `GET`

**URL:** `{{baseUrl}}{{BANK_MANAGEMENT}}/customer/accounts/${bnkAccNbr}`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Bank Operation Check

**Method:** `POST`

**URL:** `{{baseUrl}}{{BANK_MANAGEMENT}}/account/doCheckConditionsBeforeTranfer`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Calculate Fees

**Method:** `POST`

**URL:** `{{baseUrl}}{{FINTECH_BASE_PATH}}/rest/mobilebanking/doCalculateFees`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Bank Accounts

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/bank-accounts`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Banks

**Method:** `GET`

**URL:** `{{baseUrl}}/bam/common/bank`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Check Bank Account

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/bank-accounts-check`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
[{
  "accountKey": "key",
  "accountNo": "123456",
  "bankCode": "001",
  "bankName": "BankName",
  "branchCode": "001",
  "currency": { "id": 1 },
  "iban": "IBAN123",
  "swift": "SWIFT"
}]
```

---


### Endpoint: Add Bank Account

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/bank-accounts`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
[{
  "accountKey": "key",
  "accountNo": "123456",
  "bankCode": "001",
  "bankName": "BankName",
  "branchCode": "001",
  "currency": { "id": 1 },
  "iban": "IBAN123",
  "swift": "SWIFT",
  "mfa": "mfa-token"
}]
```

---


### Endpoint: Remove Bank Account

**Method:** `DELETE`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/bank-accounts/:account_id`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Generate QR Code

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/qr-code/generate/gimac`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "isStatic": true,
  "posId": 1,
  "merchantWalletId": "walletId",
  "merchantId": "merchantId",
  "merchantName": "Merchant Name",
  "merchantCategoryCode": "1234",
  "merchantCity": "City",
  "intent": "PURCHASE",
  "payloadFormatIndicator": "01"
}
```

---


### Endpoint: Send Collected Money

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/wallet/transactions/send-collected-money`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "amount": "1000",
  "currencyCode": "USD",
  "reason": "Settlement",
  "debitorEntityId": 1,
  "debitorWalletUserType": "MERCHANT",
  "complementInfoDTO": {
    "paymentMethodCode": "BANK",
    "channel": "WEB",
    "userCode": "user1",
    "paymentMode": "TRANSFER"
  }
}
```

---


### Endpoint: Get Wallet Balance

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/wallet/balance`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "userType": "MERCHANT",
  "userId": "merchantId"
}
```

---


### Endpoint: Get Wallet Transactions List

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/wallet/history`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "page": 1,
  "size": 10,
  "currencyCodes": "USD",
  "fromDate": "2023-01-01",
  "toDate": "2023-01-31",
  "userType": "MERCHANT",
  "userId": "merchantId"
}
```

---


### Endpoint: List Bulk Payment

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/bulk-payment`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "unknown": "value"
}
```

---


### Endpoint: Pending First Approval

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/bulk-payment/pending-first-approval`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "unknown": "value"
}
```

---


### Endpoint: Pending Second Approval

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/bulk-payment/pending-second-approval`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "unknown": "value"
}
```

---


## **1. Wallet To Wallet**

### Endpoint: Proceed Wallet to Wallet

**Method:** `POST`

**URL:** `http://{Base URL}/wallet-management/api/transactions/walletToWallet`

### Request Body


```json

{
    "beneficiaryUserType": "CUSTOMER",
    "beneficiaryMobileNumber": "237693942919",
    "amount": 100,
    "currencyCode": "XAF",
    "reason": "TR",
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 1.1,
        "feeIds": [
            181
        ],
        "fixedAmount": 0.0,
        "percentageAmount": 1.1,
        "debitSenderAmount": 1.1,
        "ttaAmount": 0.0,
        "status": true,
        "message": "FOND SUFFISANT"
    },
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "complementInfoDTO": {
        "paymentMethodCode": "WALLET_TO_WALLET_TRANSFER_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "WALLET_TO_WALLET_TRANSF",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "WALLET"
    }
}

```


---

## **2. Bank to bank Transfer**

### Endpoint: Bank To Bank Transfer

**Method:** `POST`

**URL:** `http://{Base URL}/bam/txn`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "sender": "10005-00001-38110090602-06",
    "receiverName": "BOULA FANKEM FRANKLIN",
    "receiver": "10005-00001-06139111051-05",
    "amount": 1000,
    "currency": "XAF",
    "description": "TR",
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "feeIds": [
            183
        ],
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    },
    "type": "DEPOSIT",
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "complementInfoDTO": {
        "paymentMethodCode": "BANK_TO_BANK_TRANSFER_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "BANK_ACCOUNT_TO_BANK_ACCOUNT_TRANSF",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANK_ACCOUNT"
    }
}

```


---

## **3. Recurrent bank transfer**

### Endpoint: Recurent Bank Transfer

**Method:** `POST`

**URL:** `http://{Base URL}/bam/txn/recurrentTransfer`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "sender": "10005-00001-05452011051-50",
    "receiverName": "Test beneficiare EKOBAN",
    "receiver": "10029-26011-01318253101-34",
    "amount": 1000,
    "currency": "XAF",
    "description": "TR",
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "feeIds": [
            183
        ],
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    },
    "type": "DEPOSIT",
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "complementInfoDTO": {
        "paymentMethodCode": "BANK_TO_BANK_TRANSFER_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "BANKACC_TO_BANKACC_RECCUR_TRANSF",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANKACC_TO_BANKACC_RECCUR_TRANSF"
    }
}

```


---
## 4. Request Money

### Endpoint: Get Received Request Money List

**Method:** `GET`

**URL:** `http://{Base URL}/wallet-management/api/requestMoney/received?page=0&size=10`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| page | 0 |
| size | 10 |




---

### Endpoint: Get send request list

**Method:** `GET`

**URL:** `http://{Base URL}/wallet-management/api/requestMoney/requested?page=1&size=10`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| page | 1 |
| size | 10 |




---

### Endpoint: Pay Request

**Method:** `POST`

**URL:** `http://{Base URL}/wallet-management-interne/api/transactions/payRequestMoney`


**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
     "requestCode": "7bb2838f-db12-492a-bea8-88c5fd66359a",
        "reason": "Paying to request money",
        "mfaToken": 378835,
        "commission": {"currencyCode": "XAF", "transactionFee": 0.0, "feeId": null, "feeIds": [150], "fixedAmount": 0.0, "percentageAmount": 0.0, "debitSenderAmount": 0.0, "ttaAmount": 0.0, "status": true, "message": "FOND SUFFISANT"}
}

```


---

## 5. Transactions history

### a. Endpoint: Get All Wallet Transactions

**Method:** `GET`

**URL:** `http://{Base URL}/wallet-management/api/wallets/history?currencyCodes=XAF&fromDate=2023-12-04&toDate=2023-12-14&page=0&size=10`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| currencyCodes | XAF |
| fromDate | 2023-12-04 |
| toDate | 2023-12-14 |
| page | 0 |
| size | 10 |


### b. Endpoint: Get Bank Transactions History

**Method:** `GET`

**URL:** `http://{Base URL}/bam/account/statement/10005-00056-07605371051-12/2023-02-26/2023-03-08/0/100`

**Purpose:** This endpoint likely retrieves resource details.

## **6. GIMAC**

### Endpoint: Check Gimac Availability

**Method:** `GET`

**URL:** `http://{Base URL}/gimac/api/gimac/authentication/doCheckAvailabilityOfGimac`

**Purpose:** This endpoint likely retrieves resource details.

## **7. Cash In**

**Method:** `POST`

**URL:** `http://{Base URL}/wallet-management-interne/api/wallets/topUp/afriland`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "bankAccount": "10005-00056-07605371051-12",
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "description": "Top up through bank",
    "walletTopupReq": {
        "countryCode": "CM",
        "currencyCode": "XAF",
        "amount": 10000
    },
    "complementInfoDTO": {
        "paymentMethodCode": "WALLET_CASH_IN_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "CASHIN_SM",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANK_ACCOUNT"
    },
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    }
}

```


---

## **8. Cash Out**

**Method:** `POST`

**URL:** `http://{Base URL}/wallet-management-interne/api/transactions/cashOut`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "toAccountNumber": "10005-00056-07605371051-12",
    "beneficiaryName": "N/A",
    "amount": "500",
    "currencyCode": "XAF",
    "reason": "Sample",
    "mfaToken": "111111",
    "complementInfoDTO": {
        "paymentMethodCode": "WALLET_CASH_IN_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "CASHIN_SM",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANK_ACCOUNT"
    },
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "feeIds": [
            183
        ],
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    }
}

```


---

## **9. Service Payment**

### a. Endpoint: Get List Of Services

**Method:** `GET`

**URL:** `http://{Base URL}/wallet-management/api/payment/services`

**Purpose:** This endpoint likely retrieves a list of resources.





---

### b. Endpoint: Get List of merchants

**Method:** `GET`

**URL:** `http://{Base URL}/wallet-management/api/payment/merchants`

**Purpose:** This endpoint likely retrieves a list of resources.





---

## **10. Merchant payment**

### a. Endpoint: Get Merchant Details

**Method:** `POST`

**URL:** `http://{Base URL}/saramerchant-interne/customer/transactions/before-payment-by-code`

**Purpose:** This endpoint likely retrieves resource details.




### Request Body


```json

{
    "merchantCode" :"237654842744"
}

```


---

### b. Endpoint: Pay Merchant

**Method:** `POST`

**URL:** `http://{Base URL}/saramerchant-interne/customer/transactions/payment-by-code`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "debtorUserType": "CUSTOMER", 
    "debtorUserId": "655807870", 
    "currencyCode": "XAF", 
    "amount": 250, 
    "reason": "te", 
    "merchantCode": "2376548427", 
    "mfaToken": 111111
}

```

## 11. Calculate fee 

**Method:** `POST`

**URL:** `http://{Base URL}/sarabackofficeservices-interne/customer/transactionFees/calculate`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "paymentMethodCode": "WALLET_CASH_IN_METHOD", 

### Endpoint: Login Agent

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management-interne/api-public/auth/login`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "client_id": "PUBLIC_CLIENT",
    "grant_type": "password",
    "username": "a_678884383",
    "password": "123456"
}
```

---


### Endpoint: Generate MFA Token

**Method:** `POST`

**URL:** `http://{{baseUrl}}/agentms-interne/api-public/AgencyBanking/MFAGenerationForTransaction`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "mfaChannel": "SMS",
    "customerType": "AGENT"
}
```

---


### Endpoint: Forgot Password Agent

**Method:** `POST`

**URL:** `http://{{baseUrl}}/agentms-interne/api/agentdetails/forgotPasswordReset`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
"emailAddress": "kens@gmail.com", 
"mfaChannel": "EMAIL", 
"password": "123456@Aa", 
"mfaToken": 1111, 
"confirmPassword": "123456@Aa"
}
```

---


### Endpoint: Login User

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management/api-public/auth/login`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| client_id | PUBLIC_CLIENT |
| grant_type | password |
| username | c_659460125 |
| password | 1234 |
| Accept-Language |  |

### Request Body

```json
{
    "client_id": "PUBLIC_CLIENT",
    "grant_type": "password",
    "username": "c_237655807870",
    "password": "1234"
}
```

---


### Endpoint: Logout

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management/api-public/auth/logout`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "client_id": "PUBLIC_CLIENT",
    "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICJmNWJhMDQ5OC1lYTliLTQ4NzQtOWIwYy1kNmM5NWM4MTY0ZWUifQ.eyJleHAiOjE2ODU3MDIyNjAsImlhdCI6MTY4NTcwMDQ2MCwianRpIjoiMjFiYjUwODUtN2MxNS00YTBkLWE3ZjItZTMzZGZjOTYxNjJkIiwiaXNzIjoiaHR0cDovLzE3Mi4yNi41LjI1OjgwNzAvYXV0aC9yZWFsbXMvQUZCX1NBUkEiLCJhdWQiOiJodHRwOi8vMTcyLjI2LjUuMjU6ODA3MC9hdXRoL3JlYWxtcy9BRkJfU0FSQSIsInN1YiI6IjZlMWYyYzRlLTY3ZTQtNDQ2YS1hMTNmLTAxNWRlOWIxNWFhMyIsInR5cCI6IlJlZnJlc2giLCJhenAiOiJQVUJMSUNfQ0xJRU5UIiwic2Vzc2lvbl9zdGF0ZSI6ImJiYWI3ZDcyLTI5YmQtNDViMi1iMTNlLTE2ZDQxNzliNGI3MiIsInNjb3BlIjoiZW1haWwgcHJvZmlsZSIsInNpZCI6ImJiYWI3ZDcyLTI5YmQtNDViMi1iMTNlLTE2ZDQxNzliNGI3MiJ9.VCw6AloeRS-0m49x8ZKYAAz4CGmm8HOJsKyzTCkrAOY"
}
```

---


### Endpoint: Generate MFA Token

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management-interne/api/mfa/generate`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "mfaChannel": "EMAIL"
}
```

---


### Endpoint: Generate MFA Token

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management-interne/api/mfa/generate`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "mfaChannel": "EMAIL"
}
```

---


### Endpoint: Generate MFA Token

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management-interne/api/mfa/generate`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "mfaChannel": "EMAIL"
}
```

---


### Endpoint: Reset User Password

**Method:** `PUT`

**URL:** `{{baseUrl}}/saramerchant/merchant/sub-user/resetPassword/:id`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Change Password

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/auth/changePassword`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "oldPassword": "oldpass",
  "newPassword": "newpass"
}
```

---

    "subscriptionPlanId": 2, 
    "currencyCode": "XAF", 
    "transactionAmount": 250
    
}

```

## **12. Generate MFA token**

**Method:** `POST`

**URL:** `http://{Base URL}/user-management-interne/api/mfa/generate`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "mfaChannel": "EMAIL"
}

```


---

# AUTH

## **1. Login User**

**Method:** `POST`

**URL:** `http://{Base URL}/user-management/api-public/auth/login`

**Purpose:** This endpoint likely creates a new resource.


### Query Parameters

| Key | Value |
|-----|-------|
|  | None |


### Headers

| Key | Value |
|-----|-------|
| client_id | PUBLIC_CLIENT |
| grant_type | password |
| username | c_659460125 |
| password | 1234 |
| Accept-Language | en/fr |




---

## **2. Logout**

**Method:** `POST`

**URL:** `http://{Base URL}/user-management/api-public/auth/logout`

**Purpose:** This endpoint likely creates a new resource.





---

## **3. Register**

### Endpoint: Bank Souscription

**Method:** `POST`

**URL:** `http://{Base URL}/user-management/api-public/registration/customer`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "bankCustomerId": "1234567",
    "countryCode": "CM",
    "phoneNumberCountryCode": "237",
    "passwordResetPhoneNumber": "237677876754",
    "passwordResetEmailAddress": "recup@gmail.com",
    "phoneNumber": "237654996543",
    "idDocumentType": "ID_CARD",
    "idDocumentNumber": "111222333",
    "idDocumentExpiryDate": "2023-11-04",
    "uin": "123456",
    "tcAccepted": true,
    "locale": "fr",
    "currencyCode": "XAF",
    "agentBankerPhoneNumber": "agentbanker phone",
    "registrationType": "EXISTING_BANK_CUSTOMER",
    "recommandedByPhoneNumber": "237655435432"
}

```

## **4. Forgot Password**

### a. Endpoint: Generate OTP Password Reset Autonomus

**Method:** `POST`

**URL:** `http://{Base URL}/user-management/api-public/mfa/generateOtpPasswordResetAutonomous`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "saraPhoneNumber": "237696403455",
    "emailAddressToValidate": "recuploic96@yopmail.com",
    "phoneNumberToValidate": "237655282898"
}

```


---

### b. Endpoint: Reset Password

**Method:** `GET`

**URL:** `http://{Base URL}/user-management/api-public/customers/forgotPasswordResetAutonomous`

**Purpose:** This endpoint likely retrieves resource details.




### Request Body


```json

{
    "mfaToken": "111111",
    "password": "1234",
    "confirmPassword": "1234",
    "mfaChannel": "SMS",
    "saraPhoneNumber": "237696403455",
    "passwordResetPhoneNumber": "237655282898",
    "passwordResetEmailAddress": "recuploic96@yopmail.com"
}

```


---

## **5. Recovery Password**

### a. Endpoint: Fetch Recovery Email or PhoneNumber

**Method:** `GET`

**URL:** `http://{Base URL}/user-management/api-public/customers/passwordResetChannelIdentifiers/237696403455`


**Purpose:** This endpoint likely retrieves resource details.

### b. Endpoint: Fetch Recovery Email or PhoneNumber

**Method:** `GET`

**URL:** `http://{Base URL}/user-management/api-public/customers/passwordResetChannelIdentifiers/237659460125`


**Purpose:** This endpoint likely retrieves resource details.

### c. Endpoint: Generate OTP

**Method:** `POST`

**URL:** `http://{Base URL}/user-management/api-public/mfa/generateOtpForValidatePhoneOrEmail`


**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

### Endpoint: Get Agent member List

**Method:** `GET`

**URL:** `http://{{baseUrl}}/agentms-interne/api-internal/backoffice/getAgentMemberList`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Non Sara Withdraw

**Method:** `GET`

**URL:** `http://{{baseUrl}}/getTrxNonSara/W202207190000946/1608696008`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Add Agent Commission

**Method:** `GET`

**URL:** `http://{{baseUrl}}/agentms-interne/api/agentdetails/addCommissionAccount`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Bearer | |


---


### Endpoint: Get Sub Agent From Agent

**Method:** `GET`

**URL:** `http://{{baseUrl}}/agentms-interne/api/agentdetails/getAgentMemberList`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Query Parameters

| Key | Value |
|-----|-------|
| iamId | ebc8a1c1-8b44-44c1-a5f7-809c4c3b26be |
| page | 0 |
| size | 10 |


---


### Endpoint: Get User Profile

**Method:** `GET`

**URL:** `http://{{baseUrl}}/user-management/api/customers/profile`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Verify Bank Account

**Method:** `GET`

**URL:** `http://{{baseUrl}}/bam/customer/0748192`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Bank Accounts

**Method:** `GET`

**URL:** `http://{{baseUrl}}/bam/customer/accounts/0760537`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Calculate Fees

**Method:** `POST`

**URL:** `http://{{baseUrl}}/sarabackofficeservices-interne/customer/transactionFees/calculate`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "paymentMethodCode": "WALLET_CASH_IN_METHOD", 
    "subscriptionPlanId": 2, 
    "currencyCode": "XAF", 
    "transactionAmount": 250
    
}
```

---


### Endpoint: Calculate Fees

**Method:** `POST`

**URL:** `http://{{baseUrl}}/sarabackofficeservices-interne/customer/transactionFees/calculate`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "paymentMethodCode": "WALLET_CASH_IN_METHOD", 
    "subscriptionPlanId": 2, 
    "currencyCode": "XAF", 
    "transactionAmount": 250
    
}
```

---


### Endpoint: Bank To Bank Transfer

**Method:** `POST`

**URL:** `http://{{baseUrl}}/bam/txn`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "sender": "10005-00001-38110090602-06",
    "receiverName": "BOULA FANKEM FRANKLIN",
    "receiver": "10005-00001-06139111051-05",
    "amount": 1000,
    "currency": "XAF",
    "description": "TR",
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "feeIds": [
            183
        ],
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    },
    "type": "DEPOSIT",
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "complementInfoDTO": {
        "paymentMethodCode": "BANK_TO_BANK_TRANSFER_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "BANK_ACCOUNT_TO_BANK_ACCOUNT_TRANSF",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANK_ACCOUNT"
    }
}
```

---


### Endpoint: Bank to other Bank Transfer

**Method:** `POST`

**URL:** `http://{{baseUrl}}/bam/txn`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "sender": "10005-00001-05452011051-50",
    "receiverName": "Test beneficiare EKOBAN",
    "receiver": "10029-26011-01318253101-34",
    "amount": 1000,
    "currency": "XAF",
    "description": "TR",
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "feeIds": [
            183
        ],
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    },
    "type": "DEPOSIT",
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "complementInfoDTO": {
        "paymentMethodCode": "BANK_TO_BANK_TRANSFER_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "BANK_ACCOUNT_TO_BANK_ACCOUNT_TRANSF",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANK_ACCOUNT"
    }
}
```

---


### Endpoint: Calculate Fees

**Method:** `POST`

**URL:** `http://{{baseUrl}}/sarabackofficeservices-interne/customer/transactionFees/calculate`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "paymentMethodCode": "WALLET_CASH_IN_METHOD", 
    "subscriptionPlanId": 2, 
    "currencyCode": "XAF", 
    "transactionAmount": 250
    
}
```

---


### Endpoint: Recurent Bank Transfer

**Method:** `POST`

**URL:** `http://{{baseUrl}}/bam/txn/recurrentTransfer`

**Purpose:** This endpoint likely creates or retrieves a resource.

### Request Body

```json
{
    "sender": "10005-00001-05452011051-50",
    "receiverName": "Test beneficiare EKOBAN",
    "receiver": "10029-26011-01318253101-34",
    "amount": 1000,
    "currency": "XAF",
    "description": "TR",
    "type": "RECURRENT_TRANSFER",
    "startDate": "2024-02-07",
    "endDate": "2024-02-08",
    "period": "M",
    
    "commission": {
        "currencyCode": "XAF",
        "transactionFee": 50,
        "feeIds": [
            183
        ],
        "fixedAmount": 50,
        "percentageAmount": 0,
        "debitSenderAmount": 50.0,
        "ttaAmount": 0.00,
        "status": true,
        "message": "FOND SUFFISANT"
    },
    "mfaToken": 111111,
    "validateWithPin": false,
    "confirm": false,
    "complementInfoDTO": {
        "paymentMethodCode": "BANK_TO_BANK_TRANSFER_METHOD",
        "channel": "SARA_MOBILE",
        "aggregatorCode": "",
        "partnerCode": "",
        "toMemberCode": "",
        "fromMemberCode": "",
        "toMemberShortName": "",
        "fromMemberShortName": "",
        "externalWalletSource": "",
        "externalWalletDestination": "",
        "externalMobileSource": "",
        "externalMobileDestination": "",
        "aggregatorTransactionType": "",
        "digitalServiceType": "BANKACC_TO_BANKACC_RECCUR_TRANSF",
        "messengerName": "",
        "messengerPhone": "",
        "paymentMode": "BANKACC_TO_BANKACC_RECCUR_TRANSF"
    }
}
```

---


### Endpoint: Get Password Config

**Method:** `GET`

**URL:** `{{baseUrl}}{{FINTECH_BASE_PATH}}/general/config/getconfigMdp`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Update Password Config

**Method:** `POST`

**URL:** `{{baseUrl}}{{FINTECH_BASE_PATH}}/general/config/setconfigMdp`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Client NonSara Config

**Method:** `GET`

**URL:** `{{baseUrl}}{{NON_SARA_PATH}}/getGeneralConfigNonSara`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Update Client NonSara Config

**Method:** `PUT`

**URL:** `{{baseUrl}}{{NON_SARA_PATH}}/updateGeneralConfigNonSara`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Transaction NonSara Refund

**Method:** `POST`

**URL:** `{{baseUrl}}{{NON_SARA_PATH}}/doCancelVoucherByOwner`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Specific Ceiling

**Method:** `GET`

**URL:** `${CHECKED_URL}/api-internal/getSpecificCeiling`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Add Specific Ceiling

**Method:** `POST`

**URL:** `${CHECKED_URL}/api-internal/addSpecificCeiling`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Update Specific Ceiling

**Method:** `PUT`

**URL:** `${CHECKED_URL}/api-internal/updateSpecificCeiling/${id}`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Delete Specific Ceiling

**Method:** `DELETE`

**URL:** `${CHECKED_URL}/api-internal/deleteSpecificCeiling/${id}`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Ceiling Scopes

**Method:** `GET`

**URL:** `${CHECKED_URL}/api-internal/getPortee`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get System List

**Method:** `GET`

**URL:** `${CHECKED_URL}/api-internal/getSystem`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Operation

**Method:** `GET`

**URL:** `${CHECKED_URL}/api-internal/getOperation/${system}/${phone}`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Update Specific Ceiling By Operation

**Method:** `POST`

**URL:** `${CHECKED_URL}/api-internal/updateSpecificCeilingByOperation`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Delete Specific Ceiling By Operation

**Method:** `DELETE`

**URL:** `${CHECKED_URL}/api-internal/deleteSpecificCeilingByOperation/${id}`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get USSD Transactions

**Method:** `GET`

**URL:** `{{baseUrl}}{{USSD_BASE_API_PATH}}/api/transfer/search`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Check Partner Availability

**Method:** `GET`

**URL:** `${CHECKED_URL}/api-internal/check_partner_availability/${serviceType}`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Merchant Profile Infos

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/info`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Merchant Profile Data

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Add Access History

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/addAccessHistory`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Upload Profile Pic

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/upload-image`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | multipart/form-data |

### Request Body

```json
{
    "image": "",
    "type": "MERCHANT_LOGO"
}
```

---


### Endpoint: Get Profile Pic

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/image/:name`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Create Sub User

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/sub-user`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "email": "user@example.com",
  "name": "John Doe",
  "mobileNumber": "1234567890",
  "password": "password123",
  "confirmPassword": "password123",
  "merchant": { "id": "merchantId" },
  "merchantGroups": [{ "id": 1 }],
  "roles": [{ "id": "roleId" }]
}
```

---


### Endpoint: Edit Sub User

**Method:** `PUT`

**URL:** `{{baseUrl}}/saramerchant/merchant/sub-user`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "id": 1,
  "email": "user@example.com",
  "name": "John Doe",
  "password": "password123",
  "confirmPassword": "password123",
  "mobileNumber": "1234567890",
  "merchant": { "id": "merchantId" },
  "merchantGroups": [{ "id": "1" }],
  "roles": [{ "id": "roleId" }]
}
```

---


### Endpoint: Create Group

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/group`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "name": "Group Name",
  "merchant": { "id": "merchantId" },
  "roles": [{ "id": "roleId" }]
}
```

---


### Endpoint: Edit Group

**Method:** `PUT`

**URL:** `{{baseUrl}}/saramerchant/merchant/group/:id`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "id": 1,
  "name": "Group Name",
  "merchant": { "id": "merchantId" },
  "roles": [{ "id": "roleId" }]
}
```

---


### Endpoint: Delete Group

**Method:** `DELETE`

**URL:** `{{baseUrl}}/saramerchant/merchant/group/:id`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Subscribed Plan

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/subscriptions`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Merchant Summary

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/dashboard/summary`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get All Users

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/sub-user`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get All Groups

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/group`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Currencies

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/currencies`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Countries

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/countries`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Mobile Operators

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/mobile-operators`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Mobile Accounts

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/mobile-accounts`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Add Mobile Account

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/mobile-accounts`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
[{
  "country": { "id": 1 },
  "isCustomerWallet": true,
  "operator": { "operator_id": 1 },
  "phoneNumber": "1234567890"
}]
```

---


### Endpoint: Remove Mobile Account

**Method:** `DELETE`

**URL:** `{{baseUrl}}/saramerchant/merchant/profile/mobile-accounts/:account_id`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get KYC Details

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/kyc`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Send KYC Details

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/kyc`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | multipart/form-data |

### Request Body

```json
{
    "json": "{...KYC JSON...}",
    "uploadproof": "",
    "addressproof": ""
}
```

---


### Endpoint: Get Shops

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Create Shop

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "name": "Shop Name",
  "status": true
}
```

---


### Endpoint: Edit Shop

**Method:** `PUT`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops/:shopId`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "shopId": 1,
  "name": "Shop Name",
  "status": true
}
```

---


### Endpoint: Get MSM Shops

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops/users/:userId`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Shop Managers

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops/:shopId/users`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Edit Shop Managers

**Method:** `PUT`

**URL:** `{{baseUrl}}/sarabackofficeservices/merchant/shops/:shopId/users`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "email": "manager@example.com",
  "mobileNumber": "1234567890",
  "name": "Manager Name",
  "shopId": 1
}
```

---


### Endpoint: Create Shop Manager

**Method:** `POST`

**URL:** `{{baseUrl}}/sarabackofficeservices/merchant/shops/users`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "email": "manager@example.com",
  "mobileNumber": "1234567890",
  "name": "Manager Name",
  "shopId": 1,
  "password": "password123",
  "confirmPassword": "password123",
  "shopIds": [1,2]
}
```

---


### Endpoint: Get Default POS

**Method:** `GET`

**URL:** `{{baseUrl}}/sarabackofficeservices/merchant/shops/pos/default`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Get Shop POS

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops/:shopId/pos`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Create POS

**Method:** `POST`

**URL:** `{{baseUrl}}/sarabackofficeservices/merchant/shops/:shopId/pos`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "shopId": 1,
  "name": "POS Name"
}
```

---


### Endpoint: Update POS

**Method:** `PUT`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops/pos/:id`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "id": 1,
  "name": "POS Name",
  "status": true,
  "shopId": 1,
  "shop": { "shopId": 1 }
}
```

---


### Endpoint: Create POS Manager

**Method:** `POST`

**URL:** `{{baseUrl}}/sarabackofficeservices/merchant/shops/pos/:posId/users`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "posIdList": 1,
  "shopId": 1,
  "name": "Manager Name",
  "mobileNumber": "1234567890",
  "email": "manager@example.com",
  "password": "password123",
  "confirmPassword": "password123"
}
```

---


### Endpoint: Get POS Managers

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/shops/pos/:posId/users`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Edit POS Managers

**Method:** `PUT`

**URL:** `{{baseUrl}}/sarabackofficeservices/merchant/shops/pos/:posId/users`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "posIdList": 1,
  "shopId": 1,
  "name": "Manager Name",
  "mobileNumber": "1234567890",
  "email": "manager@example.com"
}
```

---


### Endpoint: Get All Roles

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/roles`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Create Role

**Method:** `POST`

**URL:** `{{baseUrl}}/saramerchant/merchant/roles`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "payload": {
    /* RoleDto fields here */
  }
}
```

---


### Endpoint: Edit Role

**Method:** `PUT`

**URL:** `{{baseUrl}}/saramerchant/merchant/roles/:id`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "id": "roleId",
  "payload": {
    /* RoleDto fields here */
  }
}
```

---


### Endpoint: Get Merchant Permissions

**Method:** `GET`

**URL:** `{{baseUrl}}/saramerchant/merchant/roles/permissions`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Register Phone Verification

**Method:** `GET`

**URL:** `{{baseUrl}}/sarabackofficeservices/public/merchant/verification/phone/:phone`

**Purpose:** This endpoint likely creates or retrieves a resource.


---


### Endpoint: Register User

**Method:** `POST`

**URL:** `{{baseUrl}}/sarabackofficeservices/public/merchant/registration`

**Purpose:** This endpoint likely creates or retrieves a resource.


### Headers

| Key | Value |
|-----|-------|
| Content-Type | application/json |

### Request Body

```json
{
  "merchantName": "Merchant Name",
  "email": "merchant@example.com",
  "password": "password123",
  "confirmPassword": "password123",
  "phoneNo": "1234567890",
  "firstName": "John",
  "lastName": "Doe",
  "twoFactorStatus": true
}
```

---


{
    "mfaToken": 748826,
    "saraPhoneNumber": "237659460125",
    "passwordResetPhoneNumber": "237655807870"
}

```


---

### d. Endpoint: Save phone number / email of recovery

**Method:** `POST`

**URL:** `http://{Base URL}/user-management/api-public/customers/savePhoneOrEmailForPasswordReset`



**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "mfaToken": "111111",
    "saraPhoneNumber": "237659460125",
    "passwordResetEmailAddress":"bbb@gmail.com"
}

```


---



# OTHERS

## **1. Tontine**

 ### a. Endpoint: Add New Member

**Method:** `POST`

**URL:** `http://{Base URL}/tontine/member`



**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "wallet": 2376, 
    "tontineId": 506, 
    "type": "OM"
}

```
---

### b. Endpoint: Get Jackpot Approval

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/jackpot/approval`


**Purpose:** This endpoint likely retrieves resource details.





---

### c. Endpoint: Get Jackpot Details

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/jackpot/getJackPotDetails?jackpotId=318`


**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| jackpotId | 318 |




---

### d. Endpoint: Get Jackpot Details

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/jackpot/getJackPotDetails?jackpotId=329`


**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| jackpotId | 329 |




---

### e. Endpoint: Get Jackpot Invitation

**Method:** `GET`

**URL:** `http://{Base URL}/tontine-interne/jackpot/invitation?inviteeId=1214&state=APPROVED&event=DISBURSEMENT
`


**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| inviteeId | 1214 |
| state | APPROVED |
| event | DISBURSEMENT
 |




---

### f. Endpoint: Get Jackpot List

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/jackpot`



**Purpose:** This endpoint likely retrieves a list of resources.




### Request Body


```json

{
    "tontineId": 605,
    "state": null
}

```


---

### e. Endpoint: Get Sub Tontine

**Method:** `GET`

**URL:** `http://{Base URL}/tontine-interne/tontine/sub/1502`


**Purpose:** This endpoint likely retrieves resource details.

---

### f. Endpoint: Get Sub Tontine By Wallet

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/invitation/byWallet?wallet=653346688&tontineType=SUB_TONTINE
`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| wallet | 653346688 |
| tontineType | SUB_TONTINE |
---

### g. Endpoint: Get Sub Tontine List

**Method:** `GET`

**URL:** `http://{Base URL}/tontine-interne/tontine/sub/1502`


**Purpose:** This endpoint likely retrieves a list of resources.

---

### h. Endpoint: Get Tontine Contribution History

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/transact/history?memberId=2502&txnType=CONTRIBUTION&page=1&size=20`


**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| memberId | 2502 |
| txnType | CONTRIBUTION |
| page | 1 |
| size | 20 |
---

### i. Endpoint: Get Tontine Contribution List

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/transact/history?memberId=2502&txnType=DISBURSEMENT&page=1&size=20`


**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| memberId | 2502 |
| txnType | DISBURSEMENT |
| page | 1 |
| size | 20 |
---

### j. Endpoint: Get Tontine Jackpot History

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/transact/history?memberId=2461&txnType=DISBURSEMENT&page=0&size=20`



**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| memberId | 2461 |
| txnType | DISBURSEMENT |
| page | 0 |
| size | 20 |

---

### k. Endpoint: Get Tontine List

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/tontine/findByWallet?wallet=237655807870&tontineType=TONTINE`


**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| wallet | 237655807870 |
| tontineType | TONTINE |
---

### l. Endpoint: Get Tontine Member List ???

**Method:** `GET`

**URL:** `http://sara-gateway.eastus.cloudapp.azure.com/tontine/member/byTontine?tontineId=27`

**Base URL:** `sara-gateway.eastus.cloudapp.azure.com`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| tontineId | 27 |
---

### m. Endpoint: Get Tontine Pending Invitation List

**Method:** `GET`

**URL:** `http://{Base URL}/tontine/invitation/byWallet?wallet=696403455&tontineId=453&state=&event&type=TONTINE&fromDate&toDate`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| wallet | 696403455 |
| tontineId | 453 |
| state |  |
| event | None |
| type | TONTINE |
| fromDate | None |
| toDate | None |
---

### n. Endpoint: Tontine Invitation

**Method:** `GET`

**URL:** `http://{Base URL}/tontine-interne/invitation/byWallet?wallet=655807870&tontineId=1217&tontineType=TONTINE`


**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| wallet | 655807870 |
| tontineId | 1217 |
| tontineType | TONTINE |
---

### o. Endpoint: Tontine Invitation

**Method:** `GET`

**URL:** `http://{Base URL}/tontine-interne/invitation/byWallet?wallet=655807870&tontineId=1217&tontineType=TONTINE`



**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| wallet | 655807870 |
| tontineId | 1217 |
| tontineType | TONTINE |

---

## **2. Devices management**

### a. Endpoint: Check Connexion

**Method:** `GET`

**URL:** `http://{Base URL}:7001/api-internal/devices/checkConnexion/237659460125/IOS_16.2_9B153498-4CDD-46A2-B335-3409032DBFA`


**Purpose:** This endpoint likely retrieves resource details.

### b. Endpoint: Delete Device

**Method:** `DELETE`

**URL:** `http://{Base URL}/user-management/api-internal/devices/remove/166`


**Purpose:** This endpoint likely deletes a resource.





---

### c. Endpoint: Get Device List

**Method:** `GET`

**URL:** `http://{Base URL}/user-management/api-internal/devices/myDevice/1027346`



**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| type | root |



## **3. Localisation Agence/ATM/TPE**

### Endpoint: Get Branch By Town

**Method:** `GET`

**URL:** `http://{Base URL}/bam/common/branch/YAOUNDE`


**Purpose:** This endpoint likely fetches a specific resource using a query parameter.


## **4. Accounts/Profile**

### a. Endpoint: Get Bank Accounts

**Method:** `GET`

**URL:** `https://{Base URL}/bam/customer/accounts/771354`




### b. Endpoint: Get User Profile

**Method:** `GET`

**URL:** `https://{Base URL}/user-management/api/customers/profile`


**Purpose:** This endpoint likely retrieves resource details.


### c. Endpoint: Get Wallet Account

**Method:** `GET`

**URL:** `https://{Base URL}/wallet-management/api/wallets/balance`


**Purpose:** This endpoint likely retrieves a list of resources.

### d. Endpoint: Verify Bank Account

**Method:** `GET`

**URL:** `http://{Base URL}/bam/customer/0748192`


**Purpose:** This endpoint likely retrieves resource details.

### e. Endpoint: Get UserName By His Phone Number

**Method:** `GET`

**URL:** `http://{Base URL}/wallet-management/api/wallets/237659460125/name`


**Purpose:** This endpoint likely fetches a specific resource using a query parameter.


### f. Endpoint: Wallet Transfer Get Customer Detailes

**Method:** `GET`

**URL:** `http://{Base URL}/agentms/api/walletTransfers/walletCustomerDetails/237696403455`


**Purpose:** This endpoint likely retrieves a list of resources.





---

### g. Endpoint: Get User Wallet Balance

**Method:** `GET`

**URL:** `http://{Base URL}/wallet-management/api-internal/wallets/getBalance?userType=CUSTOMER&walletOwnerNumber=237659460125`


**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| userType | CUSTOMER |
| walletOwnerNumber | 237659460125 |


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTcyOTgyMjc5NywxMTc4Njc3MDM5LC01NT
QzMjY0NDJdfQ==
-->