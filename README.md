# Umbrella SMS Gateway API Documentation

Umbrella Ltd provides a service allowing users to send an SMS messages via an API (Application Programming Interface).

The API is very simple to use and consists of the following 2 endpoints/functions:

 - [Login](#login-post)
 - [Send SMS](#send-sms-post)

## Base URL
The base URL for all the endpoints is as follows
    
    https://umbrellasmsengine.azurewebsites.net

## Login (POST)
### Path

    {base URL}/token

### Headers

    {"Content-Type": "application/x-www-form-urlencoded"}

### Parameters
This function requires no URL parameters

### Body

    {
    "username" : "example@website.com",
    "password" : "P@$$W0RD",
    "grant_type" : "password"
    }

### Response

    {
        "access_token": "k6o7bGKYp-vzweBcz7V6_KM9GblqmAu1WnlNF1Prm4NfmFIB7GbB4ru_TCxVUPZMYpYMmEATXGbtXkAyhrdSkAMyvbdy0Xv4_8IWYGo80_HnuTySge8qgcOcRYlqOQZ-C0cckNhcI-Jbcrkw5CWfw0Lz2IL2Wgsp-wg_-KrnePmfOZxe3n3D0GVdjtaHUuLsdB935VGTiuwV5UYA0x3QHwrsNidRT2LJUV7Nd6Kcyxsvj2lTq9Ggdf0SbDPAzVEHGKmCO3YI47a-nO-jOMHtNlkghltHUONjdkgAAwonvF5lusjElGBNnAHrIU1JzdxqxFo66H_rWlg9PDAJ51lsxPrENBkEHyWzJopuaSD029eUUW-zRBgySjwjJaTddjxNiwfG135Z8ofnU8nTyOBveA08papboLT0iiag8LTSqrN14n03WtH-SLvIti_1d-DSOV4KqSS7U2OxVv2aglKx2BQYhwSHejEv_si_IL_tykN3NVgZlrZh5lzYOIQiKKvI",
        "token_type": "bearer",
        "expires_in": 1209599,
        "userName": "UMSSandBox@umbrella.ly",
        ".issued": "Wed, 19 May 2021 15:48:12 GMT",
        ".expires": "Wed, 02 Jun 2021 15:48:12 GMT"
    }

## Send SMS (POST)
### Path

    {base URL}/api/SendSMSFromGW

### Headers
    
    {
    "Content-Type": "application/json",
    "Authorization": "Bearer QUof6egyxj0Y5uwdUd52wCI_KUHQ5nfAcJTnoktIOgkbhfAK2uFlomkRaA6umplAftu09Q4p1C-rkxcrkk8OFISPOnAFKnCFjYrrHmmANNkSb--WmlsdKGeEBOmzxvazROhQ8ho-Gl_wCFpg6S_hTkG5S3cDa1l9hucSY8ePKI99qsAD5B87Qhh17Ck0h2vhG-w4y2prYcNVLJwUjroZrIrj-Nm9yAnZjjrj9nAK9WMFLDd4bYgKbZ6FQr57nHtqpMjpaN0bk9QxtmWfSdphZ8FKFJhcVlOwKgeQX7rMleooiRN16ghPAKqpPNjsBSjsNZU_6aT4DEJOEzAtbvlwxN6Qw2ouepR8t6d2tl1AU1jnO51us7Q9B7TeBomesPUi5susm9qRjujV8-3OLvfYsetGAGMlBQqJn9FXrL-kUMPEUnPkejsTxJ410xHb_4_6vIIDlQkdP_oCzfN5AG0PqAzt5z1xZqUcrUSZ8qcrElLCTz_fhmJtdGPhTDci5gZu"
    }

### Parameters
This function requires no URL parameters

### Body
This function requires the following body parameters

    {
    "APIKey", "80e29ea0-67c8-4fb1-b4f7-7f53611d59ac",
    "PhoneNumber" : 218916222566,
    "msg" : "This is a test message",
    "sender_name" : "Umbrella Developer"
    }

where `APIKey` is a unique string associated to each account and will be provided along with the username and password.

### Response
If successful, the response will be as follows:

    {
        "MsgState": 2
    }
