# Regras de negócio

## Associado

- Um associado que se desliga não deve ser apagado.
- O cadastro existente deve ser reutilizado quando a pessoa retornar.
- O histórico anterior deve ser preservado.
- Desligado ou inativo não significa exclusão.
- Um associado poderá possuir vários períodos de filiação.
- Um associado poderá possuir várias contribuições.
- Sair e voltar não cria um novo associado.
- A prevenção de duplicidade deve considerar o CPF.

## Período de filiação

- `data_fim` e `motivo_saida` ficam vazios enquanto o período estiver em curso.
- Um novo período começa quando o associado retorna.

## Documentos

- A secretaria pode emitir documentos com supervisão do presidente.
- A ficha de inscrição e a carteirinha foram identificadas como necessidades, mas seus requisitos ainda precisam ser confirmados.
