# Hashtag Awareness DevStack

This is the development stack for the Hashtag Awareness app.
Use this setup in order to create container which can run the app.

## Nginx vhost

The stack provides an Nginx host with SSL vhost.

Run the following command inside `./images/nginx/` in order to generate the needed `cert.pem` and `key.pem` files.

```sh
$ openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out cert.pem
```

## PHP

No additional configuration is needed for the php process. You can change the `images\php\Dockerfile` 
 in case more php extensions are needed.

## Build and run the container

Use the following command to build and run the container.

```sh
$ docker-compose up --build -d
```

## Running the app

Once the container is running checkout the project inside the `app` folder.
Then follow it's install instructions.

This approach is used for the development environment.
In production there is a separate container and the code is packaged within it.