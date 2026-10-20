# Sistema de Gestão de Associações

Sistema web para cadastro e gerenciamento de associados, controle da vida associativa e registro de contribuições financeiras de associações comunitárias.

O projeto tem como objetivo centralizar informações, melhorar a organização administrativa e oferecer maior confiabilidade no acompanhamento dos associados e de suas contribuições.

**Status:** Em desenvolvimento 🚧

## Sobre o projeto

O Sistema de Gestão de Associações está sendo desenvolvido para atender às necessidades administrativas de associações comunitárias, proporcionando uma solução para organizar cadastros, acompanhar períodos de filiação e registrar contribuições.

O desenvolvimento será realizado de forma participativa, considerando as necessidades identificadas junto à associação parceira.

A primeira versão será organizada em dois módulos principais:

- **Associados:** gerenciamento dos dados cadastrais, situação atual e histórico da vida associativa.
- **Contribuições:** registro, consulta e acompanhamento dos pagamentos realizados pelos associados.

O sistema será desenvolvido com foco em integridade dos dados, facilidade de uso, segurança e possibilidade de evolução futura.

## Objetivos

- Centralizar os dados cadastrais dos associados.
- Reduzir duplicidades e inconsistências nos registros.
- Preservar o histórico da vida associativa.
- Registrar desligamentos e reativações sem perder informações anteriores.
- Organizar o registro e a consulta de contribuições.
- Facilitar a consulta de informações e a geração de relatórios.
- Aplicar boas práticas de desenvolvimento, segurança e persistência de dados.

## Funcionalidades planejadas

### 1. Módulo de associados

- Cadastro de associados.
- Consulta e atualização de dados cadastrais.
- Pesquisa por nome, identificador e situação.
- Prevenção de cadastros duplicados.
- Controle da situação do associado.
- Registro de desligamentos.
- Reativação sem necessidade de um novo cadastro.
- Histórico de eventos da vida associativa.
- Registro dos períodos de filiação.
- Preservação dos registros históricos.

Um associado que se desliga não deverá ser excluído simplesmente por deixar de fazer parte da associação. Seu cadastro e histórico serão preservados para permitir consultas e uma eventual reativação, respeitando as regras de retenção de dados aplicáveis.

### 2. Módulo de contribuições

- Registro de contribuições realizadas.
- Consulta ao histórico de pagamentos.
- Associação dos lançamentos ao respectivo associado.
- Registro de valor, data, competência e forma de pagamento.
- Consulta por associado e período.
- Tratamento controlado de lançamentos incorretos.
- Preservação do histórico de correções e cancelamentos.

As regras de cobrança, incluindo periodicidade, valores, pagamentos parciais e identificação de pendências, serão definidas conforme as necessidades da associação parceira.

### 3. Relatórios e indicadores

Funcionalidades previstas para evolução do sistema:

- Total de associados ativos e desligados.
- Consulta de contribuições por período.
- Relatórios financeiros e administrativos.
- Filtros por situação e competência.
- Exportação de dados para CSV.
- Geração de recibos, caso seja necessária.

### 4. Segurança e auditoria

Como o sistema poderá armazenar dados pessoais e informações financeiras, serão consideradas as seguintes medidas:

- Autenticação de usuários autorizados.
- Controle de acesso baseado em permissões.
- Armazenamento seguro de senhas por meio de hash apropriado.
- Validação de dados no backend.
- Proteção dos endpoints da aplicação.
- Registro de operações importantes.
- Preservação do histórico de alterações relevantes.
- Proteção das credenciais e dos dados de configuração.
- Procedimentos de backup e restauração.

Esses recursos serão implementados e validados progressivamente antes da disponibilização para uso real.

## Regras de negócio

O desenvolvimento deverá respeitar as seguintes regras:

