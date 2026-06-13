
# OpenGDPS
> OpenGDPS is an open-source implementation of Geometry Dash server, in Python. It supports 2.11 only, versions below 2.0 or 2.2+ are not supported.

> It's very modular, and implemented in Flask (I know, FastAPI just exists, but Flask is better for prototyping).

> NEVER use this implementation in production - IT'S REALLY UNSAFE, CONTAINS SQL-INJECTIONS! It's just prototype. And it uses SQLite, so it will die in async operations.

> Also, don't ask me, why there's a token in discordbot.py - anyways, it's not valid for now. But I say for everyone - never save tokens in files with source code, you should create separate .json for minimum, or better - use environment variables

## What is implemented
- Most Geometry Dash routes:
  - [accounts](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/accounts) - Login/register, cloud save load/backup, main account data editing (YouTube/Twitch links for example, and DM/friend req)
  - [messages](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/messages) - DM, and posts on own accounts
  - [misc](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/misc) - Endpoints for music (need to upload own)
  - [relationships](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/relationships) - Friend requests, and friends list
  - [scores](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/scores) - Leaderboard
  - [users](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/users) - Part of friends list, friend requests (Geometry Dash architecture is a little bit weird)
- Some other endpoints:
  - [dl](https://github.com/thelittlepony/OpenGDPS-Core/blob/main/routes/dl.py) - For own music
  - [like_acc_or_lvl_comment](https://github.com/thelittlepony/OpenGDPS-Core/blob/main/routes/like_acc_or_lvl_comment.py) - Adding likes/dislikes to comment on account or level (It's very awful and unsafe!!!)
  - [request_user_access](https://github.com/thelittlepony/OpenGDPS-Core/blob/main/routes/request_user_access.py) - Endpoint to enable client-side features for mods
- Dummy, or not implemented:
  - [frontend](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/frontend) - Dummy for `/database/accounts/accountManagement.php`
  - [legacy](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/legacy) - Just exists, I forgot to implement it
  - [levels](https://github.com/thelittlepony/OpenGDPS-Core/tree/main/routes/levels) - Partially implemented, but uploading/downloading levels I was unable to implement
  - downloadGJLevel - Level downloading

## Problems
- Security (SQL-injections, you know)
- Code is a little bit slow
- Some endpoints not implemented, or just dummy
- It's prototype, it's okay if this contains problems

## How to run
Requires Python 3.9-3.10
```
git clone https://github.com/thelittlepony/OpenGDPS-Core
python3 -m pip install -r requirements.txt
python3 main.py
```

You server is ready. BUT NEVER USE THIS IN PRODUCTION, THIS CONTAINS SQL-INJECTION VULNERABILITY, REMEMBER!
