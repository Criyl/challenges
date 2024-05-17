##  Simple Session Auth Server

Create an authentication service that uses `session tokens` to identify users.

### API

GET `/request`
> Return an anonymous `session token`

POST `/refresh`
> Refresh an existing `session` and return the new `session token`


### Anatomy of the Token

Session
- id
> ID for the session
- expire_time
> time in epoch format
- salt
> random salt

```json
{
    "id": 9223372036854775807 ,
    "expire": 9223372036854775807,
    "salt": 9223372036854775807
}
```

### Optional Endpoints

POST `/register`

BODY
```json
{
    "username/email": "admin",
    "password": "changeme"
}
```
> Return `200` if successful
>
> Side Effect: user created

POST `/login`

BODY
```json
{
    "username/email": "admin",
    "password": "changeme"
}
```
> Return `session token`
