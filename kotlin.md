## Send Message

```
val client = OkHttpClient()

val mediaType = MediaType.parse("application/json")
val body = RequestBody.create(mediaType, "{\n\t\"message\" : \"test message\",\n\t\"phoneNumber\": \"+40720123456\"\n}")
val request = Request.Builder()
  .url("https://smsalert.mobi/api/v2/message/send")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Authorization", "Basic dXNlcm5hbWU6cGFzc3dvcmQ=")
  .build()

val response = client.newCall(request).execute()
```