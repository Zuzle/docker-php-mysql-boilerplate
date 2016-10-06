Docker PHP/MySQL Boilerplate
===

Easy development docker enviroment for php projects.

Basic initialization
---
```bash
cp .env.dist .env
```

```bash
docker-compose up -d
```

Starting symfony 2 project
---
```bash
docker-compose exec php bash
symfony new . 2.8
```

Starting symfony 3 project
---
```bash
docker-compose exec php bash
symfony new .
```