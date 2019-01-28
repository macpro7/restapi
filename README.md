# Send sms
### HTTP Requests
POST /api/sms/v1/sendsms
### Limit: 
- For one number : 1 time / 60s 
- For global system : 80000 times MAX / 1s

### Request Sample
POST /api/sms/v1/sendsms

If you want to send an auth-sms to Mr. Tom like this : 

`Dear Mr. Tom , your auth code is 888888. The code will expire in 60 seconds. Have a good time! [Cookpad]`

Then , the parameter should like this:

> ' {"client_id":"cookpad_Server_001","passcode":"ARDOR-7JF3-8F2E-QUWZ-CAN7F","phone_number":"13800138000","templet_id":"t1","contents":[{"p1":"Mr. Tom"},{"p2":"888888"},{"p3":"Have a good time!"}] }'

Parameters   |  Parameters Types | Required |   Description
-------------|-------------------|----------|--------------------
client_id    |  String           |    Yes   | The Client ID customized by yourself.
passcode     |  String           |    Yes   | A generated Key for the server to identify legal clients.
phone_number |  String           |    Yes   | The target user's phone number.
templet_id   |  String           |    Yes   | Each sms must follow a certain sms templet defined before. Use templet & parameters to combine a real sms to send.
contents     |  String           |    Yes   | Parameters and contents for the sms.

### Response Sample
> '{ "sms_uid":"550e8400-e29b-41d4-a716-446655440000", "status":"sent", "error_code":"0"} '

Parameters   |  Parameters Types |  Description
-------------|-------------------|----------------
sms_uid      |    String         | The sms's uid returned by the server for further querying.
status       |    String         | The status of that sms. [ queuing / sent / delivered / error   ]. The status can be changed till it reaches **delivered** or **error\_\***. 
error_code   |    String         | Show the error information if any error occurs.


-------------------------



# EORROR CODE:
## Common Error Codes
- 400    Bad Request — Invalid request format
- 401    Unauthorized — Invalid passcode 
- 403    Forbidden — You do not have access to the requested resource
- 404    Not Found
- 500    Internal Server Error — We had a problem with our server

 Additional errors:
- 429   Too Many Requests.

## Success
A successful response is indicated by HTTP status code 200 and may contain an optional body.
If the response has a body it will be documented under each resource below.


--------------------------

# Send sms
### HTTP Requests
POST /api/sms/v1/sendsms
### Limit: 
- For one number : 1 time / 60s 
- For global system : 80000 times MAX / 1s

### Request Sample
POST /api/sms/v1/sendsms

If you want to send an auth-sms to Mr. Tom like this : 

`Dear Mr. Tom , your auth code is 888888. The code will expire in 60 seconds. Have a good time! [Cookpad]`

Then , the parameter should like this:

> ' {"client_id":"cookpad_Server_001","passcode":"ARDOR-7JF3-8F2E-QUWZ-CAN7F","phone_number":"13800138000","templet_id":"t1","contents":[{"p1":"Mr. Tom"},{"p2":"888888"},{"p3":"Have a good time!"}] }'

Parameters   |  Parameters Types | Required |   Description
-------------|-------------------|----------|--------------------
client_id    |  String           |    Yes   | The Client ID customized by yourself.
passcode     |  String           |    Yes   | A generated Key for the server to identify legal clients.
phone_number |  String           |    Yes   | The target user's phone number.
templet_id   |  String           |    Yes   | Each sms must follow a certain sms templet defined before. Use templet & parameters to combine a real sms to send.
contents     |  String           |    Yes   | Parameters and contents for the sms.

### Response Sample
> '{ "sms_uid":"550e8400-e29b-41d4-a716-446655440000", "status":"sent", "error_code":"0"} '

Parameters   |  Parameters Types |  Description
-------------|-------------------|----------------
sms_uid      |    String         | The sms's uid returned by the server for further querying.
status       |    String         | The status of that sms. [ queuing / sent / delivered / error   ]. The status can be changed till it reaches **delivered** or **error\_\***. 
error_code   |    String         | Show the error information if any error occurs.


-------------------------

# Send sms
### HTTP Requests
POST /api/sms/v1/sendsms
### Limit: 
- For one number : 1 time / 60s 
- For global system : 80000 times MAX / 1s

### Request Sample
POST /api/sms/v1/sendsms

If you want to send an auth-sms to Mr. Tom like this : 

`Dear Mr. Tom , your auth code is 888888. The code will expire in 60 seconds. Have a good time! [Cookpad]`

Then , the parameter should like this:

> ' {"client_id":"cookpad_Server_001","passcode":"ARDOR-7JF3-8F2E-QUWZ-CAN7F","phone_number":"13800138000","templet_id":"t1","contents":[{"p1":"Mr. Tom"},{"p2":"888888"},{"p3":"Have a good time!"}] }'

Parameters   |  Parameters Types | Required |   Description
-------------|-------------------|----------|--------------------
client_id    |  String           |    Yes   | The Client ID customized by yourself.
passcode     |  String           |    Yes   | A generated Key for the server to identify legal clients.
phone_number |  String           |    Yes   | The target user's phone number.
templet_id   |  String           |    Yes   | Each sms must follow a certain sms templet defined before. Use templet & parameters to combine a real sms to send.
contents     |  String           |    Yes   | Parameters and contents for the sms.

### Response Sample
> '{ "sms_uid":"550e8400-e29b-41d4-a716-446655440000", "status":"sent", "error_code":"0"} '

Parameters   |  Parameters Types |  Description
-------------|-------------------|----------------
sms_uid      |    String         | The sms's uid returned by the server for further querying.
status       |    String         | The status of that sms. [ queuing / sent / delivered / error   ]. The status can be changed till it reaches **delivered** or **error\_\***. 
error_code   |    String         | Show the error information if any error occurs.


-------------------------


--------------------------

# Query sms
### HTTP Requests
POST /api/sms/v1/querysms
### Limit: 
- For global system : 1000 queries MAX / s

### Request Sample
POST /api/sms/v1/querysms

If you want to query a sms  : 

`Dear Mr. Tom , your auth code is 888888. The code will expire in 60 seconds. Have a good time! [Cookpad]`

Then , the parameter should like this:

> ' {"client_id":"cookpad_Server_001","passcode":"ARDOR-7JF3-8F2E-QUWZ-CAN7F","sms_uid":"550e8400-e29b-41d4-a716-446655440000" }'

Parameters   |  Parameters Types | Required |   Description
-------------|-------------------|----------|--------------------
client_id    |  String           |    Yes   | The Client ID customized by yourself.
passcode     |  String           |    Yes   | A generated Key for the server to identify sms_uid      |  String           |    Yes   | The unique ID for the sms which you want to check.

### Response Sample
> '{ "sms_uid":"550e8400-e29b-41d4-a716-446655440000", "status":"sent", "error_code":"0"} '


Parameters   |  Parameters Types |  Description
-------------|-------------------|----------------
sms_uid      |    String         | The unique ID for the sms.
status       |    String         | The status of that sms. [ queuing / sent / delivered / error   ]. The status can be changed till it reaches **delivered** or **error\_\***. 
error_code   |    String         | Show the error information if any error occurs.

-------------------------

# EORROR CODE:
## Common Error Codes
- 400    Bad Request — Invalid request format
- 401    Unauthorized — Invalid passcode 
- 403    Forbidden — You do not have access to the requested resource
- 404    Not Found
- 500    Internal Server Error — We had a problem with our server

 Additional errors:
- 429   Too Many Requests.

## Success
A successful response is indicated by HTTP status code 200 and may contain an optional body.
If the response has a body it will be documented under each resource below.
