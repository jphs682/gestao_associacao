# Processo atual observado na secretaria

**Data:** 3 de setembro de 2026  
**Fonte:** experiência do estudante como secretário de uma associação  
**Uso:** complementar a conversa com a vice-diretora do STR

---

## Como é feito hoje

### Ficha de inscrição

As fichas são montadas no Word, impressas e preenchidas à mão.

Não há cadastro digital do associado. O papel é o registro.

### Desligamento

Na associação observada, quando um associado comum se desliga, **não fica registro**.

Se quem sai é membro da diretoria, é feita uma **carta de renúncia**.

### Emissão de documentos

A secretaria pode emitir documentos, mas **com supervisão do presidente**.

Isso pede dois papéis no sistema, no mínimo:

- quem elabora (secretaria)
- quem autoriza (presidência)

### Carteirinha

O CardForge foi uma solução local para não fazer carteirinha à mão no Word. Não é o sistema da associação.

Se o projeto avançar, a carteirinha entra como **módulo à parte** do sistema web, não como dependência do CardForge.

---

## O que isso confirma para os requisitos

- Cadastro hoje é papel; o sistema precisa substituir a ficha refeita e a ficha perdida.
- Desligamento sem registro é o caso real a tratar, não a exceção.
- Diretoria e associado comum podem ter fluxos diferentes de saída.
- Documento emitido pela secretaria não sai sozinho: precisa do crivo do presidente.
- Carteirinha é módulo futuro, separado de Associados e Contribuições.
