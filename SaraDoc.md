
# SARA V2 API Documentation 

This document describes the available API endpoints in the SARA V2 mobile system.   
The collection is organized into three main categories:

-   **OPERATIONS**: APIs related to transaction flows and financial activities, including **wallet** and **bank** operations.
    
-   **AUTH**: Authentication and security-related endpoints to manage user access, tokens, and session flows.
    
-   **OTHERS**: Additional supporting APIs that don't fall under the main operation or auth flows but are essential to the overall application functionality.
   
---
**baseUrl=** `serverAddress`

## OPERATIONS

## **1. Wallet To Wallet**

### Endpoint: Proceed Wallet to Wallet

**Method:** `POST`

**URL:** `http://{{baseUrl}}/wallet-management/api/transactions/walletToWallet`

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

**URL:** `http://{{baseUrl}}/bam/txn`

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

**URL:** `http://{{baseUrl}}/bam/txn/recurrentTransfer`

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

**URL:** `http://{{baseUrl}}/wallet-management/api/requestMoney/received?page=0&size=10`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| page | 0 |
| size | 10 |




---

### Endpoint: Get send request list

**Method:** `GET`

**URL:** `http://{{baseUrl}}/wallet-management/api/requestMoney/requested?page=1&size=10`

**Purpose:** This endpoint likely retrieves a list of resources.


### Query Parameters

| Key | Value |
|-----|-------|
| page | 1 |
| size | 10 |




---

### Endpoint: Pay Request

**Method:** `POST`

**URL:** `http://{{baseUrl}}/wallet-management-interne/api/transactions/payRequestMoney`


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

**URL:** `http://{{baseUrl}}/wallet-management/api/wallets/history?currencyCodes=XAF&fromDate=2023-12-04&toDate=2023-12-14&page=0&size=10`

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

**URL:** `http://{{baseUrl}}/bam/account/statement/10005-00056-07605371051-12/2023-02-26/2023-03-08/0/100`

**Purpose:** This endpoint likely retrieves resource details.

## **6. GIMAC**

### Endpoint: Check Gimac Availability

**Method:** `GET`

**URL:** `http://{{baseUrl}}/gimac/api/gimac/authentication/doCheckAvailabilityOfGimac`

**Purpose:** This endpoint likely retrieves resource details.

## **7. Cash In**

**Method:** `POST`

**URL:** `http://{{baseUrl}}/wallet-management-interne/api/wallets/topUp/afriland`

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

**URL:** `http://{{baseUrl}}/wallet-management-interne/api/transactions/cashOut`

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

**URL:** `http://{{baseUrl}}/wallet-management/api/payment/services`

**Purpose:** This endpoint likely retrieves a list of resources.





---

### b. Endpoint: Get List of merchants

**Method:** `GET`

**URL:** `http://{{baseUrl}}/wallet-management/api/payment/merchants`

**Purpose:** This endpoint likely retrieves a list of resources.





---

## **10. Merchant payment**

### a. Endpoint: Get Merchant Details

**Method:** `POST`

**URL:** `http://{{baseUrl}}/saramerchant-interne/customer/transactions/before-payment-by-code`

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

**URL:** `http://{{baseUrl}}/saramerchant-interne/customer/transactions/payment-by-code`

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

**URL:** `http://{{baseUrl}}/sarabackofficeservices-interne/customer/transactionFees/calculate`

**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "paymentMethodCode": "WALLET_CASH_IN_METHOD", 
    "subscriptionPlanId": 2, 
    "currencyCode": "XAF", 
    "transactionAmount": 250
    
}

```

## **12. Generate MFA token**

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management-interne/api/mfa/generate`

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

**URL:** `http://{{baseUrl}}/user-management/api-public/auth/login`

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

**URL:** `http://{{baseUrl}}/user-management/api-public/auth/logout`

**Purpose:** This endpoint likely creates a new resource.





---

## **3. Register**

### Endpoint: Bank Souscription

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management/api-public/registration/customer`

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

**URL:** `http://{{baseUrl}}/user-management/api-public/mfa/generateOtpPasswordResetAutonomous`

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

**URL:** `http://{{baseUrl}}/user-management/api-public/customers/forgotPasswordResetAutonomous`

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

**URL:** `http://{{baseUrl}}/user-management/api-public/customers/passwordResetChannelIdentifiers/237696403455`


**Purpose:** This endpoint likely retrieves resource details.

### b. Endpoint: Fetch Recovery Email or PhoneNumber

**Method:** `GET`

**URL:** `http://{{baseUrl}}/user-management/api-public/customers/passwordResetChannelIdentifiers/237659460125`


**Purpose:** This endpoint likely retrieves resource details.

### c. Endpoint: Generate OTP

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management/api-public/mfa/generateOtpForValidatePhoneOrEmail`


**Purpose:** This endpoint likely creates a new resource.




### Request Body


```json

{
    "mfaToken": 748826,
    "saraPhoneNumber": "237659460125",
    "passwordResetPhoneNumber": "237655807870"
}

```


---

### d. Endpoint: Save phone number / email of recovery

**Method:** `POST`

**URL:** `http://{{baseUrl}}/user-management/api-public/customers/savePhoneOrEmailForPasswordReset`



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

**URL:** `http://{{baseUrl}}/tontine/member`



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

**URL:** `http://{{baseUrl}}/tontine/jackpot/approval`


**Purpose:** This endpoint likely retrieves resource details.





---

### c. Endpoint: Get Jackpot Details

**Method:** `GET`

**URL:** `http://{{baseUrl}}/tontine/jackpot/getJackPotDetails?jackpotId=318`


**Purpose:** This endpoint likely retrieves resource details.


### Query Parameters

| Key | Value |
|-----|-------|
| jackpotId | 318 |




---

### d. Endpoint: Get Jackpot Details

**Method:** `GET`

**URL:** `http://{{baseUrl}}/tontine/jackpot/getJackPotDetails?jackpotId=329`


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
eyJoaXN0b3J5IjpbLTY5OTE2MzEwNSwyMDk4MzA0OTYxLC02Nz
E0OTE1NzgsLTIxMDM5MjgwNDgsODIyNzgzMDQzLDE5ODg4NDYy
MjAsLTQyODc3MTksLTk0MjU2NDAyNSw1MjE1MTI0ODcsLTEzND
U0ODA0NjMsMTE4MzEyOTY0NSwtMTA4NjYwMjgwNiwxNjMzODY0
Nzc4LC01NzgxNzM1ODZdfQ==
-->