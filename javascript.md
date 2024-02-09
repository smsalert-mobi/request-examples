## Send Message

```
const data = JSON.stringify({
  "message": "test message",
  "phoneNumber": "+40720123456"
});

const xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === this.DONE) {
    console.log(this.responseText);
  }
});

xhr.open("POST", "https://smsalert.mobi/api/v2/message/send");
xhr.setRequestHeader("Content-Type", "application/json");
xhr.setRequestHeader("Authorization", "Basic dXNlcm5hbWU6cGFzc3dvcmQ=");

xhr.send(data);
```