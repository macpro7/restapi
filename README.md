<!-- TITLE: Pi 002 En Restapi -->
<!-- SUBTITLE:  -->

# Send sms
### HTTP Requests
POST /api/sms/v1/sendsms
### Limit: 
1 time / 60s

### Request Sample
POST /api/sms/v1/sendsms

If you want to send a auth-sms to Mr. Tom: 

`Dear Mr. Tom , your auth code is 888888. The code will expire in 60 seconds. Have a good time! [Cookpad]`
Then , the parameter should like this:

> ' {"client_id":"cookpad_Server_001","phone_number":"13800138000","templet_id":"t1","contents":["p1":"Mr. Tom","p2":"888888","p3":"Have a good time!"] }'

Parameters   |    Parameters Types |   Required |   Description
--------|--------------------|------------|---------
client_id      |  String     |         No        |  the Client ID customized by yourself
phone_number  |   String     |         Yes    |     Contract ID,e.g. “TC-USD-180213”
templet_id  |     String     |         Yes       |  1:open long 2:open short 3:close long 4:close short
contents    |     String     |         Yes      |   Price of each contract




# EORROR CODE:
## Common Error Codes
400    Bad Request — Invalid request format
401    Unauthorized — Invalid API Key
403    Forbidden — You do not have access to the requested resource
404    Not Found
500    Internal Server Error — We had a problem with our server
429   Too Many Requests’ will be returned.

## Success
A successful response is indicated by HTTP status code 200 and may contain an optional body.
If the response has a body it will be documented under each resource below.
