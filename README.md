# Sistema de Gestão de Associações

Sistema web para cadastro e gerenciamento de associados e controle de contribuições de associações comunitárias.

## Sobre o projeto

O projeto propõe uma solução computacional para centralizar e organizar informações de associações comunitárias por meio de um sistema web.

A primeira versão será composta por dois módulos principais:

- **Associados** — gerenciamento dos dados cadastrais, da situação e do histórico de vida associativa.
- **Contribuições** — registro e consulta dos pagamentos realizados pelos associados.

O desenvolvimento será realizado de forma participativa, considerando as necessidades identificadas junto à associação parceira.

## Funcionalidades da primeira versão

- Cadastro, consulta e atualização de associados
- Controle da situação do associado
- Prevenção de cadastros duplicados
- Histórico da vida associativa
- Reativação de associado sem refazer o cadastro
- Registro dos períodos de filiação
- Registro e consulta de contribuições
- Histórico de contribuições

Um associado que se desliga não deve ser apagado. Seu cadastro e histórico permanecem disponíveis para uma eventual reativação.

## Tecnologias

| Tecnologia | Utilização |
| --- | --- |
| Java 21 | Linguagem principal |
| Spring Boot | Desenvolvimento do backend |
| Spring Data JPA | Persistência de dados |
| Hibernate | ORM |
| PostgreSQL | Banco de dados |
| HTML5 | Estrutura das páginas |
| CSS3 | Estilização |
| JavaScript | Interações da interface |
| Bootstrap | Componentes e layout |
| Git | Controle de versão |
| GitHub | Hospedagem do código |

## Como executar

### Pré-requisitos

- Java 21
- Maven
- PostgreSQL
- Git

### Clonar o repositório

```bash
git clone <URL_DO_REPOSITORIO>
cd sistema-gestao-associacoes
```

### Configurar o banco de dados

Crie um banco PostgreSQL:

```sql
CREATE DATABASE associacoes;
```

Configure as credenciais em `src/main/resources/application.properties`.

Exemplo:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/associacoes
spring.datasource.username=postgres
spring.datasource.password=sua_senha

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```

> **Importante:** as credenciais reais do banco de dados não devem ser versionadas no repositório.

### Executar

Com Maven Wrapper:

```bash
./mvnw spring-boot:run
```

No Windows:

```cmd
mvnw.cmd spring-boot:run
```

Ou com Maven instalado globalmente:

```bash
mvn spring-boot:run
```

## Documentação

A documentação foi separada por assunto dentro de `docs/`:

- [Levantamento](docs/levantamento/)
- [Requisitos](docs/requisitos/)
- [Modelagem](docs/modelagem/)
- [Desenvolvimento](docs/desenvolvimento/)
- [Testes](docs/testes/)
- [Projeto acadêmico](docs/projeto/)
- [Manual](docs/manual/)

## Status

**Em desenvolvimento 🚧**

Os requisitos, modelos, funcionalidades e estrutura técnica poderão ser modificados durante o desenvolvimento conforme as necessidades identificadas junto à associação parceira.

## Contribuição

Durante o desenvolvimento acadêmico, sugestões e melhorias podem ser registradas por meio das **Issues** e **Pull Requests** do repositório.

## Licença

A licença do projeto deverá ser definida de acordo com as orientações da instituição de ensino e as condições estabelecidas com a associação parceira.
