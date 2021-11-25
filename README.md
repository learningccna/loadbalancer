# loadbalancer

Files for loadbalancer

** Change server ip addresses if instances are shutdown **

etc/nginx/sites-available/

```
upstream backend {
    server 54.158.67.8:8081;
    server 54.91.15.209:8081;
    server 54.234.101.86:8081;
 }

server {
    listen 80;
      server_name 3.88.137.52;
      location / {
      proxy_pass http://backend;
    }
}
```
