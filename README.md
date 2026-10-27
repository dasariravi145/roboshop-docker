# RoboShop Docker

This repository contains a Docker Compose-based deployment for the RoboShop microservices application. It packages the frontend, cart, catalogue, user, payment, shipping, and backing services as individual containers connected through Docker networking.

## Architecture Overview

The stack includes:

- Frontend
- Catalogue
- User
- Cart
- Shipping
- Payment
- MongoDB
- Redis
- MySQL
- RabbitMQ

The services are defined in `docker-compose.yaml` and use custom image tags built from the project directories.

## Repository Structure

```bash
.
├── docker-compose.yaml
├── frontend/
├── cart/
├── catalogue/
├── user/
├── payment/
├── shipping/
├── mongodb/
├── mysql/
├── redis/
├── rabbitmq/
└── README.md
```

## Service Summary

- `frontend` serves the application UI.
- `catalogue`, `user`, `cart`, `payment`, and `shipping` represent the app business services.
- `mongodb`, `redis`, `mysql`, and `rabbitmq` provide stateful and messaging dependencies.
- Docker Compose manages service startup order and network configuration.

## How to Run

```bash
docker compose up -d
```

To stop and remove containers:

```bash
docker compose down
```

## Useful Notes

- Images are tagged as `ravidasari145/<service>:1.0.0`.
- Networking is defined via a default Docker bridge network.
- Persistent data is mapped to named volumes for MongoDB, Redis, MySQL, and RabbitMQ.

## Use Cases

This repository is useful for:

- learning Docker Compose multi-service orchestration
- validating microservice dependencies and startup order
- demonstrating an end-to-end app deployment in a local environment

## Related Projects

- [roboshop-ansible](https://github.com/dasariravi145/roboshop-ansible)
- [ansible-roboshop-roles](https://github.com/dasariravi145/ansible-roboshop-roles)
- [k8-roboshop](https://github.com/dasariravi145/k8-roboshop)
- [shell-roboshop](https://github.com/dasariravi145/shell-roboshop)
