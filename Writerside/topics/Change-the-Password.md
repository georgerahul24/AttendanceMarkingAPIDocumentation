# Change the Password

Changing the password is a `two-step` process.
<procedure>
<step> The first step is to generate an OTP for the User who wants to change the password. This OTP will be stored in a database inorder to cross verify it in the next step</step>
<step> The next step is to get the new password and change it in the main database - `UserDetails`</step>
</procedure>

## API Calls

### API Address

The API address is :
`http://<IP Address>/user/api/changePassword/`

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

### Verifying the OTP and Changing the Password {collapsible="true"}

<warning> This part has not been tested properly</warning>

#### Input JSON {id="input-json_1"}

```JSON
{
  "message": "verifyOTP",
  "userID": "<UserID>",
  "OTP": "<The OTP that the user has entered>",
  "password": "<The new Password for the User>"
}
```

#### Output { id="output_1"}

The output would be an HTTP response with the value `OK`