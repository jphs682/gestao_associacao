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


## Documento de Arquitetura de Software

A visão arquitetural detalhada, incluindo tecnologias, módulos, infraestrutura, segurança, implantação, testes e decisões técnicas, está documentada no [Documento de Arquitetura de Software (DAS)](../arquitetura/DAS.md).

Este arquivo mantém uma visão resumida da arquitetura para apoiar a leitura da documentação de modelagem. Em caso de divergência, as decisões deverão ser revisadas e alinhadas entre os documentos; o DAS é a referência geral da arquitetura planejada.
