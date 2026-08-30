# Sistema de Gestão de Associações

Sistema web desenvolvido como projeto de extensão universitária no âmbito do **PIBEX**, com o objetivo de auxiliar associações comunitárias na organização de informações de associados e no controle de contribuições.

## 📌 Sobre o projeto

Muitas associações comunitárias ainda realizam parte de suas atividades administrativas utilizando fichas, livros, recibos e registros manuais. Esse modelo pode dificultar a consulta e atualização das informações, além de aumentar o risco de duplicidade de cadastros e perda do histórico dos associados.

Este projeto busca desenvolver uma solução computacional simples e adequada à realidade da associação, permitindo centralizar e organizar essas informações.

A primeira versão do sistema será concentrada em dois módulos principais:

* **Associados**
* **Contribuições**

O desenvolvimento será realizado de forma participativa, considerando as necessidades identificadas junto aos responsáveis pela associação.

---

## 🎯 Objetivos

### Objetivo geral

Desenvolver uma solução computacional para auxiliar uma associação comunitária na organização do cadastro de seus associados e no controle de suas contribuições.

### Objetivos específicos

* Cadastrar associados;
* Consultar associados;
* Atualizar dados cadastrais;
* Controlar a situação dos associados;
* Evitar cadastros duplicados;
* Consultar o histórico dos associados;
* Registrar contribuições;
* Consultar o histórico de contribuições;
* Aplicar conhecimentos de desenvolvimento de software em uma situação real;
* Avaliar a utilização da solução junto aos usuários da associação.

---

## 🧩 Funcionalidades

### 👥 Associados

O módulo de associados deverá permitir:

* [ ] Cadastrar associado
* [ ] Consultar associado
* [ ] Atualizar dados
* [ ] Controlar situação do associado
* [ ] Impedir cadastros duplicados
* [ ] Consultar histórico do associado

### 💰 Contribuições

O módulo de contribuições deverá permitir:

* [ ] Registrar pagamento
* [ ] Associar pagamento a um associado
* [ ] Consultar pagamentos
* [ ] Consultar histórico de contribuições
* [ ] Identificar contribuições pendentes
* [ ] Emitir recibo

> As funcionalidades serão implementadas e avaliadas durante o desenvolvimento do projeto.

---

## 🏗️ Arquitetura prevista

A aplicação será desenvolvida seguindo uma arquitetura web baseada em camadas.

```text
┌──────────────────────────┐
│        Usuário           │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│ HTML / CSS / JavaScript  │
│        Bootstrap         │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│       Spring Boot        │
│                          │
│ Controllers              │
│ Services                 │
│ Repositories             │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│ Spring Data JPA /        │
│ Hibernate                │
└────────────┬─────────────┘
             │
             ▼
┌──────────────────────────┐
│       PostgreSQL         │
└──────────────────────────┘
```

---

## 🛠️ Tecnologias

| Tecnologia          | Utilização                        |
| ------------------- | --------------------------------- |
| **Java 21**         | Linguagem principal               |
| **Spring Boot**     | Desenvolvimento do backend        |
| **PostgreSQL**      | Banco de dados                    |
| **HTML**            | Estrutura das páginas             |
| **CSS**             | Estilização                       |
| **JavaScript**      | Interações da interface           |
| **Bootstrap**       | Componentes e layout              |
| **Git**             | Controle de versão                |
| **GitHub**          | Hospedagem do código              |

---

## 🗄️ Estrutura inicial dos dados

O sistema terá como entidades principais:

```text
┌─────────────────┐
│    ASSOCIADO    │
├─────────────────┤
│ id              │
│ nome            │
│ cpf             │
│ data_nascimento │
│ telefone        │
│ endereco        │
│ data_entrada    │
│ situacao        │
└────────┬────────┘
         │
         │ 1:N
         │
         ▼
┌─────────────────┐
│  CONTRIBUICAO   │
├─────────────────┤
│ id              │
│ associado_id    │
│ data_pagamento  │
│ competencia     │
│ valor           │
│ forma_pagamento │
└─────────────────┘
```

Um associado poderá possuir várias contribuições registradas.

---

## 📂 Estrutura prevista do projeto

```text
sistema-associacao/
│
├── src/
│   ├─ main/
│      ├── java/
│      │   └── ...
│      └── resources/
│          ├── static/
│          ├── templates/
│          └── application.properties
│   
│    
│
├── docs/
│
├── pom.xml
├── README.md
└── .gitignore
```

---

## 🚀 Como executar

### Pré-requisitos

Antes de executar o projeto, será necessário ter instalado:

* Java 21 ou superior;
* PostgreSQL;
* Git.

### Clonar o repositório

```bash
git clone https://github.com/jphs682/gestao_associacao.git
cd gestao_associacao
```

### Configurar o banco de dados

Criar um banco PostgreSQL para o projeto e configurar as informações de conexão no arquivo:

```text
src/main/resources/application.properties
```

Exemplo:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/associacao
spring.datasource.username=postgres
spring.datasource.password=SUA_SENHA

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=false
```

> As configurações utilizadas no ambiente de desenvolvimento não devem conter senhas ou informações sensíveis diretamente no repositório.

---

## 📚 Contexto acadêmico

Este projeto está sendo desenvolvido no contexto da formação em **Licenciatura em Computação**, como proposta de extensão universitária vinculada ao **PIBEX**.

O desenvolvimento busca aplicar conhecimentos acadêmicos em uma demanda real da comunidade, envolvendo:

* levantamento de requisitos;
* modelagem de sistemas;
* programação;
* banco de dados;
* desenvolvimento web;
* testes;
* usabilidade;
* documentação;
* capacitação de usuários.

---

## 🌱 Extensão universitária

O projeto busca estabelecer uma relação entre universidade e comunidade.

A associação participa do processo por meio do levantamento de necessidades, avaliação das funcionalidades e utilização da solução desenvolvida.

O objetivo não é apenas desenvolver um software, mas utilizar a Computação como instrumento para contribuir com a organização das atividades da associação e, ao mesmo tempo, proporcionar experiência prática ao estudante.

---

## 🔒 Segurança

Por trabalhar com informações de associados, o sistema deverá considerar aspectos básicos de segurança, incluindo:

* autenticação de usuários;
* controle de acesso;
* proteção das credenciais;
* validação dos dados;
* prevenção de duplicidade;
* realização de backups;
* proteção de informações sensíveis.

---

## 🚧 Status do projeto

**Em desenvolvimento 🚧**

O projeto encontra-se em fase de planejamento e levantamento de requisitos.

As funcionalidades serão implementadas gradualmente durante o desenvolvimento.

---

## 🔮 Possíveis evoluções

A primeira versão será propositalmente limitada aos módulos de associados e contribuições.

Futuramente, caso os resultados justifiquem a expansão, poderão ser estudadas funcionalidades como:

* reuniões e atas;
* controle de ofícios;
* projetos e ações;
* gestão de documentos;
* controle de diretorias;
* relatórios;
* aplicativo móvel;
* suporte a múltiplas associações.

Essas funcionalidades **não fazem parte do escopo inicial**.

---

## 👨‍💻 Autor

Projeto desenvolvido por um estudante do curso de **Licenciatura em Computação**, no contexto de um projeto de extensão universitária (PIBEX).

---

## 📄 Licença

A licença do projeto será definida durante o desenvolvimento, considerando os objetivos acadêmicos e extensionistas da proposta.

---

> **Projeto acadêmico e extensionista — Licenciatura em Computação / PIBEX**

