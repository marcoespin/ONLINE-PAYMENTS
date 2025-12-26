---
stoplight-id: 40a4d94988403
---



# Changelog

**Stay up to date with changes and updates to the Kushki API.**

We used the [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) standard (**YYYY-MM-DD**) for dates, the Semantic Versioning (**MAJOR.MINOR.PATCH**) for version numbers, increasing the:

1. **MAJOR** version when we make incompatible API changes,
2. **MINOR** version when we add functionality in a backwards compatible manner, and
3. **PATCH** version when we make backwards compatible bug fixes.

### Types of changes

- `Added` for new features.
- `Changed` for changes in existing functionality.
- `Deprecated` for soon-to-be removed features.
- `Removed` for now removed features.``
- `Fixed` for any bug fixes.
- `Security` in case of vulnerabilities.

All notable changes to this project will be documented in this file.

## 1.3.1 - 2022-06-24

### Added


- Added the `IVAagenciaDeViaje` field in `extraTaxes` object for airlines in Colombia.
- Added `accountType` field in `card` object for **CARD - Request a card token** and **ON-DEMAND & SCHEDULED CHARGES - Request a recurring charge token** endpoints. This field will be required for debit card transactions in Colombia.
- Added `jwt` field in **CARD - Request a card token** and **ON-DEMAND & SCHEDULED CHARGES - Request a recurring charge token** endpoints to add support to 3DS via API.
- Added **PE, CO - 3DS authentication required** and **PE - 3DS authentication not required** request examples on CARD - Request a card token endpoint.
- Added **PE, CO - 3DS authentication required** and **PE - 3DS authentication not required** response examples on CARD - Request a card token endpoint.
- Example of response code 400 **PE, CO - 3DS Otp not validated** added in the **Make a charge or deferred charge** endpoint.
- Example of response code 500 **GL - JWT expired or invalid** added in the **Make a charge or deferred charge** endpoint.
- Added `baseMessage`, `paymentBrand` and `transactionReference` fields in **CARD - Make a charge or deferred charge** endpoint for responde code 400.
- Examples of response code 400 added in the **Create a recurring charge** endpoint.
- Updated schema for 400 code response on **ON-DEMAND & SCHEDULED CHARGES - Make an on-demand charge** endpoint.
- Example of response code 400 **GL - Declined transaction** added in the **ON-DEMAND & SCHEDULED CHARGES - Make an on-demand charge** endpoint.

### Changed

- Transfer In - Init Transaction: response of `referenceNumber` will be `1111111` for México.

## 1.3.0 - 2022-05-11

### Added

- New CARD - **Bin Info V2** endpoint added for eight digit bins support.

### Changed

- CARD - Request deferred options endpoint description updated. Changed text from "first six digits" to "first eight digits" to add support for eight digit bins.

### Removed

- TRANSFER OUT - **Void a transaction** endpoint removed.

## 1.2.0 - 2022-04-21

### Added

- Support for chargebacks through the API added. The following endpoints have been added to handle chargebacks through the API:
  - List all chargebacks: lists all chargebacks in INITIALIZED status generated up to 72 hours before the time of the query.
  - Upload evidence: You can upload files through this endpoint that serve as evidence to help us resolve the chargeback in your favor.
  - Update a chargeback: Depending on the type of chargeback, it will be necessary to update the chargeback with the necessary evidence.

## 1.1.0 - 2022-04-12

### Added

- Transfer In - Init Transaction:
  - `contactDetails` object required for merchants in Colombia using PSE Avanza.
  - Example **CO - PSE Avanza** added

- Transfer Out - Get Bank List: 
  - Examples **CO - Bank list** and **MX - Bank list** added.
  
- Transfer Out - Request a Transfer Out token:
  - `name` field added. **Only required for Mexican transfer out transactions. Full name.**
  - Allowed value `CB` for `accountType` field added for Mexican transfer out transactions.
  - `accountType` description added: 
    CC = Cuenta Corriente.
    CA = Cuenta Ahorros
    CB = Cuenta CLABE.
  - Allowed value `MXN`for `currency`field added for Mexican transfer out transactions.
  - Examples **CO - Request a Transfer Out token** and **MX - Request a Transfer Out token** added.
  - Example of error code 400 **GL - Invalid request body.** added

- Transfer Out -Get Status:
    - Allowed value `MXN`for `currency`field added for Mexican transfer out transactions.
    - `transactionReference` field added in response body.
    - Examples **CO - Approval transaction** and **MX - Initialized transaction** added.


### Changed

- Transfer In - Request a Transfer In token: 
  - Updated `userType` field description from "Required in Colombia, Perú, Chile and Ecuador." to "**Required in Colombia, Optional in Chile.**"

- Transfer Out - Request a Transfer Out token:
  - `Public-Merchant-Id` and `Content-Type` headers required.

- Transfer Out - Void a transaction:
  - Updated endpoint description. Added **NOTE: Void only works for Colombia.**
- On-demand & scheduled charges - Make an on-demand charge:
  - changed `token` field description from "Get this token from your front-end using the **requestTokenCharge()** method available in kushki.js" to "Get this token from your front-end using the **requestDeviceToken()** method available in kushki.js"


