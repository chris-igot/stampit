## About

Stampit is a photo sharing webapp that uses emojis for viewer responses. These emojis can be placed anywhere on the photo. It has a Java Spring backend with a React frontend.  
See it deployed here: [https://stampit.chris-igot.link/](https://stampit.chris-igot.link/)
Docker: [https://hub.docker.com/repository/docker/chrisigot/stampit](https://hub.docker.com/repository/docker/chrisigot/stampit)

## Setup

The following environmental variables need to be set:  
`UPLOADS_PATH`  
`MYSQL_PATH`  
`MYSQL_USER`  
`MYSQL_PW`  
`ADMIN_EMAIL`  
`ADMIN_PW`  
`ADMIN_PATH`

Example `docker-compose.yml`:

```
version: '3.8'
services:
  server:
    image: stampit
    ports:
      - 8080:8080
    volumes:
      - uploads:/app/uploads
      - {{your ADMIN_PATH value}}:/app/admin
    restart: always
    environment:
      UPLOADS_PATH: {{your UPLOADS_PATH value}}
      MYSQL_PATH: {{your MYSQL_PATH value}}
      MYSQL_USER: {{your MYSQL_USER value}}
      MYSQL_PW: {{your MYSQL_PW value}}
      ADMIN_EMAIL: {{your ADMIN_EMAIL value}}
      ADMIN_PW: {{your ADMIN_PW value}}
      ADMIN_PATH: {{your ADMIN_PATH value}}
volumes:
  uploads:
    external: false
```
