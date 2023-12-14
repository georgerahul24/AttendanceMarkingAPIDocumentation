# Database Schema

The databases used are:

## QRCode Details

This database is used to manage the generated QR Codes
Here is the DDL for the database

```SQL
create table QRCode_qrcodedetails
(
    id             integer      not null primary key autoincrement,
    userAssignedTo varchar(100) not null,
    stringData     varchar(100) not null,
    timestamp      datetime     not null,
    verified       bool         not null
);
```

## User Details

This stores all the details about the user. The password is not salted nor hashed in this.

```SQL
create table UserDetails_userdetails
(
    userID                 integer      not null  primary key,
    password               varchar(100) not null,
    phoneNumber            integer      not null,
    IPAddressOfTheComputer varchar(40)  not null,
    IMEI                   varchar(100) not null,
    location               varchar(100) not null,
    faceEncoding           BLOB
);
```

## Login Details

This stores all the successful login details

```SQL
create table UserDetails_logindetails
(
    id                                      integer      not null
        primary key autoincrement,
    userID                                  integer      not null,
    dateAndTime                             varchar(100) not null,
    location                                varchar(100) not null,
    locationDistanceFromTheExpectedDistance real         not null,
    IMEI                                    varchar(100) not null,
    faceMatchPercentage                     real         not null
);
```

## Invalid Login Details

This stores all the details of invalid logins

```SQL
(
    id                                      integer      not null
        primary key autoincrement,
    userID                                  integer      not null,
    dateAndTime                             varchar(100) not null,
    location                                varchar(100) not null,
    locationDistanceFromTheExpectedDistance real         not null,
    receivedIMEI                            varchar(100) not null,
    expectedIMEI                            varchar(100) not null,
    faceMatchPercentage                     real         not null,
    errorMessage                            varchar(100) not null
);
```

## User Changes Details

When the user changes any personal information, it is reflected here,

```SQL
create table UserDetails_userchangesdetails
(
    id              integer      not null
        primary key autoincrement,
    userID          integer      not null,
    dateAndTime     varchar(100) not null,
    oldIMEI         varchar(100) not null,
    newIMEI         varchar(100) not null,
    oldLocation     varchar(100) not null,
    newLocation     varchar(100) not null,
    oldFaceEncoding BLOB,
    newFaceEncoding BLOB
);
```