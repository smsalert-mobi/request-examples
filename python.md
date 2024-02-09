## Send Message

```
import http.client

conn = http.client.HTTPSConnection("smsalert.mobi")

payload = "{\n\t\"message\" : \"test message\",\n\t\"phoneNumber\": \"+40720123456\"\n}"

headers = {
    'cookie': "t_sticky_smsalert=bd6d040c9f110f97",
    'Content-Type': "application/json",
    'User-Agent': "insomnia/8.5.1",
    'Authorization': "Basic dXNlcm5hbWU6cGFzc3dvcmQ="
    }

conn.request("POST", "/api/v2/message/send", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```