---
title: Infrastructure Nginx Reverse Proxy Checklist
date: 2026-06-30 14:30:00
tags:
  - Knowledge
categories:
  - Infrastructure
---

# Nginx Reverse Proxy Checklist

Nginx is often used as the public entry point in front of an application server. The browser talks to Nginx, and Nginx forwards the request to a local app such as Django, Node.js, or another backend service.

## Basic Flow

1. User visits a domain name.
2. DNS points the domain to the server IP.
3. Nginx receives the HTTP or HTTPS request.
4. Nginx forwards the request to the application port.
5. The application returns a response to Nginx.
6. Nginx sends the response back to the browser.

## Minimal Reverse Proxy Config

```nginx
server {
    listen 80;
    server_name example.com www.example.com;

    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

## Useful Commands

```shell
sudo nginx -t
sudo systemctl reload nginx
sudo systemctl status nginx
sudo tail -f /var/log/nginx/error.log
sudo tail -f /var/log/nginx/access.log
```

## Common Problems

1. Nginx config test fails
   - Run `sudo nginx -t`.
   - Check missing semicolons, wrong file paths, or duplicated `server_name`.

2. Browser shows 502 Bad Gateway
   - Confirm the backend app is running.
   - Check that `proxy_pass` uses the correct host and port.
   - Look at `/var/log/nginx/error.log`.

3. Static files do not load
   - Confirm the static file path exists.
   - Check folder permissions.
   - Add a dedicated `location /static/` block if needed.

4. HTTPS redirect loop
   - Confirm the app understands `X-Forwarded-Proto`.
   - Check whether both the app and Nginx are forcing redirects.

## Static File Example

```nginx
location /static/ {
    alias /var/www/example/static/;
}

location /media/ {
    alias /var/www/example/media/;
}
```

## Deployment Notes

Keep Nginx responsible for public traffic, TLS, redirects, and static files. Keep the application server focused on application logic. This separation makes production debugging easier because each layer has a clear job.
