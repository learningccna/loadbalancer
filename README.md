# Loadbalancer config file for Nginx

Files for loadbalancer

** Change server ip addresses if instances are shutdown **

etc/nginx/sites-available/

```
upstream backend {
    server jwwebserver.ddns.net:8081;
    server jwwebserver2.ddns.net:8081;
    server jwwebserver3.ddns.net:8081;
 }

server {
    listen 80;
      server_name jwloadbalancer.ddns.net;
      location / {
      proxy_pass http://backend;
    }
}
```
