## Nginx - Reverse Proxy Server

- Reverse proxy runs on port 80, also run on 443 for https
- we defined in .conf, If req come to this domain, redirect it to 8080, we can redirect it to 8081,8082,8083..
- A reverse proxy listen on 40,and it will redirect to other ports
- A proxy(forward proxy), is like VPN, we request to vpn, vpn send our req to the internet.

## Install Nginx

- As you install nginx, you have nginx on port 80

```sh
sudo apt update
sudo apt install nginx
```

## Go to DNS provider

- point the domain to the server ip

## Create Reverse Proxy

```sh
sudo rm /etc/nginx/nginx.conf
```

```sh
sudo vi /etc/nginx/nginx.conf
```

```javascript

events {
   #Event directives....
}

http {
    server{
        listen 80;
        server_name example.com;

        # Proxy requests to the backend server
        location / {
            proxy_pass http://localhost:8080;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_cache_bypass $http_upgrade;
        }

    }
}

```

```sh
sudo systemctl reload nginx
```