1. Um associado não deverá possuir cadastros duplicados conforme os identificadores definidos nos requisitos.
2. O desligamento não deverá apagar automaticamente o cadastro ou o histórico associativo.
3. A reativação deverá preservar os períodos anteriores e registrar um novo período de filiação.
4. As alterações de situação deverão respeitar as regras de negócio estabelecidas.
5. Toda contribuição deverá estar associada ao registro correto do associado.
6. Os lançamentos financeiros deverão possuir validações de valor, data e demais campos obrigatórios.
7. Correções e cancelamentos de contribuições deverão preservar a rastreabilidade das operações.
8. As operações deverão respeitar as permissões do usuário autenticado.
9. As validações críticas deverão ser realizadas no backend, e não apenas na interface.
10. As informações pessoais deverão ser tratadas de acordo com a legislação aplicável e as regras de retenção definidas para o sistema.

## Tecnologias utilizadas

| Tecnologia | Utilização |
|---|---|
| Java 21 | Linguagem principal |
| Spring Boot | Desenvolvimento do backend |
| Spring Web | Criação de endpoints e APIs REST |
| Spring Data JPA | Persistência e acesso aos dados |
| Hibernate | Mapeamento objeto-relacional (ORM) |
| PostgreSQL | Banco de dados relacional |
| HTML5 | Estrutura das páginas |
| CSS3 | Estilização das interfaces |
| JavaScript | Interações no frontend |
| Bootstrap | Componentes e layout responsivo |
| Maven | Gerenciamento de dependências e build |
| Git | Controle de versão |
| GitHub | Hospedagem do código e colaboração |
| JUnit 5 | Testes automatizados |
| Mockito | Apoio a testes unitários |
| Flyway ou Liquibase | Versionamento das alterações do banco, a definir |

A seleção final das dependências e ferramentas poderá ser ajustada durante o desenvolvimento.

## Arquitetura

O projeto adotará uma arquitetura em camadas, buscando separar as responsabilidades e facilitar a manutenção.

- **Controller:** recebe requisições HTTP e organiza as respostas da aplicação.
- **Service:** concentra as regras de negócio e coordena as operações.
- **Repository:** realiza o acesso aos dados por meio do Spring Data JPA.
- **Entity:** representa as entidades persistidas no banco.
- **DTO:** define os dados de entrada e saída da API.
- **Config/Security:** concentra configurações e mecanismos de segurança.
- **Exceptions:** centraliza o tratamento de erros.
- **Auditoria:** registra operações relevantes, conforme as regras definidas.

A aplicação será inicialmente estruturada como um monólito modular, evitando a complexidade desnecessária de microsserviços para o escopo inicial.

### Modelo de dados conceitual

As principais entidades previstas são:

- **Associado:** dados cadastrais e situação atual.
- **Período de filiação:** início, encerramento e informações referentes a cada período de vínculo.
- **Contribuição:** dados dos lançamentos e pagamentos.
- **Usuário:** credenciais, perfil e permissões de acesso.
- **Auditoria:** registros das operações relevantes.

Caso os requisitos financeiros exijam o controle de cobranças e pendências, poderá ser criada uma entidade específica para as obrigações de pagamento, separada dos pagamentos efetivamente realizados.

O modelo definitivo será documentado em `docs/modelagem/`.

## Estrutura da documentação

A documentação do projeto está organizada por assunto dentro da pasta `docs/`:

- [Levantamento](docs/levantamento/) — necessidades identificadas junto à associação.
- [Requisitos](docs/requisitos/) — requisitos funcionais, não funcionais e regras de negócio.
- [Modelagem](docs/modelagem/) — diagramas, entidades e relacionamentos.
- [Desenvolvimento](docs/desenvolvimento/) — arquitetura, decisões técnicas e orientações de implementação.
- [Testes](docs/testes/) — cenários, procedimentos e resultados de testes.
- [Projeto acadêmico](docs/projeto/) — documentação acadêmica e informações do projeto.
- [Manual](docs/manual/) — instruções para utilização do sistema.

## Pré-requisitos

Para executar o projeto localmente, serão necessários:

- Java Development Kit (JDK) 21.
- Maven ou Maven Wrapper disponibilizado no repositório.
- PostgreSQL.
- Git.

Um editor ou ambiente de desenvolvimento compatível com Java também é recomendado.

## Como executar

### 1. Clonar o repositório

```bash
git clone https://github.com/jphs682/gestao_associacao.git
cd gestao_associacao
```

> Caso o nome do diretório criado pelo Git seja diferente, utilize o nome efetivamente gerado no seu ambiente.

### 2. Criar o banco de dados

