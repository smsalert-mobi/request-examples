## Send Message

```
<?php

$curl = curl_init();

$postFields = [
    'message' => 'test message',
    'phoneNumber' => '+40720123456',
];

// Basic Authentication credentials
$username = "your_username";
$password = "api_key";

curl_setopt_array($curl, [
    CURLOPT_URL => "https://smsalert.mobi/api/v2/message/send",
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_TIMEOUT => 5,
    CURLOPT_CUSTOMREQUEST => "POST",
    CURLOPT_POSTFIELDS => json_encode($postFields),
    CURLOPT_HTTPHEADER => [
        "Content-Type: application/json",
    ],
    CURLOPT_USERPWD => "$username:$password",
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
    echo "cURL Error #:" . $err;
} else {
    echo $response;
}
```
