# Login

This API is to check if the User ID and the Password Matches.

## API Address

The API address is : `http://<IP Address>/user/api/login/`

## Input JSON {collapsible="true"}

```JSON
{
  "userID": "<User ID of the User>",
  "password": "<Password of the User>",
  "IMEI": "<IMEI number of the phone>",
  "location": "<latitude,longitude> Eg: 1.345,48.23"
}
```

## Output JSON {collapsible="true"}

```JSON
{
  "status": "<Status Message>"
}
```

| Status Message             | Meaning                                                                     |
|----------------------------|-----------------------------------------------------------------------------|
| User Verified Successfully | The UserID, Password, Location and the IMEI have successfully been verified |
| Invalid UserID             | The User ID is not found in the database                                    |
| Invalid Password           | The password is invalid                                                     |
| Invalid Location           | The location of the user is not near the expected location of the User      |
| Invalid IMEI               | The registered IMEI number does not match with the IMEI given by the user   |
| Server Error               | An Unknown Error from the Server Side                                       |


