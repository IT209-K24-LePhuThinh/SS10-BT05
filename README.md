# BT05 - Khởi chạy dịch vụ đơn giản với Docker Compose

## Tạo tệp docker-compose.yml

`docker-compose.yml`:

```yaml
services:
  web:
    image: nginx:alpine
    ports:
      - "8082:80"
```

## Khởi chạy dịch vụ

```bash
devops@0310263186:~/ss10-bt05$ docker compose up -d
[+] Running 2/2
 ✔ Network ss10-bt05_default  Created                                      0.2s
 ✔ Container ss10-bt05-web-1  Started                                      0.5s
```

## Kiểm tra dịch vụ

```bash
devops@0310263186:~/ss10-bt05$ docker compose ps
NAME              IMAGE          COMMAND                  SERVICE   CREATED          STATUS          PORTS
ss10-bt05-web-1   nginx:alpine   "/docker-entrypoint.…"   web       6 seconds ago    Up 5 seconds    0.0.0.0:8082->80/tcp, [::]:8082->80/tcp
```

## Kiểm tra trang web

```bash
devops@0310263186:~/ss10-bt05$ curl http://localhost:8082
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

## Hạ dịch vụ xuống

```bash
devops@0310263186:~/ss10-bt05$ docker compose down
[+] Running 2/2
 ✔ Container ss10-bt05-web-1  Removed                                      0.4s
 ✔ Network ss10-bt05_default  Removed                                      0.1s
```
