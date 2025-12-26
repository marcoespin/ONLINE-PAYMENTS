# Kushki API errors

Learn about common mistakes and how to solve them.

## HTTP Status Codes

Kushki will be able to return different HTTP status codes depending on the requests made. Below are the most common HTTP status codes, their associated standard message, as well as a more detailed description of the response.

| Code     | Message     | Detail     |
| ---------- | ---------- | ---------- |
| 200      | OK       | The process was successful. Everything worked as expected, according to the HTTP method      |
| 400      | Bad Request       | The server cannot interpret the request (incorrect syntax, too large size, missing parameters)       |
| 401       | Authorization Required       | Credentials must be authenticated, or authentication has failed       |
| 403       | Forbidden       | Do not have the necessary permissions to perform this action       |
| 404       | Not Found       | Resource or page not found       |
| 409       | Conflict       | The request cannot be processed because of a conflict with the resource (e.g., multiple simultaneous updates)      |
| 410       | Gone       | The requested resource has been deleted from the server, and will no longer be available     |
| 429       | Too Many Requests       | Too many requests have been sent in a short period of time       |
| 430       |  Request Header Fields Too Large    | Unofficial code, applies only to Shopify. Similar to code 429      |
| 500       | Internal Server Error       | An unexpected server-side error occurred       |
| 502       | Bad Gateway       | The server (acting as a proxy or gateway) received an invalid response from another server       |
| 503       | Service Temporarily Unavailable       | The server is unavailable (usually because it is under maintenance, or because it is overloaded)       |
| 504       | Gateway Timeout       | The server (acting as a proxy or gateway) has not received a response from the other server in time     |

## Codes Returned by the API

