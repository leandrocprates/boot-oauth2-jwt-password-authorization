# boot-oauth2-jwt-password-authorization
Authorization Server Utilizando JWT 

Nesse Projeto A geração de Token é feita utilizando o <b>JWT</b> 


Collection PostMan no diretorio : src/main/resources/collection_postman


URL POST : http://localhost:8080/oauth/token
```
Basic Auth : 
  username : javainuse-client 
  password : javainuse-secret
```
```
Body : 

grant_type : password
username : javainuse-user 
password : javainuse-pass
```

Resposta :
```json
{
  "access_token": "eyJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MTY5MDMzMDEsInVzZXJfbmFtZSI6ImphdmFpbnVzZS11c2VyIiwiYXV0aG9yaXRpZXMiOlsiUk9MRV9VU0VSIl0sImp0aSI6IjY5OWI3NzQwLWNhYTctNDQ2Ny1iMDZiLTUxOGQwMTRhNDVjZiIsImNsaWVudF9pZCI6ImphdmFpbnVzZS1jbGllbnQiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXX0.JVk91as8bYeDjIppfnpFNBwi5Vm1cJICPudyXSFPmh0",
  "token_type": "bearer",
  "refresh_token": "eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX25hbWUiOiJqYXZhaW51c2UtdXNlciIsInNjb3BlIjpbInJlYWQiLCJ3cml0ZSJdLCJhdGkiOiI2OTliNzc0MC1jYWE3LTQ0NjctYjA2Yi01MThkMDE0YTQ1Y2YiLCJleHAiOjE2MTk0NTIxMDEsImF1dGhvcml0aWVzIjpbIlJPTEVfVVNFUiJdLCJqdGkiOiI3YmRhNDVkOC01YTgyLTRkNTktOTA3Ny1hZTRiZGJjNjJiOGEiLCJjbGllbnRfaWQiOiJqYXZhaW51c2UtY2xpZW50In0.iG4wFdPA9sCFCA7Ne6VEBfh6AGfPnnoxz7qX4vibkFM",
  "expires_in": 43199,
  "scope": "read write",
  "jti": "699b7740-caa7-4467-b06b-518d014a45cf"
}
```


URL GET : http://localhost:8080/validateUser
```
Header 
    Authorization : Bearer eyJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MTY5MDMzMDEsInVzZXJfbmFtZSI6ImphdmFpbnVzZS11c2VyIiwiYXV0aG9yaXRpZXMiOlsiUk9MRV9VU0VSIl0sImp0aSI6IjY5OWI3NzQwLWNhYTctNDQ2Ny1iMDZiLTUxOGQwMTRhNDVjZiIsImNsaWVudF9pZCI6ImphdmFpbnVzZS1jbGllbnQiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXX0.JVk91as8bYeDjIppfnpFNBwi5Vm1cJICPudyXSFPmh0
``` 

Passar token do retorno ao serviço "oauth/token"

Resposta :

```json
{
  "details": {
    "remoteAddress": "0:0:0:0:0:0:0:1",
    "sessionId": null,
    "tokenValue": "eyJhbGciOiJIUzI1NiJ9.eyJleHAiOjE2MTY5MDI2MDUsInVzZXJfbmFtZSI6ImphdmFpbnVzZS11c2VyIiwiYXV0aG9yaXRpZXMiOlsiUk9MRV9VU0VSIl0sImp0aSI6IjVhNWU2YTk4LWI4NDQtNGUyMS1hYTlmLTk1Y2NjNDNmMDBlMyIsImNsaWVudF9pZCI6ImphdmFpbnVzZS1jbGllbnQiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXX0.ADBHYs-CZZiIMxbVZ0bS92GMKFEE8ac7-rRa9B9cAPQ",
    "tokenType": "Bearer",
    "decodedDetails": null
  },
  "authorities": [
    {
      "authority": "ROLE_USER"
    }
  ],
  "authenticated": true,
  "userAuthentication": {
    "details": null,
    "authorities": [
      {
        "authority": "ROLE_USER"
      }
    ],
    "authenticated": true,
    "principal": "javainuse-user",
    "credentials": "N/A",
    "name": "javainuse-user"
  },
  "oauth2Request": {
    "clientId": "javainuse-client",
    "scope": [
      "read",
      "write"
    ],
    "requestParameters": {
      "client_id": "javainuse-client"
    },
    "resourceIds": [],
    "authorities": [],
    "approved": true,
    "refresh": false,
    "redirectUri": null,
    "responseTypes": [],
    "extensions": {},
    "refreshTokenRequest": null,
    "grantType": null
  },
  "credentials": "",
  "principal": "javainuse-user",
  "clientOnly": false,
  "name": "javainuse-user"
}

```