### Deprecated

- `propina` in `extraTaxes` deprecated.



## 1.0.1 - 2022-03-22

### Added

- Request a card token: 5 new examples were added for the next countries: Peru (Soles), Colombia (COP), Ecuador and Peru (USD), México(MXN), and Chile (CLP).
- Note for tokens expiration (30 minutes).
- `Product model` was added.
- `Card model` was added.
- `Deferred model` was added.
- `OrderDetails` model was added.
- `BinInfo` model was added.
- `Channel` model was added with the following allowed values: `PRESTASHOP`, `WOOCOMMERCE`, `MAGENTO`, `WEBCHECKOUTPLUS`, `WEBCHECKOUT`.
- `Country model` was added with the following allowed values: `Peru`, `México`, `Colombia`, `Ecuador`, `Chile`.
- `PaymentMethod` model was added with the following allowed values: `card`, `cash`, `transfer`.
- Search credentials: Added filter by `merchantId`, `privateCredentialId`, `publicCredentialId` or `credentialId`.
- ON-DEMAND & SCHEDULED CHARGES - Authorize payments: Added `months` field for deferred transaction.
- Card - Authorize payments: Added `months` field for deferred transaction.


### Changed

- Request a card token: `totalAmount` field marked as required.
- Make a charge or deferred charge: **Single charge** example was updated.
- Make a charge or deferred charge: updated response schema.
- Changed `ExtraTaxes` to `extraTaxes` on applicable endpoints.
- Make a charge or deferred charge: changed `address` to `address1` and `address2` for `shippingDetails` and `billingDetails` objects.
- Make a charge or deferred charge: updated **deferred** examples.
- Make a charge on a suscription: Token marked as required.
- Make a charge on a suscription: changed token note from *Required only when working with Sift* to *Get this token from your front-end using the `requestTokenCharge()` method available in kushki.js*.
- Refund a transaction: Updated response schema with all posibles fields.
- Refund a transaction: Added response examples.
- Authorize payments: Added `orderDetails`, `ip`, `maskedCardNumber`, `acquirerBank`, `processorType`, `cardType`, `issuingBank`, `country`, `foreignCard`, `cardCountry`, `rules` fields to response.
- Authorize payments: Updated 400 response schema. Added 400 code example.
- Capture an authorized payment: Added `ticketNumber`, `maskedCardNumber`, `acquirerBank` fields to response.
- Capture an authorized payment: Updated 201 code example.
- Capture an authorized payment: Added 400 code example
- Bin Info: Added credit and debit examples
- Validate OTP: Added "CardRule Credential not found" example
- Create a payment button: Added 400 code example.
- Get Commission Configuration: Added 400 code example.
- Get Commission Configuration: `Content-Type`and `Public-Merchant-Id`headers required.
- Get gateway status: `Content-Type`and `Public-Merchant-Id`headers required.
- Get transactions list: Updated response schema. Added `acquirer_bank`, `aurus_ticket_number`, `contact_details`, `country`, `credential_metadata`, `foreign_card`, `historical`, `operation_id`, `preauth_transaction_reference`, `processor_transaction_id`, `public_credential_id`, `sale_approval_code`, `sale_transaction_type`, `visibility`, `card_country_code`, `card_country`, `order_details`, `product_details` fields.
- Get transactions list: Changed security object from `code`, `id`, `message`, `service` to `ip`, `user_agent`, `whitelist`
- Get transactions list: Updated 200 code example.
- Create a credential: Content-Type header required.
- Create a credential: Updated request example.
- Create a credential: Updated 201 code example.
- Search credentials: Content-Type header required.
- Search credentials: Updated 200 code example.
- Search credentials: The `data` and `total` fields are required in the response.
- Search credentials: Added descriptions for `limit`, `offset` and `filter` fields in the request.
- Advanced search: Content-Type header required.
- Activate or deactivate: Added response schema.
- Activate or deactivate: Added response examples.
- Activate or deactivate: Changed path parameter name from `credential_id` to `credentialId`. 
- Delete credential: `Content-Type` header required.
- Delete credential: Changed path parameter name from `credential_id` to `credentialId`. 
- Update credential: `Content-Type` header required.
- Update credential: Changed path parameter name from `credential_id` to `credentialId`.
- Update credential: Added 402 error code example.
- Regenerate a credential: `Content-Type` header required.
- Create a Smartlink: `Private-Merchant-Id` and `Content-Type` headers required.
- Create a Smartlink: updated `amount`field in the request.
- Create a Smartlink: Changed `primaryColor` and `secondaryColor` to not required.
- Create a Smartlink: Added request examples.
- Get a Smartlink: `Private-Merchant-Id` header required.
- Get a Smartlink: Updated 400 erro code example.
- Get a Smartlink: Updated response.
- Delete a smartlink: `Private-Merchant-Id` header required.
- Delete a smartlink: Added 400 error code examples.
- Update a Smartlink: `Private-Merchant-Id` and `Content-Type` headers required.
- Update a Smartlink: Deleted duplicated `smartlinkId` path parameter.
- Update a Smartlink: Added 400 erro code examples.
- Async card subscription - Request a token: `Public-Merchant-Id` and `Content-Typ`e headers required.
- Init an async card subscription: `Private-Merchant-Id` and `Content-Type` headers required.
- Init an async card subscription: Updated `contactDetails` and `amout` fields in request body.
- Init an async card subscription: Updated request body example.
- Init an async card subscription: Added 400 code examples.
- Request a card async token: `Public-Merchant-Id` and `Content-Type` headers required.
- Request a card async token: Updated 400 code example.
- Card async - Init Transaction: `Private-Merchant-Id` and `Content-Type` headers required.
- Card async - Init Transaction: Updated `amount` field in request body.
- Card async - Init Transaction: Added 400 error code examples.
- Card async - Get Status: `Private-Merchant-Id` and `Content-Type` headers required.
- Card async - Get Status: Updated status field in request body allowed values, added `requestedToken`value.
- Card async - Get Status: Updated response body. Added `credentialInfo`object.
- Request a cash out token: `Public-Merchant-Id` and Content-Type headers required
- Request a cash out token: Updated request body example.
- Cash out - Init Transaction: `Private-Merchant-Id` and `Content-Type` headers required.
- Cash out - Init Transaction: Added 400 error code examples.
- Cash out - Transaction Status: `Private-Merchant-Id` header required.
- Cash out - Transaction Status: Added 400 error code examples.
- Update a cash out transaction: `Private-Merchant-Id` and `Content-Type` headers required.
- Update a cash out transaction: Added 400 error code examples.
- Update a cash out transaction: `totalAmount` field required.
- Delete a cash out transaction: `Private-Merchant-Id` header required.
- Delete a cash out transaction: Added 400 error code examples.
- Card subscriptions: Changed category name to **ON-DEMAND & SCHEDULED CHARGES**.
- Request a subscription token: Changed endpoint name to **Request a recurring charge token**.
- Request a recurring charge token: Updated endpoint description.
- Create a subscription: Changed endpoint name to **Create a recurring charge**.
- Create a recurring charge: Updated endpoint description.
- Update a subscription card data: Changed endpoint name to **Update recurring charge card data**.
- Update recurring charge card data: Updated endpoint description.
- Make a charge on a subscription: Changed endpoint name to **Make an on-demand charge**.
- Make an on-demand charge: Updated endpoint description.
- Add a temporary charge or discount: Updated endpoint description.
- Cancel a subscription: Changed endpoint name to **Cancel a recurring charge**.
- Cancel a recurring charge: Updated endpoint description.
- Update a subscription: Changed endpoint name to **Update a recurring charge**.
- Update a recurring charge: Updated endpoint description.
- Get Subscription Info: Changed endpoint name to **Get recurring charge Info**. 
- Authorize payments: Updated endpoint description.
- Capture an authorized payment: Updated endpoint description.
- Get Subscription Info: Changed endpoint name to **Get recurring charge Info**.
- Get recurring charge Info: Updated endpoint description.
- Cash in - Init Transaction: Updated request body example.
- Cash in - Init Transaction: Added 400 code examples.
- Cash in - Transaction Status: `Private-Merchant-Id` header required.
- Update a cash in transaction: Added 400 code examples.
- Transfer out - Get Bank List: `Public-Merchant-Id` header required.
- Request a Transfer Out token: `Public-Merchant-Id` header required.
- Transfer out - Init Transaction: `Private-Merchant-Id `and `Content-Type` headers required.
- Transfer out - Get Status: `Private-Merchant-Id` header required.
- Transfer out - Void a transaction: `Private-Merchant-Id` header required.
- Transfer out - Void a transaction: Added 400 code examples.
- Request a Transfer In token: `Public-Merchant-Id` and `Content-Type` headers required
- Transfer in - Init transaction: `Private-Merchant-Id` and `Content-Type` headers required.
- Transfer in - Get status: `Private-Merchant-Id` header required.
- Request a recurring charge token: Content-Type header required.
- Create a recurring charge: `Content-Type` header required.
- Cancel a recurring charge: `Private-Merchant-Id` header required.
- Update a recurring charge: `Private-Merchant-Id` and Content-Type headers required.
- Add a temporary charge or discount: `Private-Merchant-Id` and `Content-Type` headers required.
- Authorize payments: `Private-Merchant-Id` and `Content-Type` headers required. 
- Capture an authorized payment: `Private-Merchant-Id` and `Content-Type` headers required.
- Get recurring charge Info: `Private-Merchant-Id` header required.
- Async card subscriptions: Changed category name to **ASYNC CARD RECURRING CHARGES**.
- ASYNC CARD RECURRING CHARGES - Request a token: Updated endpoint description.
- ASYNC CARD RECURRING CHARGES - Init an async card subscription: Changed endpoint name to **Init an async card recurring charge**.
- Init an async card recurring charge: Updated endpoint description.


### Fixed

- Fixed typos in many edpoints pages



## 1.0.0 - 2022-02-21

### Added

- This change log file will serve as a reference for future updates.
