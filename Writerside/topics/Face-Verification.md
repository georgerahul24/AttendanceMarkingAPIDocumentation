# Face Verification

This module is used to verify the face of the user by comparing his default encoding.
It is also to be noted that when a login is successful, it will be saved in the database also.

## API Address

The API address to verify the Face is : `http://<IP Address of the Server>/faceVerification/api/verifyFace/`

## Input JSON

<tldr>
    <p>It must be noted that the face image must be send in the request as a FILE. The easiest way to do this 
is to make sure that the HTTP Request  is multipart and attach the file in the multipart section.</p>
</tldr>
<tip>Make sure that the image has been properly rotated before sending the image to the server. For this, use the xcif data that are provided when clicking the photo.
In some phones like samsung and motorola, the image would be rotated 90 degrees before sending. While in Mi phones, the image is send without any rotations.
So, make sure that the photos are normalised before sending it to the server</tip>

```JSON
{
  "userID": "<User ID of the User>",
  "location": "<Current location of the User>",
  "faceImage": "<The image file attached in the multi part section",
  "IMEI": "<IMEI Number of the Registered Phone>"
}
```

## Output JSON

```JSON
{
  "status": "<status message>"
}
```

| Status Message   | Meaning                                                                             |
|------------------|-------------------------------------------------------------------------------------|
| Face Matched     | The face matched successfully                                                       |
| Face Mismatch    | The face has not been matched properly                                              |
| Location Invalid | The location of the user and default location expected from the User does not match |