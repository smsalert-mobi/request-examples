## Send Message

```
const http = require("https");

const options = {
  "method": "POST",
  "hostname": "smsalert.mobi",
  "port": null,
  "path": "/api/v2/message/send",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Basic dXNlcm5hbWU6cGFzc3dvcmQ="
  }
};

const req = http.request(options, function (res) {
  const chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    const body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({message: 'test message', phoneNumber: '+40720123456'}));
req.end();
```