Acesse o PostgreSQL e execute:

```sql
CREATE DATABASE associacoes;
```

### 3. Configurar a conexão

Configure as propriedades de conexão em `src/main/resources/application.properties`.

Exemplo para desenvolvimento local:

```properties
spring.datasource.url=${DB_URL:jdbc:postgresql://localhost:5432/associacoes}
spring.datasource.username=${DB_USERNAME:postgres}
spring.datasource.password=${DB_PASSWORD}

spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```

A estratégia de criação e atualização do esquema deverá ser configurada conforme o ambiente. Para ambientes compartilhados ou de produção, recomenda-se utilizar migrations versionadas com Flyway ou Liquibase, em vez de depender de atualizações automáticas do Hibernate.

A variável `DB_PASSWORD` deverá ser definida no ambiente antes da execução, ou substituída por uma configuração local apropriada.

**Importante:** não versione senhas reais, tokens ou outras credenciais no repositório. O arquivo de configuração deve conter apenas valores seguros para compartilhamento.

### 4. Executar a aplicação

Com Maven Wrapper no Linux ou macOS:

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

A inicialização dependerá da configuração correta do banco de dados e das dependências do projeto.

O endereço local, as rotas disponíveis e as instruções de acesso à interface serão documentados conforme a implementação evoluir.

## Testes

Os testes serão utilizados para verificar as regras de negócio e reduzir o risco de regressões.

Entre os cenários previstos estão:

- Impedir cadastros duplicados.
- Cadastrar, consultar e atualizar associados.
- Desligar e reativar associados preservando o histórico.
- Registrar e consultar contribuições.
- Rejeitar valores e dados inválidos.
- Bloquear operações não autorizadas.
- Verificar a integridade dos relacionamentos no banco.
- Validar o tratamento de erros.
- Testar backup e restauração dos dados.

Serão considerados testes unitários com JUnit 5 e Mockito, além de testes de integração para validar a interação entre a aplicação e o banco de dados.

A documentação dos cenários e resultados ficará em `docs/testes/`.

## Segurança e proteção de dados

O sistema deverá observar boas práticas de segurança da informação e os requisitos aplicáveis da Lei Geral de Proteção de Dados Pessoais (LGPD).

As medidas previstas incluem:

- Minimização dos dados coletados.
- Controle de acesso conforme as responsabilidades dos usuários.
- Proteção das credenciais.
- Restrições de acesso a informações pessoais e financeiras.
- Cuidados com logs e backups.
- Procedimentos de retenção e descarte de dados.
- Uso de HTTPS em ambientes de produção.
- Definição de procedimentos de recuperação e continuidade.

A preservação do histórico associativo deverá ser conciliada com as obrigações legais e com a política de retenção de dados definida para a associação.

## Boas práticas de desenvolvimento

O desenvolvimento deverá seguir práticas que favoreçam a qualidade e a manutenção do código:

- Separação de responsabilidades.
- Nomes claros para classes, métodos e variáveis.
- Validação consistente dos dados.
- Tratamento centralizado de exceções.
- Uso de transações quando necessário.
- Controle de versão com Git.
- Commits pequenos e descritivos.
- Testes antes da integração de mudanças.
- Documentação das decisões técnicas relevantes.
- Revisão dos requisitos com a associação parceira.

## Contribuição

Durante o desenvolvimento acadêmico, sugestões, correções e melhorias poderão ser registradas por meio das Issues e Pull Requests do repositório.

Antes de propor uma alteração, recomenda-se consultar a documentação e verificar se já existe uma Issue relacionada.

As contribuições deverão respeitar o escopo acadêmico e as condições acordadas com a associação parceira.

## Licença

A licença do projeto será definida conforme as orientações da instituição de ensino e as condições estabelecidas com a associação parceira.

Até que essa definição seja formalizada, não se deve presumir que o código esteja liberado para redistribuição ou uso irrestrito.

## Considerações finais

O Sistema de Gestão de Associações está em desenvolvimento e poderá passar por mudanças conforme os requisitos forem validados.

A prioridade é construir uma solução confiável, segura e de fácil manutenção, que preserve o histórico dos associados, organize as contribuições e atenda às necessidades reais da associação parceira.
