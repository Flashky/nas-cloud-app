# nas-cloud-app

## Configuration properties

Before running the service, you will need to customize several properties or environment variables:

Property | Description | Default value
--|--|--
``ADMIN_SERVER_USERNAME`` | Spring Boot Admin server username | ``admin`` **(*)**
``ADMIN_SERVER_PASSWORD`` | Spring Boot Admin server password | ``admin`` **(*)**
``TELEGRAM_BOT_TOKEN`` | The Telegram Bot token provided by [@BotFather](https://t.me/botfather) | None
``TELEGRAM_CHAT_ID`` | The Telegram chat id to send any notifications | None 

***:** *It is highly recommended to change both default username and password.*

## Docker Compose

#### Requirements

- Docker.

#### Run

Check for images updates:

```bash
docker-compose pull
```

Run in dettach mode:

```shell
docker-compose up -d
```

The previous command will setup the following containers:
- [spring-boot-admin](https://github.com/Flashky/spring-boot-admin)

It will use ``.env`` file by default for getting the [configuration properties](#configuration-properties).

If you want to use multiple environments you can duplicate ``.env``, customize its values, and finally run ``docker-compose`` specifying ``--env-file`` flag  to select which configuration to use.

Example with a ``.env.dev`` file:

```shell
docker-compose pull
docker-compose --env-file .env.dev up -d
```

#### Image cleanup

Use the following command to remove old images:

````bash
docker image prune -f
```
