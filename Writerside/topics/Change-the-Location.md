# Change the Location

Changing the Location is a `two-step` process.
<procedure>
<step> The first step is to generate an OTP for the User who wants to change the location. This OTP will be stored in a database inorder to cross verify it in the next step</step>
<step> The next step is to get the new Location and change it in the main database - `UserDetails`.
Also, the database `UserChangesDetails` would also be updated with the necessary changes</step>
</procedure>

## API Calls

### API Address 

The API address is : 
`http://<IP Address>/user/api/changeLocation/` 

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

### Verifying the OTP and Changing the Location {collapsible="true"}

<warning> This part has not been tested properly</warning>

#### Input JSON {id="input-json_1"}

```JSON
{
  "message": "verifyOTP",
  "userID": "<UserID>",
  "OTP": "<The OTP that the user has entered>",
  "Location": "<The new Location of  the User>"
}
```

#### Output { id="output_1"}

The output would be an HTTP response with the value `OK`