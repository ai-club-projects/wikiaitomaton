# Как добавить поддомен

- заходим https://dcc.godaddy.com/control/dnsmanagement?domainName=aitomaton.online

- добавляем dns A запись с нужным поддоменом  и ip сервера


- создаем nginx config
/etc/nginx/sites-enabled/apitable.aitomaton.online.conf 

пример для apitable на порту 1412:
```
server {
    server_name apitable.aitomaton.online;

    location / {
        proxy_pass http://localhost:1412;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
server {
    if ($host = apitable.aitomaton.online) {
        return 301 https://$host$request_uri;
    }
    listen 80;
    server_name apitable.aitomaton.online;
}
```
- выполняем `sudo certbot --nginx`, выбираем из списка новый домен

- готово
