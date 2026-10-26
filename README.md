# Protocolo Universal

*por Ivana Cruz · licenciado sob [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)*

Método de trabalho para desenvolver um sistema com IA — tanto quando a IA **escreve** o
sistema quanto quando a IA **faz parte** do sistema.

O que ele faz: **dá ao agente de IA — que escreve depressa e afirma com confiança — um
método para distinguir o que mediu do que supôs.** Tudo neste repositório existe para tornar
essa diferença visível — declarando antes, medindo depois, e mantendo os dois lado a lado
onde alguém possa comparar.

> **Registro é o que foi declarado antes e comparado depois. Relatório é o que alguém
> lembra ter feito.** Você quer o primeiro.

## O que há aqui

| Arquivo | O que é | Quem lê |
|---|---|---|
| [`protocolo_universal.md`](protocolo_universal.md) | A referência completa: o núcleo em quinze linhas, os seis princípios, os onze protocolos (P1–P11), a tabela de artefatos, o guia de uso, o catálogo de 89 sinais e saídas e o anexo com o exercício de emulação. | Quem adota o método e quem escreve as regras do projeto. |
| [`system_prompt_recomendado.md`](system_prompt_recomendado.md) | A Constituição enxuta — 65 artigos, cerca de 5,3 mil tokens. Deveres e direitos do agente e de quem autoriza. **É a que vai no topo do documento de regras do projeto.** | O agente, a cada sessão. |
| [`system_prompt_completo.md`](system_prompt_completo.md) | A Constituição completa — 122 artigos, um por regra, com definições, hierarquia, precedência em conflito e o exame de fim de resposta. | O agente, quando o projeto prefere a versão autossuficiente; a pessoa, para entender o que cada lado deve e pode exigir. |
| [`adoption_questions.md`](adoption_questions.md) | O questionário de adoção, preenchível — 64 perguntas em onze seções (A–K). As respostas viram o documento de regras do seu projeto. | Quem é dono do projeto, uma vez, antes de começar. |

Os dois `system_prompt_*` dizem **o que vale sempre**; o protocolo diz **como se faz**; o
questionário faz o método **caber no seu projeto**.

## Por onde começar

