# Command 

- We will be making a command for the python library `pycord`.

- Make sure you have a database in this case I will be using pymongo.

- First make a slash command with the code below this text.

```python
@Bot.slashcommand(description="your description here")
async def commandnamehere(ctx):

```

- Now using that code above we will make a log in command with pymongo and discord Options.

- The code will be below this text.

```python
@Bot.slashcommand(description="your description here")
async def commandnamehere(ctx, authcode: Option(str, "authcode here")):
    check = await cursor.find_one({"discordid": ctx.author.id})
    url = f"https://account-public-service-prod.ol.epicgames.com/account/api/oauth/token"
    headers = {
        "Content-Type": f"application/x-www-form-urlencoded",
        "Authorization": f"basic MzQ0NmNkNzI2OTRjNGE0NDg1ZDgxYjc3YWRiYjIxNDE6OTIwOWQ0YTVlMjVhNDU3ZmI5YjA3NDg5ZDMxM2I0MWE="
    }
                
    data = f"grant_type=authorization_code&code={authcode}"
    request = requests.post(url, headers=headers, data=data)
```

- That is the command but you will have to figure out on how to save the data.



