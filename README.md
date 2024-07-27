### Access file

```
sudo nano default
```

### Setting config

```
    location /app {
      proxy_set_header X-Real-IP $remote_addr;
      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header Host $http_host;
      proxy_set_header X-NginX-Proxy true;
      proxy_pass http://127.0.0.1:3000/;
      proxy_redirect off;
    }
```

### Reload nginx config

```
sudo nginx -s reload
```

### Restart nginx

```
sudo service nginx restart
```

### Run jenkins docker

```
docker run -d --name jenkins -p 8080:8080 -p 50000:50000 --volume jenkins-data:/var/jenkins_home jenkins/jenkins:lts docker pull jenkins/jenkins:lts
```