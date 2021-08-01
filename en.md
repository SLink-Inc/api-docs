Authentication

To authenticate with the API system, you need to send your API key as an authorization token with each request. You can see sample code below.
Curl:

```c
curl --location --request POST 'https://slink.cf/api/url/add' \ 
--header 'Authorization: Token BP5jCxXDo6Zv' \
--header 'Content-Type: application/json' \ 
```
Php: 
```php
$curl = curl_init();
curl_setopt_array($curl, array(
  CURLOPT_URL => "https://slink.cf/api/url/add",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 2,
  CURLOPT_TIMEOUT => 10,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Token BP5jCxXDo6Zv",
    "Content-Type: application/json",
  ),
));

$response = curl_exec($curl);
```
Shortening a link

To shorten a url, you need to send a valid date in JSON via a POST request. The data must be sent as the raw body of your request as shown below. The example below shows all the parameters you can send but you are not required to send all (See table for more info).
```c
curl --location --request POST 'https://slink.cf/api/url/add' \
--header 'Authorization: Token GQxYFmK7GyWq' \
--header 'Content-Type: application/json' \
--data-raw '{
    "url": "https://google.com",
    "custom": "google",
    "password": "mypass",
    "domain": "http://goo.gl",
    "expiry": "2020-11-11 12:00:00",
    "type": "splash",
    "geotarget": [{
        "location": "Canada",
        "link": "https://google.ca"
      },
      {
        "location": "United States",
        "link": "https://google.us"
      }
    ],
    "devicetarget": [{
        "device": "iPhone",
        "link": "https://google.com"
      },
      {
        "device": "Android",
        "link": "https://google.com"
      }
    ]
  }'```
