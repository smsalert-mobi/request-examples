## Send Message

```
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://smsalert.mobi/api/v2/message/send"

	payload := strings.NewReader("{\n\t\"message\" : \"test message\",\n\t\"phoneNumber\": \"+40720123456\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("Authorization", "Basic dXNlcm5hbWU6cGFzc3dvcmQ=")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```