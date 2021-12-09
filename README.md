# Loadbalancer config file for Nginx

Files for loadbalancer

** Change server ip addresses if instances are shutdown **

etc/nginx/sites-available/

```
upstream backend {
    server 192.168.1.52:8081;
    server 192.168.1.53:8081;
    server 192.168.1.54:8081;
 }

server {
    listen 80;
      server_name 192.168.1.51;
      location / {
      proxy_pass http://backend;
    }
}
```
