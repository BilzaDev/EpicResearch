# Auth code
We will be loggin in through an authentication code.

- We will be using requests to send a post request to `https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token` 

- Then we will print the data from the request that we made.

```python
url = f"https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token"
headers = {
    "Content-Type": f"application/x-www-form-urlencoded",
    "Authorization": f"basic MzQ0NmNkNzI2OTRjNGE0NDg1ZDgxYjc3YWRiYjIxNDE6OTIwOWQ0YTVlMjVhNDU3ZmI5YjA3NDg5ZDMxM2I0MWE="
}
    
data = f"grant_type=authorization_code&code={authcode}"
request = requests.post(url, headers=headers, data=data)
print({request.json()})
```

- Now you have an access token that can be used for epic games services.
