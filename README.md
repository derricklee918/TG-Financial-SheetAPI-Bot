# Telegram Financial Bot (Integrated Google Sheet APIs)

Telegram bot for tracking personal expenses and budgeting, [video with explanations of the code and description](https://www.youtube.com/watch?v=Kh16iosOTIQ).

In the environment variables, you need to specify the bot's API token, as well as the proxy address and login-password to it.

## Contact me
Telegram: [@derricklee918](https://t.me/@derricklee918)


## How to Run

`TELEGRAM_API_TOKEN` — API Bot Token

`TELEGRAM_PROXY_URL` — Proxy Server URL

`TELEGRAM_PROXY_LOGIN` — proxy server login

`TELEGRAM_PROXY_PASSWORD` — proxy server password

`TELEGRAM_ACCESS_ID` — Telegram account ID from which messages will be received (messages from other accounts are ignored)

Usage with Docker is shown below. Pre-fill the ENV variables specified above in the Dockerfile, and also specify the local directory with the project instead of `local_project_path` in the run command. The SQLite database will be located in the project folder `db/finance.db`.

```
docker build -t tgfinance ./
docker run -d --name tg -v /local_project_path/db:/home/db tgfinance
```

To enter a running container:

```
docker exec -ti tg bash
```

Login to SQL shell in container:

```
docker exec -ti tg bash
sqlite3 /home/db/finance.db
```


