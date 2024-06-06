Para crear túneles con URL públicas.

``` shell
ngrok auth token (token)
docker run --rm -p 80:80 nginx:alpine
```

## Ngrok container [Docker](Hacking%20ético/Docker/Docker.md)
The request is not authorized because credentials are missing or invalid.


```bash
docker run --net=host -it ngrok/ngrok http 80
```

Access the web inspector on the host machine at localhost:3000

```bash
docker run -it --p 3000:4040 ngrok/ngrok http 80
```

Run the ngrok agent with auth token 'xyz'

```bash
docker run -it -e NGROK_AUTHTOKEN=xyz ngrok/ngrok:alpine http 80
```

Run the ngrok agent with the config file './ngrok.yml' from the host machine

```bash
docker run -it -v $(pwd)/ngrok.yml:/etc/ngrok.yml -e NGROK_CONFIG=/etc/ngrok.yml ng
```


