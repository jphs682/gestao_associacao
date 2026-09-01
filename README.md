# Sistema de Gestão de Associações

Sistema web para cadastro e gerenciamento de associados e controle de contribuições de associações comunitárias.

O projeto é desenvolvido no contexto da **Licenciatura em Computação**, com foco em tecnologia, inclusão digital e desenvolvimento comunitário.

---

## 📋 Sobre o projeto

Associações comunitárias desempenham um papel importante na organização e representação das comunidades. Entre suas atividades estão o cadastro de associados, a organização administrativa e o controle das contribuições realizadas.

Entretanto, esses processos podem ser realizados de forma predominantemente manual, utilizando fichas, livros, recibos e planilhas. Esse cenário pode dificultar a localização, atualização e preservação das informações, além de aumentar a possibilidade de duplicidades e desorganização dos registros.

Este projeto propõe o desenvolvimento de uma solução computacional para centralizar e organizar essas informações por meio de um sistema web.

A primeira versão será composta por dois módulos principais:

* **Associados** — gerenciamento dos dados cadastrais e da situação dos associados.
* **Contribuições** — registro e consulta dos pagamentos realizados pelos associados.

O desenvolvimento será realizado de forma participativa, considerando as necessidades identificadas junto à associação parceira.

---

## 🎓 Contexto acadêmico

* **Área temática:** Tecnologia e Produção
* **Área de conhecimento:** Ciência da Computação / Licenciatura em Computação
* **Área de extensão:** Tecnologia, inclusão digital e desenvolvimento comunitário
* **Tipo de projeto:** Extensão universitária

---

## 🎯 Objetivo geral

Desenvolver e avaliar uma solução computacional para auxiliar uma associação comunitária na organização do cadastro de seus associados e no controle de suas contribuições, promovendo a informatização de processos administrativos e a aplicação prática dos conhecimentos adquiridos na Licenciatura em Computação.

---

## 🎯 Objetivos específicos

* Identificar como são realizados atualmente o cadastro dos associados e o registro das contribuições.
* Levantar as principais dificuldades encontradas pelos responsáveis pela associação.
* Definir os requisitos funcionais e não funcionais do sistema.
* Modelar o banco de dados da aplicação.
* Desenvolver um sistema web utilizando Java e Spring Boot.
* Implementar o gerenciamento de associados.
* Implementar o registro e consulta das contribuições.
* Criar mecanismos para evitar cadastros duplicados.
* Permitir a consulta do histórico dos associados.
* Permitir a consulta do histórico de contribuições.
* Realizar testes técnicos e testes de utilização.
* Capacitar os usuários responsáveis pela administração.
* Avaliar a contribuição do sistema para os processos administrativos.

---

## 👥 Público-alvo

### Público direto

* Presidente da associação;
* Secretário;
* Tesoureiro;
* Demais membros responsáveis pela administração.

### Público indireto

* Associados;
* Membros da comunidade;
* Futuras diretorias da associação.

---

## 📦 Escopo da primeira versão

A primeira versão do sistema será limitada a dois módulos principais:

### 👤 Módulo de Associados

O sistema deverá permitir:

* Cadastro de associados;
* Consulta de associados;
* Atualização de dados cadastrais;
* Controle da situação do associado;
* Prevenção de cadastros duplicados;
* Consulta do histórico do associado.

#### Dados cadastrais previstos

* Nome;
* CPF;
* Data de nascimento;
* Telefone;
* Endereço;
* Data de entrada na associação;
* Situação do associado.

#### Situação do associado

Inicialmente, poderão ser utilizadas as seguintes situações:

* **Ativo**
* **Inativo**
* **Desligado**

A estrutura poderá ser adaptada conforme os requisitos identificados durante o desenvolvimento.

---

### 💰 Módulo de Contribuições

O módulo de contribuições deverá permitir:

* Registrar pagamentos;
* Associar pagamentos a um associado;
* Registrar a data do pagamento;
* Registrar o valor;
* Registrar a competência;
* Registrar a forma de pagamento;
* Consultar pagamentos realizados;
* Visualizar o histórico de contribuições de um associado.

#### Exemplo

**Associado:** João da Silva

| Competência    |    Valor |
| -------------- | -------: |
| Janeiro/2026   | R$ 20,00 |
| Fevereiro/2026 | R$ 20,00 |
| Março/2026     | R$ 20,00 |
| Abril/2026     | R$ 20,00 |

