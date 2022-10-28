# fluentd-collector

A project to run Fluentd in collector mode.

## Pre-deployment preparation

---

Before deploying the project, install Docker, Docker Compose latest versions.

---

## Installation

---

For installation:
To install, run:

1. Do a git clone.

2. Create an .env file and fill with variables:

```bash
cp ./.env_temp ./.env
```

3. Run the project

```bash
docker-compose up -d
```

4. After a couple of minutes, the service will start.

---

### Useful links

---

[Fluentd: Official Manual](https://docs.fluentd.org/)