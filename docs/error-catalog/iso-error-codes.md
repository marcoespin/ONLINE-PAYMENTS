# ISO errors

>This Error Catalog only applies to **Kushki Acquiring Model**, available for Colombia, Chile, Mexico, and Peru.


The field `isoErrorCode` is returned in declined single charges, preauthorizations, one-click charges when the `fullResponse` is set to `v2` and could be returned either by the Card franchises or processors. 

>**Note**
><br>In case it has a value of `228` corresponds to an internal decline of Kushki.
Click [here](https://api-docs.kushkipagos.com/docs/online-payments/iso-error-codes) for the complete error catalog.

In case this code comes from the Card franchises (Visa, Mastercard or Prosa), it will have two digits. Below you will find the most common error codes:

<!--
type: tab
title: Mastercard
-->

| ISO Error Code  | Description  |
|---|---|
| 00  | Approved or completed successfully
| 01  | Refer to card issuer  |
|  03 |  Invalid merchant |
| 04  |  Capture card |
| 05 | Do not honor  |
| 08 | Honor with ID|
| 10  | Partial Approval  |
| 12   | Invalid transaction  |
| 13   | Invalid amount  |
| 14   | Invalid card number  |
| 15   | Invalid issuer  |
| 30  |Format error   |
| 41  | Lost card
| 43  |Stolen card   |
| 51  |Insufficient funds/over credit limit   |
| 54   | Expired card  |
|55    | Invalid PIN  |
| 57   | Transaction not permitted to issuer/cardholder  |
| 58   | Transaction not permitted to acquirer/terminal  |
| 61   | Exceeds withdrawal amount limit   |
|62    | Restricted card  |
| 63   | Security violation  |
| 65   | Exceeds withdrawal count limit OR Identity Check Soft-Decline of EMV 3DS Authentication (merchant should resubmit authentication with 3DSv1)|
|  70  | Contact Card  |
| 71   | Issuer PIN Not Changed  |
| 75   | Allowable number of PIN tries exceeded  |
| 76   | Invalid/nonexistent “To Account” specified  |
| 77   | Invalid/nonexistent “From Account” specified  |
| 78   |  Invalid/nonexistent account specified (general) |
| 79   | Life cycle (Mastercard use only for 0110 messages)  |
| 81   | Domestic Debit Transaction Not Allowed (Regional use only)  |
| 82   | Policy (Mastercard use only for 0110 messages)  |
| 83   | Fraud/Security (Mastercard use only for 0110 messages)  |
| 84   | Invalid Authorization Life Cycle  |
| 85   | Not declined Valid for all zero amount transactions.  |
| 86   | PIN Validation not possible  |
| 87   |  Purchase Amount Only, No Cash Back Allowed |
| 88   | Cryptographic failure  |
| 89   | Unacceptable PIN— Transaction Declined— Retry  |
| 91   | Authorization System or issuer system inoperative  |
| 92   | Unable to route transaction  |
|  94  |  Duplicate transmission detected |
| 96   | System error  |


<!--
type: tab
title: Visa
-->

| ISO Error Code  | Description  |
|---|---|
| 00  | Approval and completed successfully Accepted and processed
| 01  | Refer to card issuer  |
| 02  | Refer to card issuer, special condition  |
| 03 |  Invalid merchant |
| 04  |  Pick up card (no fraud) |
| 05 | Do not honor  |
| 06 | Error  |
| 07 | Pick up card, special condition (fraud account)  |
| 10  | Partial Approval  |
| 11  | Approved  |
| 12   | Invalid transaction  |
| 13   | Either Invalid amount or Currency conversion field overflow  |
| 14   | Either invalid card number, No modulus 10 check, not a valid length for issuer or not in positive PIN Verification file l Separator in wrong position  |
| 15   | No such issuer (first 8 digits of account number do not relate to an issuing identifier)  |
| 19  |Re-enter transaction   |
| 21  |No action taken   |
| 25  |Unable to locate record in file   |
| 28  |File is temporarily unavailable for update or inquiry  |
| 39  |No credit account  |
| 41  | Lost card, pick up card (fraud account)|
| 43  |Stolen card, pick up (fraud account)  |
| 46  |Closed account  |
| 51  |Not sufficient funds  |
| 52  |No checking account  |
| 53  |No savings account  |
| 54   | Expired card or expiration date missing  |
|55    | PIN incorrect or missing  |
|57    | Used by switch when function requested is not allowed for product or card type |
| 58   | Transaction not allowed at terminal  |
| 59   | Suspected fraud  |
| 61   | Exceeds approval amount limit   |
|62    | Restricted card (card invalid in region or country)  |
| 63   | Security violation (source not correct issuer)  |
| 64   | Transaction does not fulfill AML requirement  |
| 65   | Exceeds withdrawal frequency limit|
| 70   | PIN data required|
| 74   | Different value than that used for PIN encryption errors|
| 75   | Allowable number of PIN-entry tries exceeded  |
| 76   | Unsolicited reversal-reversal with no original transaction in history. V.I.P. unable to match reversal request to an original message  |
| 78   |  Blocked, first used or special condition—new cardholder not activated or card is temporarily blocked |
| 79   | Reversed (by switch)  |
| 80   | No financial impact (used in reversal responses to declined originals)  |
| 81   | Cryptographic error found in PIN (used for cryptographic error condition found by security module during PIN decryption)  |
| 82   |  Negative online CAM, dCVV, iCVV, CVV, CAVV, dCVV2, TAVV, or DTVV results or Offline PIN authentication interrupted |
| 85   | No reason to decline a request for address verification, CVV2 verifi- cation, or credit voucher or merchandise return | 
| 86   | Cannot verify PIN; for instance, no PVV  |
| 91   | Issuer unavailable or switch inoperative (STIP not applicable or available for this transaction). Time-out when no STIP. Credit voucher and merchandise return authorizations: V.I.P. sent transaction to issuer, but issuer unavailable. Acquirers receiving code must send transactions again. Advices not created. Issuers can respond with this code, which V.I.P. passes to the acquirer without invoking STIP. Issuers use code to indicate they cannot perform authorization on issuer’s behalf.Causes decline at POS.  |
| 92   | Financial institution or intermediate network facility cannot be found for routing (receiving institution ID invalid)  |
|  93  |  Transaction cannot be completed- violation of law. |
|  94  |  Duplicate transmission. Transaction submitted containing values in tracing data fields that duplicate values in a previously submitted transaction. |
| 96   | System malfunction  |
| 1A   | Additional customer authentication required  |
| 6P   | Verification data failed  |
| B1   | Surcharge amount not permitted on Visa cards or EBT food stamps (U.S. acquirers only) |
| N0   | Force STIP. Issuers can respond with this, which routes transactions to STIP. Issuers use code when they cannot perform authorization but want STIP to perform it.  |
| N3   | Cash service not available  |
| N4   | Cash request exceeds issuer or approved limit  |
| N7   | Decline for CVV2 failure  |
| N8   | Transaction amount exceeds pre- authorized approval amount  |
| P5   | Denied PIN unblock-PIN change or unblock request declined by issuer  |
| P6   | Denied PIN change-requested PIN unsafe  |
| Q1   | Card authentication failed or Offline PIN authentication interrupted  |
| R0   | Stop payment order  |
| R1   | Revocation of authorization order  |
| R2   | Transaction does not qualify for Visa PIN  |
| R3   | Revocation of all authorizations order  |
| Z3   | Unable to go online; offline-declined  |

<!--
type: tab
title: Prosa
-->


| ISO Error Code  | Description  |
|---|---|
| 00  | Approved or completed successfully
| 01 | Refer to card issuer                                                                                                                                                 |
| 02 | Refer to special conditions for card issuer                                                                                                                          |
| 03 | Invalid merchant                                                                                                                                                     |
| 04 | Pick-up card                                                                                                                                                         |
| 05 | Do not honor                                                                                                                                                         |
| 06 | Error                                                                                                                                                                |
| 07 | Pick-up card, special condition                                                                                                                                      |
| 09 | Request in progress (duplicate)                                                                                                                                      |
| 10 | Approved partial                                                                                                                                                     |
| 11 | Approved (VIP) \*                                                                                                                                                    |
| 12 | Invalid transaction                                                                                                                                                  |
| 13 | Invalid amount                                                                                                                                                       |
| 14 | Invalid card number (no such number)                                                                                                                                 |
| 15 | No such issuer                                                                                                                                                       |
| 30 | Format error                                                                                                                                                         |
| 31 | Bank not supported by switch                                                                                                                                         |
| 33 | Expired card                                                                                                                                                         |
| 34 | Suspected fraud                                                                                                                                                      |
| 35 | Card acceptor contact acquirer                                                                                                                                       |
| 36 | Restricted card                                                                                                                                                      |
| 37 | Card acceptor call acquirer security                                                                                                                                 |
| 38 | Allowable PIN tries exceded                                                                                                                                          |
| 39 | No credit account                                                                                                                                                    |
| 41 | Lost card                                                                                                                                                            |
| 43 | Stolen card, pick-up                                                                                                                                                 |
| 51 | Not sufficient funds                                                                                                                                                 |
| 54 | Expired card                                                                                                                                                         |
| 55 | Incorrect personal identification number \*                                                                                                                          |
| 56 | No card record                                                                                                                                                       |
| 57 | Transaction not permitted to cardholder                                                                                                                              |
| 58 | Transaction not permitted to terminal                                                                                                                                |
| 61 | Exceeds withdrawal amount limit                                                                                                                                      |
| 62 | Restricted card                                                                                                                                                      |
| 65 | Exceeds withdrawal frequency limit                                                                                                                                   |
| 75 | Allowable number of PIN tries exceeded \*                                                                                                                            |
| 76 | Reserved for private use or Approved country club \*                                                                                                                 |
| 77 | Reserved for private use or Approved pending identification (sign paper draft)\*                                                                                     |
| 78 | Reserved for private use or Approved blind \*                                                                                                                        |
| 79 | Reserved for private use or Approved administrative transaction \*                                                                                                   |
| 80 | Reserved for private use or Approved national negative file hit OK \*                                                                                                |
| 81 | Reserved for private use or Approved commercial \*                                                                                                                   |
| 82 | Reserved for private use or No security module                                                                                                                       |
| 83 | Reserved for private use or No accounts                                                                                                                              |
| 84 | Reserved for private use or No PBF \*                                                                                                                                |
| 85 | Reserved for private use or PBF update error \*                                                                                                                      |
| 86 | Reserved for private use or Invalid authorization type                                                                                                               |
| 87 | Reserved for private use or Bad Track Data                                                                                                                           |
| 88 | Reserved for private use or PTLF error \*                                                                                                                            |
| 89 | Reserved for private use or Invalid route service                                                                                                                    |
| 91 | Cutoff is in process, a switch is ending business for a day and starting the 90 next (transaction can be sent again in a few minutes) Issuer or switch is inoperative |
| 92 | Financial institution or intermediate network facility cannot be found for routing                                                                                   |
| 94 | Duplicate transmission                                                                                                                                               |
| 96 | System malfunction                                                                                                                                                   |
| N0 | Reserved for private use or Unable to authorize                                                                                                                      |
| N1 | Reserved for private use or Invalid PAN length                                                                                                                       |
| N2 | Reserved for private use or Preauthorization full                                                                                                                    |
| N3 | Reserved for private use or Maximum online refund reached                                                                                                            |
| N4 | Reserved for private use or Maximum offline refund reached                                                                                                           |
| N5 | Reserved for private use or Maximum credit per refund                                                                                                                |
| N6 | Reserved for private use or Maximum refund credit reached                                                                                                            |
| N7 | Reserved for private use or Customer selected negative file reason                                                                                                   |
| N8 | Reserved for private use or Over floor limit                                                                                                                         |
| N9 | Reserved for private use or Maximum number refund credits                                                                                                            |
| O0 | Reserved for private use or Referral file full                                                                                                                       |
| O1 | Reserved for private use or NEG file problem \*                                                                                                                      |
| O2 | Reserved for private use or Advance less than minimum                                                                                                                |
| O3 | Reserved for private use or Delinquent                                                                                                                               |
| O4 | Reserved for private use or Over limit table                                                                                                                         |
| OS | Reserved for private use or PIN required \*                                                                                                                          |
| O6 | Reserved for private use or Mod 10 check                                                                                                                             |
| O7 | Reserved for private use or Force post                                                                                                                               |
| O8 | Reserved for private use or Bad PBF \*                                                                                                                               |
| O9 | Reserved for private use or NEG file problem \*                                                                                                                      |
| P0 | Reserved for private use or CAF problem \*                                                                                                                           |
| P1 | Reserved for private use or Over daily limit \*                                                                                                                      |
| P2 | Reserved for private use or CAPF not found \*                                                                                                                        |
| P3 | Reserved for private use or Advance less than minimum                                                                                                                |
| P4 | Reserved for private use or Number of times used                                                                                                                     |
| PS | Reserved for private use or Delinquent                                                                                                                               |
| P6 | Reserved for private use or Over limit table                                                                                                                         |
| P7 | Reserved for private use or Advance less than minimum                                                                                                                |
| P8 | Reserved for private use or Administrative card needed                                                                                                               |
| P9 | Reserved for private use or Enter lesser amount                                                                                                                      |
| Q0 | Reserved for private use or Invalid transaction date                                                                                                                 |
| Q1 | Reserved for private use or Invalid expiration date                                                                                                                  |
| Q2 | Reserved for private use or Invalid transaction code                                                                                                                 |
| Q3 | Reserved for private use or Advance less than minimum                                                                                                                |
| Q4 | Reserved for private use or Number of times used                                                                                                                     |
| Q5 | Reserved for private use or Delinquent                                                                                                                               |
| Q6 | Reserved for private use or Over limit table                                                                                                                         |
| Q7 | Reserved for private use or Amount over maximum                                                                                                                      |
| Q8 | Reserved for private use or Administrative card not found                                                                                                            |
| Q9 | Reserved for private use or Administrative card not allowed                                                                                                          |
| R0 | Reserved for private use or Approved administrative request performed in window \*                                                                                   |
| R1 | Reserved for private use or Approved administrative request performed out of window \*                                                                               |
| R2 | Reserved for private use or Approved administrative request performed anytime \*                                                                                     |
| R3 | Reserved for private use or Chargeback, customer file updated                                                                                                        |
| R4 | Reserved for private use or Chargeback, customer file updated, acquirer not found                                                                                    |
| R5 | Reserved for private use or Chargeback, incorrect prefix number                                                                                                      |
| R6 | Reserved for private use or Chargeback, incorrect response code or CPF configuration                                                                                 |
| R7 | Reserved for private use or Administrative transactions not supported                                                                                                |
| R8 | Reserved for private use or Card on national negative file \*                                                                                                        |
| S4 | PTLF full \*                                                                                                                                                         |
| S5 | Reserved for private use or Chargeback approved, customer file not updated                                                                                           |
| S6 | Reserved for private use or Chargeback approved, customer file not updated, acquirer not found                                                                       |
| S7 | Reserved for private use or Chargeback accepted, incorrect destination                                                                                               |
| S8 | Reserved for private use or ADMN file problem                                                                                                                        |
| S9 | Reserved for private use or Unable to validate PIN; security module is down \*                                                                                       |
| T1 | Reserved for private use or Invalid credit card advance amount                                                                                                       |
| T2 | Reserved for private use or Invalid transaction date                                                                                                                 |
| T3 | Reserved for private use or Card not supported                                                                                                                       |
| T4 | Reserved for private use or Amount over maximum                                                                                                                      |
| T5 | Reserved for private use or CAF status = 0 or 9 \*                                                                                                                   |
| T6 | Reserved for private use or Bad UAF \*                                                                                                                               |
| T7 | Reserved for private use or Cash back exceeds daily limit                                                                                                            |
| T8 | Reserved for private use or Invalid account                                                                                                                          |
| U0 | ARQC failure decline \*                                                                                                                                              |
| U1 | Security module parameter error \*                                                                                                                                   |
| U2 | Security module failure \*                                                                                                                                           |
| U3 | KEY1 record not found \*                                                                                                                                             |
| U4 | ATC check failure \*                                                                                                                                                 |
| U5 | CVR decline \*                                                                                                                                                       |
| U6 | TVR decline \*                                                                                                                                                       |
| U7 | Reason online code decline \*                                                                                                                                        |
| U8 | Fallback decline \*                                                                                                                                                  |
| V0 | ARQC failure referral \*                                                                                                                                             |
| V1 | CVR referral \*                                                                                                                                                      |
| V2 | TVR referral \*                                                                                                                                                      |
| V3 | Reason online code referral \*                                                                                                                                       |
| V4 | Fallback referral \*                                                                                                                                                 |
| V7 | ARQC failure capture \*                                                                                                                                              |
| V8 | CVR capture \*                                                                                                                                                       |
| V9 | TVR capture \*                                                                                                                                                       |
| 40 | Command rejected                                                                                                                                                     |
| R9 | Destination not available                                                                                                                                            |
| 17 | Customer cancellation                                                                                                                                                |
| 22 | Suspected malfunction                                                                                                                                                |
| S0 | Suspect reversal                                                                                                                                                     |
| 68 | Response received too late                                                                                                                                           |
| 64 | Original amount incorrect                                                                                                                                            |
| S1 | Suspicious reversal override                                                                                                                                         |
| S2 | Misdispense reversal                                                                                                                                                 |
| 95 | Reconcile error          

<!-- type: tab-end -->

