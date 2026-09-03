# Conversa com a vice-diretora do STR

**Data:** 3 de setembro de 2026  
**Participantes:** joao paulo higino; vice-diretora do STR  
**Tipo:** levantamento inicial (conversa informal)  
**Projeto:** Sistema de Gestão de Associações

---

## Contexto

Primeira conversa com a vice-diretora do STR sobre a proposta de um sistema web para cadastro de associados, histórico e contribuições.

A conversa confirma que o caminho web faz sentido na prática: várias associações já dispõem de internet.

---

## O que foi dito

### Internet e acesso

Várias associações já têm internet. Um sistema acessível pelo navegador seria útil no dia a dia, principalmente na hora de pedir ou emitir documentos do associado — por exemplo a ficha de inscrição.

### Histórico da vida do associado

É importante saber o histórico do associado, não só o cadastro atual.

Muitos saem da associação por motivos diversos e depois voltam. Hoje, nesses retornos, o cadastro muitas vezes precisa ser refeito do zero. Isso perde continuidade e dá retrabalho.

O sistema precisa tratar saída e retorno como parte da vida associativa, sem apagar o que já existe.

### Histórico de contribuições

O histórico de pagamentos também foi apontado como importante. Mesmo quem se desliga e retorna deve continuar vinculado ao que já pagou.

### Carteirinha

Gerar a carteirinha do associado também foi citado como necessidade.

Hoje esse trabalho é chato de fazer no Word. O **CardForge** foi uma solução local para gerar as carteirinhas. Se o projeto avançar, a carteirinha entra como **módulo à parte** do sistema, não como peça da primeira versão.

---

## Problema central identificado

O cadastro atual se comporta como uma ficha solta. Quando a pessoa sai e volta, a ficha é refeita.

O que a vice-diretora descreveu pede o contrário:

1. A pessoa é única (CPF / inscrição).
2. Ela pode ter vários períodos de filiação.
3. O histórico de vida associativa e de contribuições permanece.
4. O retorno reativa o cadastro existente; não cria outro.

---

## Implicações para o sistema

| Necessidade ouvida | O que o sistema precisa fazer |
| --- | --- |
| Associações já têm internet | Manter a proposta de sistema web no navegador |
| Pedir / emitir documentos (ficha de inscrição) | Gerar ou disponibilizar a ficha a partir do cadastro |
| Histórico da vida do associado | Registrar entradas, saídas, retornos e alterações relevantes |
| Saída e retorno frequentes | Reativar sem recadastro; nunca apagar o associado |
| Histórico de contribuições | Manter pagamentos vinculados ao associado, inclusive após desligamento |
| Carteirinha | Gerar carteirinha; no curto prazo, via CardForge |

---

## Relação com o escopo da primeira versão

O README já previa **Associados** e **Contribuições**. A conversa reforça os dois e acrescenta dois pontos que ainda não estavam claros:

1. **Reativação sem recadastro** passa a ser requisito da primeira versão, não melhoria futura.
2. **Ficha de inscrição** e **carteirinha** foram pedidas. A carteirinha já tem ferramenta própria (CardForge). A ficha ainda precisa ser definida: gerar PDF no sistema, imprimir a partir do cadastro, ou só guardar o arquivo.

---

## Dados que o cadastro provavelmente precisa além do README

O CardForge já usa, nas carteirinhas reais, campos que o README ainda não lista:

- RG ou CTPS
- estado civil
- profissão
- cônjuge
- filhos
- foto
- número de inscrição
- data de filiação (que não é a mesma coisa que um único `data_entrada`, se houver vários períodos)

Esses campos devem ser confirmados na próxima conversa, não inventados agora.

---

## O que ainda falta perguntar

Parte disso já foi observada na secretaria (ficha no Word impressa à mão; desligamento sem registro; carta de renúncia na diretoria; documento com supervisão do presidente). O restante vai no questionário para o grupo de representantes:

`docs/levantamento/questionario-google-forms.md`

---

## Próximo passo

Enviar o Google Forms no grupo de representantes e cruzar as respostas com o processo da secretaria e com esta conversa.
