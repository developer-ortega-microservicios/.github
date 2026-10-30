# NestJS Microservicios

Tienda de **5 microservicios** con NestJS, construida a partir del curso [NestJS + Microservicios](https://www.udemy.com/course/nestjs-microservicios/) (Udemy, DevTalles) y desplegada en **Kubernetes (GKE)** con Helm. Proyecto de práctica de [@developer-ortega](https://github.com/developer-ortega).

## Arquitectura

```
Cliente HTTP
     │
     ▼
client-gateway ──NATS──→ products-ms (SQLite)
                ├──────→ orders-ms ──→ PostgreSQL
                ├──────→ payments-ms ──→ Stripe (webhooks)
                └──────→ auth-ms ──→ MongoDB
```

## Servicios

| Repositorio | Descripción |
|-------------|-------------|
| [products-launcher](https://github.com/developer-ortega-microservicios/products-launcher) | Punto de entrada: submódulos de Git, Docker Compose y charts de Helm para Kubernetes |
| [client-gateway](https://github.com/developer-ortega-microservicios/client-gateway) | API Gateway: único punto de entrada HTTP |
| [products-ms](https://github.com/developer-ortega-microservicios/products-ms) | Microservicio de productos (Prisma + SQLite) |
| [orders-ms](https://github.com/developer-ortega-microservicios/orders-ms) | Microservicio de órdenes (Prisma + PostgreSQL) |
| [payments-ms](https://github.com/developer-ortega-microservicios/payments-ms) | Pagos con Stripe Checkout y webhooks |
| [auth-ms](https://github.com/developer-ortega-microservicios/auth-ms) | Autenticación con JWT, bcrypt, Prisma y MongoDB |

## Stack

NestJS · TypeScript · NATS · Prisma · PostgreSQL · MongoDB · SQLite · JWT · Stripe · Docker · Kubernetes (GKE) · Helm · Google Cloud Build · Artifact Registry

## Cómo probarlo

Clona el [launcher](https://github.com/developer-ortega-microservicios/products-launcher) con sus submódulos y sigue su README:

```bash
git clone --recurse-submodules https://github.com/developer-ortega-microservicios/products-launcher.git
```

## Autor

**Renato Ortega** · Analista Programador, Viña del Mar, Chile
[GitHub](https://github.com/developer-ortega) · [LinkedIn](https://www.linkedin.com/in/renato-ortega-dev/)

