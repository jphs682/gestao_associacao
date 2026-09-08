# Arquitetura

A arquitetura inicial da aplicação será organizada da seguinte forma:

```text
                 INTERFACE WEB
                      │
                      ▼
                 SPRING BOOT
                      │
           ┌──────────┴──────────┐
           │                     │
      ASSOCIADOS          CONTRIBUIÇÕES
           │                     │
           └──────────┬──────────┘
                      ▼
               JPA / HIBERNATE
                      │
                      ▼
                 POSTGRESQL
```

A aplicação utilizará uma arquitetura baseada em camadas, permitindo separar as responsabilidades relacionadas à interface, regras de negócio, persistência e banco de dados.
