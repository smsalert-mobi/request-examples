## Send Message

```
curl --request POST \
  --url http://smsalert.mobi/api/v2/message/send \
  --header 'Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=' \
  --header 'Content-Type: application/json' \
  --data '{
	"message" : "test message",
	"phoneNumber": "+40720123456"
}'
```