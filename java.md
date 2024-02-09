## Send Message

```
HttpResponse<String> response = Unirest.post("https://smsalert.mobi/api/v2/message/send")
  .header("Content-Type", "application/json")
  .header("Authorization", "Basic dXNlcm5hbWU6cGFzc3dvcmQ=")
  .body("{\n\t\"message\" : \"test message\",\n\t\"phoneNumber\": \"+40720123456\"\n}")
  .asString();
```