---

## 🏗️ Arquitetura

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

---

## 🗄️ Modelo de dados inicial

O relacionamento principal da aplicação será:

```text
              ASSOCIADO
                  │
                  │ 1
                  │
                  │ N
                  ▼
            CONTRIBUIÇÃO
```

Um associado poderá possuir várias contribuições registradas.

### Entidade Associado

```text
Associado
├── id
├── nome
├── cpf
├── data_nascimento
├── telefone
├── endereco
├── data_entrada
└── situacao
```

### Entidade Contribuição

```text
Contribuição
├── id
├── associado_id
├── data_pagamento
├── competencia
├── valor
└── forma_pagamento
```

A estrutura será refinada durante o levantamento de requisitos e a implementação do sistema.

---

## 🛠️ Tecnologias utilizadas

| Tecnologia      | Utilização                 |
| --------------- | -------------------------- |
| Java 21         | Linguagem principal        |
| Spring Boot     | Desenvolvimento do backend |
| Spring Data JPA | Persistência de dados      |
| Hibernate       | ORM                        |
| PostgreSQL      | Banco de dados             |
| HTML5           | Estrutura das páginas      |
| CSS3            | Estilização                |
| JavaScript      | Interações da interface    |
| Bootstrap       | Componentes e layout       |
| Git             | Controle de versão         |
| GitHub          | Hospedagem do código       |

---

## 📁 Estrutura prevista do projeto

```text
sistema-gestao-associacoes/
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── .../
│   │   │
│   │   └── resources/
│   │       ├── static/
│   │       │   ├── css/
│   │       │   ├── js/
│   │       │   └── images/
│   │       │
│   │       ├── templates/
│   │       └── application.properties
│   │
│   └── test/
│
├── docs/
│   ├── manual/
│   ├── requisitos/
│   └── diagramas/
│
├── .gitignore
├── pom.xml
└── README.md
```

A estrutura definitiva poderá ser alterada conforme a arquitetura adotada durante o desenvolvimento.

---

## ⚙️ Requisitos funcionais iniciais

| Código | Requisito                              |
| ------ | -------------------------------------- |
| RF01   | Cadastrar associado                    |
| RF02   | Consultar associado                    |
| RF03   | Atualizar associado                    |
| RF04   | Alterar situação do associado          |
| RF05   | Impedir ou alertar sobre CPF duplicado |
| RF06   | Consultar histórico do associado       |
| RF07   | Registrar contribuição                 |
| RF08   | Associar contribuição a um associado   |
| RF09   | Consultar contribuições                |
| RF10   | Visualizar histórico de contribuições  |

Os requisitos serão refinados durante as etapas de levantamento e desenvolvimento.

---

## 🔒 Requisitos não funcionais

Entre os requisitos não funcionais inicialmente considerados estão:

* Interface simples e intuitiva;
* Sistema acessível por navegador;
* Persistência segura das informações;
* Integridade dos dados;
* Organização e manutenção facilitadas;
* Código versionado;
* Utilização de tecnologias de código aberto;
* Validação dos dados de entrada;
* Prevenção de registros duplicados.

---

## 🔄 Metodologia

O projeto será desenvolvido utilizando uma abordagem participativa, envolvendo os responsáveis pela associação durante o levantamento das necessidades, testes e avaliação da solução.

### 1. Levantamento da realidade atual

Serão realizadas reuniões e conversas com os responsáveis pela associação para compreender:

* Como os associados são cadastrados;
* Como os dados são atualizados;
* Como a situação dos associados é controlada;
* Como as contribuições são registradas;
* Como os registros são consultados;
* Quais são as principais dificuldades encontradas.

### 2. Levantamento de requisitos

Com base nas informações obtidas, serão definidos e refinados os requisitos funcionais e não funcionais do sistema.

### 3. Modelagem

Será realizada a modelagem:

* Do banco de dados;
* Das entidades;
* Dos relacionamentos;
* Da arquitetura da aplicação;
* Dos fluxos principais do sistema.

### 4. Desenvolvimento

A aplicação será desenvolvida utilizando Java, Spring Boot, PostgreSQL e tecnologias web.

### 5. Testes

