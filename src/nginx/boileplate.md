---
name: Boileplate
menu: nginx
route: nginx/boileplate
---

# Nginx

## Proxy for another address

```
server {
    server_name cv.hieunguyen.dev www.cv.hieunguyen.dev ;
    
        listen 128.199.154.225:80;
    
        set $root_path /var/www/cv.hieunguyen.dev/data/www/cv.hieunguyen.dev;
    
        root $root_path;
        disable_symlinks if_not_owner from=$root_path;
    
        location / {
            proxy_set_header X-Forwarded-Host $http_host;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;
    
            client_max_body_size 10m;
    
            proxy_http_version 1.1;
            proxy_pass https://curriculum-vitae-4467411736.gtsb.io;
        }
}
```

