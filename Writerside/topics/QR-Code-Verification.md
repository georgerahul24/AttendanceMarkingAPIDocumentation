# QR Code Verification

This API is used to verify the QR Code. It verifies how many times the QR Code
has already be scanned. Verification also involves where the location of QR Code and the User is.

## API Address

The API Address to verify the QR Code is: `http://<IP Address of the Server>/qrVerifier/api/verifyQR`

## Input JSON

```JSON
{
  "userID": "<User ID of the User>",
  "QRCode": "<The string that we get after decoding the QR Code>",
  "location": "<The location where the user scanned the qr code>",
  "IMEI": "<IMEI Number of the phone>"
}
```

## Output Json

```JSON
{
  "status": "<Status Message>"
}
```

| Status Message      | Meaning                                                       |
|---------------------|---------------------------------------------------------------|
| Success             | The QR Code was verified successfully                         |
| Expired             | The QR Code expired due to time                               |
| Invalid  QR         | The QR Code is invalid. Wrong QR Code might have been scanned |
| Mismatched Location | The location of the QR and the User does not match            |
| Server Error        | Some internal error in the server                             |
| Mismatched UserID   | The QR Code is not assigned to this User                      |