Serão realizados testes técnicos e testes de utilização com os responsáveis pela associação.

### 6. Capacitação

Os usuários receberão orientação sobre a utilização do sistema.

### 7. Avaliação

A solução será avaliada considerando tanto seu funcionamento técnico quanto a percepção dos usuários.

---

## 🧪 Testes previstos

### Cadastro

Verificar se um novo associado pode ser cadastrado corretamente.

### Duplicidade

Tentar cadastrar novamente um associado utilizando um CPF já existente.

**Resultado esperado:** o sistema deverá impedir o cadastro ou apresentar uma mensagem informando a existência do registro.

### Atualização

Verificar se os dados cadastrais de um associado podem ser atualizados corretamente.

### Situação

Verificar se a situação do associado pode ser alterada entre os estados disponíveis.

### Contribuições

Verificar se uma contribuição pode ser registrada e vinculada corretamente ao associado.

### Histórico

Verificar se é possível visualizar as contribuições vinculadas a determinado associado.

---

## 🎓 Capacitação dos usuários

Após a implementação, será realizada uma capacitação com os responsáveis pela associação.

A capacitação deverá abordar:

* Acesso ao sistema;
* Cadastro de associados;
* Consulta de associados;
* Atualização de informações;
* Alteração da situação;
* Registro de contribuições;
* Consulta do histórico.

Também será produzido um manual simplificado de utilização.

---

## 📊 Avaliação

A avaliação considerará aspectos técnicos e a experiência dos usuários.

Serão observados:

* Facilidade de utilização;
* Facilidade para localizar informações;
* Redução da necessidade de consultar registros físicos;
* Facilidade para registrar contribuições;
* Percepção dos usuários sobre a utilidade do sistema;
* Dificuldades encontradas durante a utilização;
* Funcionamento das principais funcionalidades.

Os resultados poderão ser utilizados para corrigir problemas e aprimorar a solução.

---

## 📈 Resultados esperados

Espera-se que o sistema contribua para:

* Centralizar os dados dos associados;
* Facilitar consultas;
* Facilitar atualizações;
* Reduzir cadastros duplicados;
* Controlar a situação dos associados;
* Preservar o histórico cadastral;
* Organizar o registro das contribuições;
* Facilitar a consulta dos pagamentos;
* Melhorar o acesso às informações administrativas;
* Reduzir a dependência de registros exclusivamente manuais.

Além disso, espera-se proporcionar ao estudante uma experiência prática envolvendo todas as principais etapas do desenvolvimento de uma solução computacional.

---

## 🌱 Impacto extensionista

O projeto busca estabelecer uma relação entre o conhecimento desenvolvido no ambiente universitário e uma necessidade identificada na comunidade.

A informatização dos processos administrativos poderá contribuir para melhorar a organização das informações da associação e facilitar o trabalho de seus responsáveis.

A participação da associação no levantamento de requisitos, nos testes e na avaliação da solução permitirá uma relação de troca entre estudante e comunidade, fortalecendo o caráter extensionista do projeto.

---

## 🎓 Impacto na formação acadêmica

O projeto permitirá ao estudante vivenciar um ciclo completo de desenvolvimento de software:

```text
Problema real
     ↓
Levantamento
     ↓
Requisitos
     ↓
Modelagem
     ↓
Programação
     ↓
Testes
     ↓
Implantação
     ↓
Capacitação
     ↓
Avaliação
```

Durante esse processo serão trabalhadas competências relacionadas a:

* Programação orientada a objetos;
* Java;
* Desenvolvimento web;
* Banco de dados;
* Modelagem de sistemas;
* Engenharia de software;
* Usabilidade;
* Testes;
* Documentação;
* Interação com usuários;
* Resolução de problemas reais.

---

## 📦 Produtos previstos

Ao final do projeto, espera-se produzir:

* Sistema web funcional;
* Banco de dados estruturado;
* Documentação técnica;
* Manual de utilização;
* Material de capacitação;
* Relatório final do projeto;
* Registro dos resultados da experiência extensionista.

---

## 🚧 Limitações e fora do escopo

A primeira versão será deliberadamente limitada aos módulos de **Associados** e **Contribuições**.

Não fazem parte do escopo inicial:

* Contabilidade completa;
* Folha de pagamento;
* Emissão de nota fiscal;
* Integração bancária;
* Pagamentos online;
* Aplicativo móvel;
* Gestão de projetos;
* Controle de ofícios;
* Gestão de documentos;
* Portal público;
* Suporte a múltiplas associações.

Essas funcionalidades poderão ser consideradas futuramente, caso os resultados da primeira versão indiquem a necessidade de expansão do sistema.

---

## 🚀 Como executar o projeto

### Pré-requisitos

Para executar o projeto localmente, será necessário ter instalado:

* Java 21;
* Maven;
* PostgreSQL;
* Git.

### 1. Clonar o repositório

```bash
git clone <URL_DO_REPOSITORIO>
```

### 2. Entrar no diretório

```bash
cd sistema-gestao-associacoes
```

### 3. Configurar o banco de dados

Crie um banco de dados PostgreSQL para o projeto:

```sql
CREATE DATABASE associacoes;
```

Depois, configure as credenciais do banco no arquivo:

```text
src/main/resources/application.properties
```

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

### 4. Executar a aplicação

Utilizando Maven Wrapper:

```bash
./mvnw spring-boot:run
```

No Windows:

```cmd
mvnw.cmd spring-boot:run
```

Ou, caso o Maven esteja instalado globalmente:

```bash
mvn spring-boot:run
```

---

## 🔀 Controle de versão

O projeto utiliza **Git** para controle de versão e **GitHub** para hospedagem do código-fonte.

Sugestão de fluxo de desenvolvimento:

```text
main
 │
 ├── develop
 │    │
 │    ├── feature/associados
 │    ├── feature/contribuicoes
 │    ├── feature/historico
 │    └── feature/interface
 │
 └── releases
```

---

## 🗺️ Roadmap

### Fase 1 — Levantamento

* [ ] Conhecer o processo atual da associação
* [ ] Levantar necessidades
* [ ] Identificar problemas
* [ ] Definir requisitos

### Fase 2 — Modelagem

* [ ] Modelar banco de dados
* [ ] Criar diagrama de entidades
* [ ] Definir arquitetura
* [ ] Definir fluxos do sistema

### Fase 3 — Associados

* [ ] Criar entidade `Associado`
* [ ] Implementar cadastro
* [ ] Implementar consulta
* [ ] Implementar atualização
* [ ] Implementar controle de situação
* [ ] Implementar prevenção de duplicidade
* [ ] Implementar histórico

### Fase 4 — Contribuições

* [ ] Criar entidade `Contribuição`
* [ ] Implementar registro de contribuição
* [ ] Associar contribuição ao associado
* [ ] Implementar consulta
* [ ] Implementar histórico de contribuições

### Fase 5 — Interface

* [ ] Criar layout
* [ ] Implementar telas de associados
* [ ] Implementar telas de contribuições
* [ ] Implementar validações
* [ ] Melhorar responsividade

### Fase 6 — Testes

* [ ] Testes de cadastro
* [ ] Testes de duplicidade
* [ ] Testes de atualização
* [ ] Testes de contribuições
* [ ] Testes de histórico
* [ ] Testes com usuários

### Fase 7 — Capacitação e avaliação

* [ ] Criar manual
* [ ] Capacitar usuários
* [ ] Avaliar utilização
* [ ] Corrigir problemas
* [ ] Documentar resultados

---

## 📚 Palavras-chave

**Extensão universitária · Associação comunitária · Desenvolvimento de software · Java · Spring Boot · PostgreSQL · Licenciatura em Computação · Inclusão digital · Desenvolvimento comunitário**

---

## 👨‍💻 Projeto acadêmico

Este projeto está sendo desenvolvido como atividade relacionada à **Licenciatura em Computação**, buscando integrar formação acadêmica, desenvolvimento de software e atuação junto à comunidade.

---

## 📄 Licença

A licença do projeto deverá ser definida de acordo com as orientações da instituição de ensino e as condições estabelecidas com a associação parceira.

---

## 🤝 Contribuição

Durante o desenvolvimento acadêmico, sugestões e melhorias podem ser registradas por meio das **Issues** e **Pull Requests** do repositório.

---

## 📌 Status do projeto

**Em desenvolvimento 🚧**

Os requisitos, modelos, funcionalidades e estrutura técnica poderão ser modificados durante o desenvolvimento conforme as necessidades identificadas junto à associação parceira.
