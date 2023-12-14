# Change the IMEI

Changing the IMEI is a `two-step` process.
<procedure>
<step> The first step is to generate an OTP for the User who wants to change the IMEI. This OTP will be stored in a database inorder to cross verify it in the next step</step>
<step> The next step is to get the new IMEI and change it in the main database - `UserDetails`.
Also, the database `UserChangesDetails` would also be updated with the necessary changes</step>
</procedure>

## API Calls

### API Address

The API address is :
`http://<IP Address>/user/api/changeIMEI/`

### Generating the OTP {collapsible="true"}

<warning> This part has not been implemented as of right now</warning>

#### Input JSON

```JSON
{
  "message": "generateOTP"
}
```

#### Output

The output would be an HTTP response with the value `OK`

### Verifying the OTP and Changing the IMEI {collapsible="true"}

<warning> This part has not been tested properly</warning>

#### Input JSON {id="input-json_1"}

```JSON
{
  "message": "verifyOTP",
  "userID": "<UserID>",
  "OTP": "<The OTP that the user has entered>",
  "IMEI": "<The new IMEI of  the User>"
}
```

#### Output { id="output_1"}

The output would be an HTTP response with the value `OK`