**Note**:  For a complete reference of the error codes you might receive in credit card transactions, please refer to [Error codes](https://docs.kushkipagos.com/co/getting-started/error-codes).

| **Code** | **Response Text (Spanish)**                                       | **Description**                                                                                                                                              |
| :------: | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|    004   | INFORMACIÓN DE CUENTA NO VÁLIDA                                   | If any card detail is invalid, then this error occurs.                                                                                                       |
|    005   | NÚMERO DE CUENTA NO VÁLIDO                                        | If the account number (Card Number) is not valid, then this error occurs.                                                                                        |
|    006   | TRANSACCIÓN RECHAZADA                                             | When the transaction is declined from the processor, then this error occurs. Comes with different sets of messages depending on the error.                   |
|    007   | CVC NO VÁLIDO                                                     | If the card CVV is not valid, then this error occurs.                                                                                                        |
|    017   | TARJETA NO VÁLIDA                                                 | When the card number is not valid, then this error occurs.                                                                                                   |
|    018   | TARJETA VENCIDA                                                   | When an expired card is used, then this error occurs.                                                                                                         |
|    019   | FONDOS INSUFICIENTES PARA REMBOLSOS                               | When the refund transaction comes with more than the charge transaction, then this error occurs.                                                      |
|    022   | TIPO DE TARJETA NO COMPATIBLE POR MRC                             | When the card type is disabled in the store setup and if the transaction comes with that card, then this error occurs.                                       |
|    023   | FECHA DE EXPIRACIÓN NO VÁLIDA                                     | When the expiry date is invalid, then this error occurs.                                                                                                     |
|    201   | ID DE COMERCIO NO VÁLIDO                                          | When the merchant ID is invalid, then this error occurs.                                                                                                     |
|    202   | TIPO DE TRANSACCIÓN NO VÁLIDO                                     | When the transaction type is not valid, then this error occurs.                                                                                              |
|    203   | MONTO DE TRANSACCIÓN NO VÁLIDO                                    | When the transaction amount is invalid, then this error occurs.                                                                                              |
|    205   | TIPO DE MONEDA NO VÁLIDA                                          | When the transaction currency code is invalid, then this error occurs.                                                                                       |
|    207   | ID DE TRANSACCIÓN NO VÁLIDO                                       | When the transaction ticket number is invalid, then this error occurs.                                                                                       |
|    211   | SOLICITUD NO VÁLIDA                                               | If the request is not in proper format eg. Unencrypted, Invalid JSON                                                                                         |
|    212   | INFORMACIÓN ENCRIPTADA NO VÁLIDA                                  | When the encrypted request is not valid, then this error occurs.                                                                                             |
|    215   | EL COMERCIO NO TIENE PERMISO PARA PROCESAR UNA TRANSACCIÓN        | When we disable a transaction from the store setup, then this error occurs.                                                                                  |
|    216   | TRANSACCIÓN REEMBOLSADA                                           | When a refund transaction occurs after it is already refunded, then this error occurs.                                                                       |
|    219   | EL MONTO ES CERO                                                  | When the amount is zero in request, this error occurs.                                                                                                       |
|    220   | MONTO DE LA TRANSACCIÓN ES DIFERENTE AL MONTO DE LA VENTA INICIAL | When the transaction amount in token, charge or init doesn't match, then this error occurs.                                                                  |
|    222   | TRANSACCIÓN NO ENCONTRADA                                         | When the transaction ticket number is not found in our database then this error occurs.                                                                      |
|    223   | TRANSACCIÓN NO SOPORTADA                                          | When the transaction is not supported by either Kushki or processor, then this error occurs                                                                  |
|    225   | TIPO DE TRANSACCIÓN NO VÁLIDO                                     | When the transaction type is not valid, then this error occurs.                                                                                              |
|    226   | PROCESADOR CC NO ASIGNADO                                         | When the credit processor is not assigned to the merchant at the time of store setup, then this error occurs.                                                     |
|    228   | PROCESADOR INALCANZABLE                                           | When we are unable to connect to the processor, then this error occurs.                                                                                      |
|    229   | EL COMERCIO NO SOPORTA LA TRANSACCIÓN                             | When the transaction is not supported by the merchant, then this error occurs.                                                                               |
|    231   | ANULACIÓN DE VENTA NO PERMITIDA                                   | When a void of a sale transaction is performed after refunding the same sale transaction, then this error occurs.                                            |
|    238   | TRANSACCÓN ANULADA                                                | When a void of an already voided transaction is performed, then this error occurs.                                                                              |
|    277   | INDICADOR DE IDIOMA NO VÁLIDO                                     | When the language indicator is invalid, then this error occurs.                                                                                                  |
|    322   | TRANSACCIÓN NO PERMITIDA                                          | When a transaction is not allowed by a merchant, then this error occurs.                                                                                      |
|    478   | SERVIDOR NO DISPONIBLE                                            | When there is some connectivity issue with the server, then this error occurs.                                                                               |
|    509   | EL MONTO INGRESADO ES MAYOR O MENOR A LO PERMITIDO                | When the amount of the transaction is less or greater than the amount allowed, then this error occurs.                                                       |
|    577   | EL TOKEN DE LA TRANSACCIÓN NO ES VÁLIDO                           | When the transaction token is invalid or doesn’t exist in the database, then this error occurs.                                                                  |
|    578   | EL TOKEN DE LA TRANSACCIÓN HA EXPIRADO                            | When the transaction is tried after 30 min of token transaction or when the transaction token is reused for a different transaction, then this error occurs. |
|    579   | TRANSACCIÓN RECHAZADA                                             | When we are unable to process the request, then this error occurs.                                                                                           |
|    597   | NO HAY RESPUESTA DEL PROCESADOR                                   | When we don’t receive any response from the processor, then this error occurs.                                                                                |
|    701   | EL TOKEN DE LA TRANSACCIÓN ES REQUERIDO                           | When the transaction token is not given in the sale transaction, then this error occurs.                                                                     |
|    702   | EL MONTO DE LA TRANSACCIÓN NO ES VÁLIDO                           | When invalid amount is entered, then this error occurs.                                                                                                      |
|    703   | EL MONTO DE LA TRANSACCIÓN ES REQUERIDO                           | When the transaction amount is not entered, then this error occurs.                                                                                              |
|    704   | EL NÚMERO DE TICKET DE LA TRANSACCIÓN NO ES VÁLIDO                | When an invalid ticket number is entered, then this error occurs.                                                                                            |
|    705   | EL NÚMERO DE TICKET DE LA TRANSACCIÓN ES REQUERIDO                | When the ticket number is not entered, then this error occurs.                                                                                               |
|    706   | LA CANTIDAD DE MESES ES REQUERIDA                                 | When the number of months is not entered in the deferred transaction, then this error occurs.                                                                |
|    707   | LA CANTIDAD DE MESES NO ES VÁLIDA                                 | When an invalid number of months is entered in the deferred transaction, then this error occurs.                                                             |
|    710   | EL COMERCIO NO HA SIDO ENCONTRADO                                 | When the merchant is not found, then this error occurs.                                                                                                      |
|    890   | DATOS NO ENCONTRADOS                                              | When there is no data for the cookie, then this error occurs.                                                                                                |
|   1000   | EL ID DE LA TARJETA ES REQUERIDA                                  | When the card token is not entered, then this error occurs.                                                                                                      |
|   1001   | EL TOKEN DE LA TARJETA NO ES VÁLIDO                               | When the card token entered is not valid, then this error occurs.                                                                                                |
|   1002   | EL NOMBRE DEL CONSUMIDOR ES REQUERIDO                             | When the customer first name is not entered, then this error occurs.                                                                                             |
|   1003   | EL NOMBRE DEL CONSUMIDOR NO ES VÁLIDO                             | When the customer first name entered is not valid, then this error occurs.                                                                                       |
|   1004   | EL APELLIDO DEL CONSUMIDOR ES REQUERIDO                           | When the customer last name is not entered, then this error occurs.                                                                                              |
|   1005   | EL APELLIDO DEL CONSUMIDOR NO ES VÁLIDO                           | When the customer last name entered is not valid, then this error occurs.                                                                                        |
|   1006   | NOMBRE DEL PLAN ES REQUERIDO                                      | When the plan name is not entered, then this error occurs.                                                                                                       |
|   1007   | NOMBRE DEL PLAN NO ES VÁLIDO                                      | When the plan name entered is not valid, then this error occurs.                                                                                                 |
|   1008   | FECHA DE INICIO ES REQUERIDA                                      | When the start date is not entered, then this error occurs.                                                                                                      |
|   1009   | FECHA DE INICIO NO ES VÁLIDA                                      | When the start date entered is not valid, then this error occurs.                                                                                                |
|   1014   | EL TIPO DE AJUSTE NO ES VÁLIDO                                    | When the adjustment type entered is not valid, then this error occurs.                                                                                           |
|   1015   | LA FECHA DE AJUSTE NO ES VÁLIDA                                   | When the adjustment date entered is not valid, then this error occurs.                                                                                           |
|   1016   | EL MONTO DE AJUSTE NO ES VÁLIDO                                   | When the adjustment amount entered is not valid, then this error occurs.                                                                                         |
|   1017   | LOS PERIODOS DE AJUSTE NO SON VÁLIDOS                             | When adjustment periods entered are not valid, then this error occurs.                                                                                        |
|   1018   | NO ES POSIBLE AGREGAR SUBSCRIPCIÓN                                | When some network error occurs while inserting subscription then this error occurs.                                                                          |
|   1019   | TOKEN DE SUBSCRIPCIÓN NO ENCONTRADO                               | When the subscription token is not present in the database, then this error occurs.                                                                          |
|   1020   | ERROR EN LA CREACIÓN DE LA SUBSCRIPCIÓN                           | When some error occurs while creating the subscription, then this error occurs.                                                                              |
|   1021   | EL ID DE SUBSCRIPCIÓN ES REQUERIDO                                | When the ubscription id is not entered, then this error occurs.                                                                                                 |
|   1022   | EL ID DE SUBSCRIPCIÓN NO ES VÁLIDO                                | When the subscription id entered is not valid, then this error occurs.                                                                                           |
|   1023   | EL CAMPO "PLANID" NO ES VALIDO                                    | When the plan id entered is not valid, then this error occurs.                                                                                                   |
|   1024   | LA FECHA DE FINALIDAD NO ES VÁLIDA                                | When the end date entered is not valid, then this error occurs.                                                                                                  |
|   1025   | DIA DEL MES NO ES VÁLIDO                                          | When the day of month entered is not valid, then this error occurs.                                                                                              |
|   1026   | ERROR AL ELIMINAR LA SUBSCRIPCIÓN                                 | When the cancel subscription fails, then this error occurs.                                                                                                 |
|   1027   | ID DE SUBSCRIPCIÓN NO ENCONTRADO                                  | When the subscription id is not present in the database, then this error occurs.                                                                                 |
|   1028   | ERROR AL ACTUALIZAR LA SUBSCRIPCIÓN                               | When the update subscription fails, then this error occurs.                                                                                                 |
|   1029   | TOKEN DE SUBSCRIPCIÓN EXPIRADO                                    | When the token is in use, then this error occurs.                                                                                                            |
|   1031   | LA FECHA DE FIN ES REQUERIDA                                      | When the end date is invalid, then this error occurs.                                                                                                        |
|   1032   | NO HAY SUSCRIPCIONES PARA ID DE COMERCIO                          | When the subscriptions are not there in the database for the requested merchant id, then this error occurs.                                                      |
|   1033   | AJUSTE NO VÁLIDO: MONTO SUBTOTALIVA                               | When the SUBTOTAL_IVA amount in adjustment Amount Object us invalid, then this error occurs.                                                                 |
|   1034   | AJUSTE NO VÁLIDO: MONTO IVA                                       | When the IVA amount in adjustment Amount Object is invalid, then this error occurs.                                                                          |
|   1035   | AJUSTE NO VÁLIDO: MONTO SUBTOTALIVA0                              | When the SUBTOTAL_IVA0 amount in adjustment Amount Object is invalid, then this error occurs.                                                                |
|   1036   | AJUSTE NO VÁLIDO: MONTO ICE                                       | When the ICE amount in adjustment Amount Object is invalid, then this error occurs.                                                                          |

| **Code** | **Message (Spanish)**                 | **Description**                                                                                                          |
| :------: | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
|   K001   | EL CUERPO DE LA PETICIÓN ES INVÁLIDO  | Malformed body                                                                                                           |
|   K002   | HA OCURRIDO UN ERROR INESPERADO       | An unidentified error has occurred, contact support.                                                                     |
|   K003   | TARJETA NO HABILITADA POR EL EMISOR   | Disabled BIN for eCommerce                                                                                               |
|   K004   | ID DE COMERCIO O CREDENCIAL NO VÁLIDO | The merchant login ID is invalid                                                                                         |
|   K005   | TOKEN EXPIRADO                        | Token is expired or reused for a different transaction                                                                   |
|   K006   | MONTO NO ES IGUAL AL ESPERADO         | The entered amount is different to the charged amount.                                                                   |
|   K007   | ESTE RECIBO YA FUE PAGADO             | Receipt has been paid                                                                                                    |
|   K008   | ESTE RECIBO YA FUE CANCELADO          | Receipt has been canceled                                                                                                |
|   K009   | RECIBO EXPIRADO                       | Receipt expired                                                                                                          |
|   K010   | TICKET NUMBER INVÁLIDO                | Ticket number is not entered properly in the request                                                                     |
|   K011   | CREDENCIALES INVÁLIDAS                | When the credentials are not correct, then this error occurs                                                             |
|   K012   | ACCESO NO AUTORIZADO                  | Authentication token is out of date or incorrect                                                                         |
|   K013   | TRANSACCIÓN TOKENIZADA COMO DIFERIDO  | The token request is set for a deferred transaction, but the deferred information is not included in the charge request. |
|   K014   | TOKEN INVÁLIDO                        | The transaction token used is not the correct one                                                                        |
|   K015   | Transacción no permitida sin ccv2. | The cvv must be sent or the merchant configuration must be verified to send recurring charges without cvv  |
|   K020   | TRANSACCIÓN RECHAZADA                 | When we are unable to process the transaction, then this error occurs                                                    |
|   K021   | TRANSACCIÓN RECHAZADA                 | When the transaction is declined by the anti-fraud system, then this error occurs                                        |
|   K023   | MONTO DEL VOID SUPERIOR AL DEL SALE   | This message appears when the amount of the partial void is higher than the sale amount                                  |
|   K055   | Tipo de moneda no permitido                 | Currency type sent in the request is not valid for the country of the merchant.                         |
|   K322   | TRANSACCIÓN RECHAZADA                 | When we are unable to process the transaction because of a security rule, then this error occurs                         |
|   K325   | Autenticación externa fallida - Datos enviados por comercio no son seguros                 | Insecure 3DS transaction without `acceptRisk` field set to `true`                         |
|   K505   | La transacción fue declinada por el procesador o emisor. | Card blocked. Use a different card. |
|   K555   | Solicitud enviada no es válida | Check that the required information is sent correctly. |

### Chargebacks Error Responses

| **Code** | **Message (Spanish)**                 | **Description**                                                                                                          |
| :------: | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| CCH001   | Cuerpo de la petición inválido.  | Malformed body |
| CCH010   | Fechas inválidas  | Invalid dates entered when obtaining the list of chargebacks |

### Get transaction List Error Responses

| **Code** | **Message (Spanish)**                 | **Description**                                                                                                          |
| :------: | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| ANL001   | Cuerpo de la petición inválido.  | Malformed body |
| ANL005   | Error en la consulta | Filters used to query the transactions might be wrong |

### Transfer out

In case there is a problem with a transfer disbursement, the Kushki API will return an error code and message.

| **Code** | **Message (Spanish)**                 | **Description**                                                                                                          |
| :------: | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| PT001   | Cuerpo de la petición inválido.  | Check that the information sent is in accordance with the [documentation](https://api-docs.kushkipagos.com/docs/online-payments/transfer-out/operations/create-a-payout-transfer-v-1-token).|
| PT007   | El comercio no existe  | Merchant doesn't exist. Please enter a valid merchant id.|
| PT008   | El comercio no existe  | Merchant doesn't exist. Please enter a valid merchant id.|
| PT0013   | Número de documento no válido  | Invalid document number|
| PT0015   | Número de cuenta inválido  | Invalid account number|
| PT057   | La moneda enviada es diferente a la definida por el procesador. | Check the currency sent. |

For Peru, there are response codes `006` and `002`. Below, we show the possible error messages returned in the `responseText` field.

| **responseCode** | **responseText**                 | 
| :------: | ------------------------------------- |
| 002   | IDC DIFIERE CON EL DE LA CNTA   |
| 006   | Cuenta destinatario inhabilitada para recibir abonos   |
| 006   | Cuenta de beneficiario incorrecta    |
| 006   | Cuenta de beneficiario cerrada   |
| 006   | Monto excede máximo permitido   |
| 006   | Servicio no disponible  |
| 006   | Saldo insuficiente   |
| 006   | Banco de beneficiario incorrecto   |
| 006   | Error de procesamiento   |
| 006   | Mensaje de BCP en el archivo    |
| 006   | Identificación de beneficiario incorrecta    |
| 006   | Cuenta e identificación de beneficiario no coinciden     |
| 006   | Declinado por el procesador     |


## Error codes during branch creation token

Kushki will be able to return different error messages while requesting a token to create or edit a branch. The response will look like the following example:

```json
{
  "code": "E001",
  "message": "Usuario o Contraseña incorrecto."
}
```

In the table below, generic error codes returned through the `code` field are summarized.

| Code     | Message     | Detail     |
| ---------- | ---------- | ---------- |
| E001      | Usuario o Contraseña incorrecto.      | Wrong username or password. |
| E015      | Usuario bloqueado, favor de ingresar a la consola para solicitar desbloqueo | More than 5 failed attempts to request a token |


## Error codes during branch creation requests

Kushki will be able to return different error messages while requesting the creation or edition of a branch. The response will look like the following example:

```json
{
    "code": "E006",
    "details": {
        "Origin": "validation process Service",
        "Message": "Error al validar los campos.",
        "Error": [
            "Correo electrónico incorrecto: 'PspNotificationEmail bcom'"
        ]
    },
    "message": "Error al validar los campos."
}
```

In the table below, generic error codes returned through the `code` field are summarized.

| Code     | Message     | Detail     |
| ---------- | ---------- | ---------- |
| E003      | Se superó el máximo de branches permitido      | Branch limit (500 per request) was exceeded (500)      |
| E007      | Registro duplicado       | Duplicate branches in request or in database       |
| E006     | Error al validar los campos       | Error validating fields or required missing field.     |

### E006 Error 

This error occurs when there is a invalid, missing field or the character limit was exceeded. Below you will find some examples of this error:

 Message     | Error     | Detail    |
| ---------- | ---------- |---------- |
| Error al validar los campos      | la propiedad Branches[0].Shareholder debe tener al menos un elemento      | The `shareHolder` field is required
|  Error al validar los campos       | la propiedad `ClientType` solo permite los siguientes elementos `KUSHKI MUNDIAL` `LATAM`      | The `ClientType` value is incorrect
| Error al validar los campos       | Fecha inválida: 'ReportingDate 01-Ma022'    | The date entered is incorrect
| Error al validar los campos       | Límite permitido superado: 'PspName(50) pspNamepspNamep     |Character limit for the field was exceeded
| Error al validar los campos       | Correo electrónico incorrecto: 'PspNotificationEmail bcom'     |Email entered is invalid
| Error al validar los campos       |La propiedad Branches[0].ConcurrenceNeeded solo permite los siguientes elementos 'Y' 'N'     |Values must be sent as `Y` or `N`

## Error codes during branch updating requests

Kushki will be able to return different error messages while requesting the creation or edition of a branch. The response will look like the following example:

```json
{
    "code": "E014",
    "details": {
        "Origin": "ValidationProcessService",
        "Message": "",
        "Error": [
            "20000000107724194060"
        ]
    },
    "message": "No se encuentran coincidencias con la información proporcionada."
}
```

In the table below, generic error codes returned through the `code` field are summarized.

| Code     | Message     | Detail     |
| ---------- | ---------- | ---------- |
| E003      | Se superó el máximo de branches permitido      | Branch limit (500) was exceeded (500)      |
| E014      | No se encuentran coincidencias con la información proporcionada      | The branchid does not exist      |
| E006     | Error al validar los campos       | There is a required missing field     |

### E006 Error

This error occurs when there is a invalid, missing field or the character limit was exceeded. Below you will find some examples of this error:

 Message     | Error     | Detail    |
| ---------- | ---------- |---------- |
| Error al validar los campos      | la propiedad Branches[0].Shareholder debe tener al menos un elemento      | The `shareHolder` field is required
|  Error al validar los campos       | la propiedad `ClientType` solo permite los siguientes elementos `KUSHKI MUNDIAL` `LATAM`      | The `ClientType` value is incorrect
| Error al validar los campos       | Fecha inválida: 'Branches[0].LegalRepresentative[0].BirthDate 02022'    | The date entered is incorrect
| Error al validar los campos       | Branches[0].LegalRepresentative[0].ResidencyCountry: El código del país deber pertenecer a la ISO 3166-1 alpha-3     |Country codes must be entered according to ISO 3166-1 alpha-3
| Error al validar los campos       | Correo electrónico incorrecto: 'PspNotificationEmail bcom'     |Email entered is invalid
| Error al validar los campos       |La propiedad Branches[0].ConcurrenceNeeded solo permite los siguientes elementos 'Y' 'N'     |Values must be sent as `Y` or `N`