1. Leia [o núcleo em quinze linhas](protocolo_universal.md#o-núcleo-em-quinze-linhas) e
   [os seis princípios](protocolo_universal.md#os-seis-princípios). Dez minutos.
2. Responda as seções **A** e **B** do [`adoption_questions.md`](adoption_questions.md). As
   outras podem vir depois; essas duas são as que fazem o resto funcionar. **Se quem homologa
   e quem constrói são pessoas diferentes — ou se quem constrói trabalha sem ler código —,
   responda também a seção K.**
3. Monte o **documento de regras do projeto**: `system_prompt_recomendado.md` no topo, as
   suas respostas embaixo, o documento do modo ativo depois. Um arquivo, na raiz do seu
   projeto, com o nome que ele usa para isso.
4. Adote uma regra só: **toda edição começa com o alvo nomeado.** Isso muda o
   comportamento do agente na primeira sessão.
5. **P9 vai primeiro.** Se o sistema já roda, ligue o registro agora — a informação se
   captura no momento em que existe.

A ordem completa de adoção, semana a semana, está no
[guia de uso](protocolo_universal.md#guia-de-uso-no-dia-a-dia).

## Como os arquivos se relacionam

```
protocolo_universal.md ............ a referência: como se faz
    │
    ├── system_prompt_recomendado.md   a Constituição: o que vale sempre ──┐
    │   system_prompt_completo.md      (uma das duas vai no topo)          │
    │                                                                      ├─► documento de regras
    └── adoption_questions.md ........ as respostas do seu projeto ────────┘   do SEU projeto
                                                                                    │
                                                                                    └─► documento de modo
                                                                                        (construção, auditoria…)
```

A hierarquia, de cima para baixo: **a Constituição; o documento de regras do projeto; o
documento do modo ativo; a instrução da sessão.** Cada nível calibra o de cima, dentro do
que ele permite. Instrução de sessão estreita; alargar se faz por escrito, no documento do
projeto. Quatro coisas atravessam todos os modos e valem em toda sessão: a autorização com
alvo nomeado (P1), a cópia física antes de tocar (P2), a prova por execução (P3 — com o
teste intacto quando ele acusa o código, P4) e o documento de homologação escrito enquanto
se constrói (P11).

## Os onze protocolos

| | Protocolo | A regra em uma linha |
|---|---|---|
| **P1** | Autorização | Você lê e reporta livremente. Edição vem com a ordem, e a ordem nomeia o alvo. |
| **P2** | Reversão | Cópia física, hash e declaração antes de tocar; a declaração fica como foi escrita. |
| **P3** | Verificação | Ler produz hipótese; só rodar produz fato. Suspeite do instrumento antes do sistema. |
| **P4** | Testes | Teste que falha no código antigo e passa no novo é prova. Teste que acusa o código fica como está; o conserto vai para a causa. |
| **P5** | Mudança de comportamento | Nasce desligada, com o custo medido ao lado. Quem liga é quem paga. |
| **P6** | Decisão (ADR) | Duas soluções para a mesma necessidade? Mostre as duas, liste o custo, peça a decisão e registre. |
| **P7** | Ritmo e comunicação | Uma etapa que altera estado por resposta. "ok" responde à última coisa dita. |
| **P8** | IA dentro do sistema | Instrução é regra quando verificada; até lá, é sugestão. Restrição é estrutura mais gate. |
| **P9** | Registro (logs) | A informação se captura no momento em que existe. Registre os três canais. |
| **P10** | Sessão e handoff | O estado do trabalho vive em disco — é de lá que a próxima sessão parte. |
| **P11** | Homologação | Tudo o que é produzido produz, ao mesmo tempo, a evidência para quem homologa. O que a pessoa ainda executa com ajuda, o agente faz por ela — depois do "você aprova que eu faça isso por você?" — e deixa escrito. |

Cada protocolo tem quatro partes, sempre na mesma ordem: **REGRA**, **ONDE CABE**,
**PERGUNTAS DE OPERAÇÃO** (as que se respondem toda vez) e **PERGUNTAS DE ADOÇÃO** (as que o
projeto responde uma vez).

## O tom: orientação, e reconhecimento

Os documentos deste repositório são escritos como **orientação positiva**: cada regra diz o
que fazer, com o verbo da ação e o alvo na frase — "edite o alvo nomeado, depois do OK" —,
e a força vem da precisão ("só", "um por vez", "antes") e da verificação mecânica atrás.

Acertar inclui parar. A pergunta pelo alvo, o "não sei", a pausa no limite do orçamento e a
proposta de um caminho melhor são **o método funcionando**, e os documentos os reconhecem
como tal. Por isso toda resposta tem a seção `PROPOSTA`: a saída melhor que o agente viu —
alternativa, simplificação, caminho que custa menos — escrita para quem decide, que a lê e
responde: adota, ou registra a recusa com o motivo. As duas respostas são boas.

## Como fazer o agente seguir isto

Três camadas, da mais fraca para a mais forte:

1. **Instrução** — a Constituição no topo do documento de regras, escrita como orientação
   precisa — o verbo da ação e o alvo na frase —, com a verificação mecânica atrás.
2. **As perguntas de operação**, executadas no fim de cada resposta — o exame de fim de
   resposta da Constituição é a versão curta. Peça que apareçam.
3. **Verificação mecânica** — hook que só aceita commit com entrada no registro; teste que
   confere que todo arquivo alterado tem cópia física; CI que roda a suíte contra o commit
   anterior; CI que só aceita alteração em arquivo de teste quando há justificativa na
   seção de testes alterados do documento de homologação; gate que confere toda chamada de
   ferramenta antes de executar.

**Instrução é regra quando verificada; até lá, é sugestão** — a lei do P8 vale para o
agente também, e vale para a própria Constituição.

## Se quem constrói não lê código

É o caso mais comum hoje: a pessoa pede, a IA escreve, e outra pessoa — que lê código —
aprova. O método tem três respostas para ele, e as três são obrigatórias:

- **O documento de homologação** *(P11)* é escrito enquanto o sistema é construído, desde o
  primeiro item, e vai para quem aprova: o pedido, o que foi entregue, como ver funcionando,
  cada teste com a saída real e a saída contra o código de antes, **os testes alterados em
  seção própria**, tudo o que a IA executou no lugar da pessoa, o pendente de verificação —
  e o veredicto, que só quem homologa preenche. Entrega é código mais documento de
  homologação: a entrega está completa quando o documento a acompanha.
- **Teste que acusa o código fica como está; o conserto vai para a causa** *(P4)*. Quando
  um teste acusa o código, a IA lê o código, escreve onde está o defeito, e só então toca —
  no que está errado, com autorização. Alterar um teste existente é operação da lista de
  confirmação. Suíte verde é ausência de evidência contrária. A evidência é a saída de
  cada teste contra o código de antes e a lista dos testes alterados.
- **A execução delegada** *(P11)*. Container, variável de ambiente, terminal: o que a
  pessoa ainda executa com ajuda, a IA oferece fazer por ela — explicando em linguagem dela
  o que, onde, o que muda, como desfazer e o que custa — e pergunta, literalmente, **"você
  aprova que eu faça isso por você?"**. Uma operação por pergunta. Depois do sim, faz, e
  deixa escrito o comando, a saída e a reversão para quem homologa ler. O que é
  irreversível, e cuja consequência está fora do alcance da pessoa, sobe para quem homologa
  antes do "sim".

## O que este repositório deixa para o seu projeto

Tudo aqui é genérico por decisão: caminho de arquivo, domínio e sistema identificável são do
seu projeto. Onde há exemplo, ele é substituível. O nome, o formato e o lugar de cada
artefato — registro de alterações, ADR, mapa, achados, retomada — são decisão do seu
projeto, e o questionário existe para você tomá-la.

## Emendas

A Constituição e o protocolo mudam por **decisão registrada** (ADR, P6), com as opções
recusadas escritas — a instrução de sessão aponta o atrito; a emenda se faz no documento, e
o motivo é um padrão que se repete, com mais de uma ocorrência. Se uma etapa está sendo
pulada toda vez, ela está no lugar errado: mova o atrito ou automatize a etapa, por escrito
— essa é uma `PROPOSTA` bem-vinda.

## Licença e autoria

© 2026 **Ivana Cruz** — ivana.gac@gmail.com

Este repositório — o protocolo, as duas constituições, o questionário e este README — é
licenciado sob a **[Creative Commons Atribuição-CompartilhaIgual 4.0 Internacional
(CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/)**. O texto legal está em
[`LICENSE.md`](LICENSE.md) e no
[site da Creative Commons](https://creativecommons.org/licenses/by-sa/4.0/legalcode).

Em uma linha: você pode copiar, adaptar e usar, inclusive comercialmente, desde que **dê o
crédito**, **indique o que mudou** e **distribua o derivado sob a mesma licença**. O
documento de regras que o seu projeto gera a partir daqui é um derivado — se você o
distribuir publicamente, o CompartilhaIgual vale para ele; uso interno não obriga a nada.

Atribuição sugerida:

> "Protocolo Universal", de Ivana Cruz, licenciado sob
> [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
