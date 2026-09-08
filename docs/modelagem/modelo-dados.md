# Modelo de dados

## Relacionamentos principais

```text
              ASSOCIADO
             /         \
            / 1         \ 1
           /             \
          / N             \ N
         ▼                 ▼
  PERÍODO DE           CONTRIBUIÇÃO
   FILIAÇÃO
```

Um associado poderá possuir vários períodos de filiação e várias contribuições. Sair e voltar não cria um novo associado.

## Entidade Associado

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

### Situação

Inicialmente, poderão ser utilizadas as seguintes situações:

- **Ativo**
- **Inativo**
- **Desligado**

**Desligado** ou **Inativo** não significa exclusão. A pessoa continua no sistema, com histórico visível, pronta para ser reativada se voltar.

## Entidade Período de filiação

```text
PeriodoFiliacao
├── id
├── associado_id
├── data_inicio
├── data_fim
└── motivo_saida
```

`data_fim` e `motivo_saida` ficam vazios enquanto o período estiver em curso. Um novo período começa quando o associado retorna.

## Entidade Contribuição

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

## Dados cadastrais previstos

- Nome
- CPF
- Data de nascimento
- Telefone
- Endereço
- Data de entrada na associação
- Situação do associado

Campos adicionais — RG/CTPS, estado civil, profissão, cônjuge, filhos, foto e número de inscrição — aparecem nas carteirinhas geradas atualmente e devem ser confirmados no próximo levantamento.
