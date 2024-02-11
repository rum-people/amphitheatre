## Amphitheatre

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Local orchestration with docker.

### Launch

After cloning this repository simply run 

```bash
docker compose up
```

And then proceed to 
```bash 
http://localhost:8080
``` 
to access the project web page.

### Architecture

Frontend client (`frontend-svc`) shall make a request to the load balancer (`upstream`) which is in fact [NGinX](https://www.nginx.com/) container managing CORS policies. 

Then request is forwarded to `backend-svc`. Latter utilizes conjugated [PostgreSQL](https://www.postgresql.org/) database (`backend-svc-pgdb`).

Ports are forwarded to local machine for direct testing purposes, however it is excessive feature since we have inner docker network. Ergo only `frontend-svc` must have an open port to be accessed from outside.