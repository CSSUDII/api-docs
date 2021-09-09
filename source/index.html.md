---
title: CSSUDII Public API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the CSSUDII Public API
---

# Introduction

Coming soon!

# Authentication

> To get an API key you will need to create an account

```ruby
require "uri"
require "net/http"

url = URI("https://api.cssudii.tk/v1/auth/register")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Content-Type"] = "application/x-www-form-urlencoded"
request.body = "name=your%20name&email=your%20email&password=your%20password"

response = https.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("api.cssudii.tk")
payload = 'name=your%20name&email=your%20email&password=your%20password'
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}
conn.request("GET", "/v1/auth/register", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --body-data 'name=your%20name&email=your%20email&password=your%20password' \
   'https://api.cssudii.tk/v1/auth/register'
```

```javascript
var axios = require('axios');
var qs = require('qs');
var data = qs.stringify({
  'name': 'your name',
  'email': 'your email',
  'password': 'your password' 
});
var config = {
  method: 'get',
  url: 'https://api.cssudii.tk/v1/auth/register',
  headers: { 
    'Content-Type': 'application/x-www-form-urlencoded'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});
```

After you have made your account you will be given an api key, if your API key expiers or you need a new one send a GET request to `/v1/auth/me` like so:
```ruby
require "uri"
require "net/http"

url = URI("https://api.cssudii.tk/v1/auth/me")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Content-Type"] = "application/x-www-form-urlencoded"
request.body = "name=your%20name&email=your%20email&password=your%20password"

response = https.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("api.cssudii.tk")
payload = 'name=your%20name&email=your%20email&password=your%20password'
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}
conn.request("GET", "/v1/auth/me", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header 'Content-Type: application/x-www-form-urlencoded' \
  --body-data 'name=your%20name&email=your%20email&password=your%20password' \
   'https://api.cssudii.tk/v1/auth/me'
```

```javascript
var axios = require('axios');
var qs = require('qs');
var data = qs.stringify({
  'name': 'your name',
  'email': 'your email',
  'password': 'your password' 
});
var config = {
  method: 'get',
  url: 'https://api.cssudii.tk/v1/auth/me',
  headers: { 
    'Content-Type': 'application/x-www-form-urlencoded'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});
```

> This will return a new API key for your account
> We have a WIP backend at: https://github.com/CSSUDII/api-backend/

# Image API

## Invert an image

```ruby
require "uri"
require "net/http"

url = URI("https://api.cssudii.tk/v1/image/invert?imgUrl=imageurl")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["x-access-token"] = "your token"

response = https.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("api.cssudii.tk")
payload = ''
headers = {
  'x-access-token': 'your token'
}
conn.request("GET", "/v1/image/invert?imgUrl=imageurl", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```shell
wget --no-check-certificate --quiet \
  --method GET \
  --timeout=0 \
  --header 'x-access-token: your token' \
   'https://api.cssudii.tk/v1/image/invert?imgUrl=imageurl'
```

```javascript
var axios = require('axios');
var qs = require('qs');
var data = qs.stringify({
   
});
var config = {
  method: 'get',
  url: 'https://api.cssudii.tk/v1/image/invert?imgUrl=imageurl',
  headers: { 
    'x-access-token': 'your token'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});
```

> This returns an png image

