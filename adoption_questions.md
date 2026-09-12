# ADOPTION_QUESTIONS

*Questionário de adoção do Protocolo Universal. As respostas viram o documento de regras
do seu projeto — aquele que o agente lê a cada sessão.*

---

## Como usar

- **Responda antes de começar.** Leva de 30 a 60 minutos. **Não pule A e B**: são as que
  fazem as outras funcionarem.
- **As respostas viram o documento de regras do projeto**, nesta ordem: a Constituição no
  topo *(`system_prompt_recomendado.md` ou `system_prompt_completa.md`)*, as respostas
  deste questionário embaixo, o documento do modo ativo depois.
- **Campo de resposta vazio fica vazio até a resposta existir.** "A definir" não é
  resposta; é um campo vazio com cara de preenchido. Deixe em branco e volte.
- **Onde a pergunta pede comando, escreva o comando literal.** Quem vai usá-lo é uma sessão
  futura sem contexto nenhum.
- **Exceção só existe se estiver nomeada.** Uma seção que não se aplica recebe a frase
  "não se aplica, porque…" — nunca fica em branco por omissão.
- As marcas *(P1)*, *(P2)*… apontam para o protocolo correspondente em
  `protocolo_universal.md`, onde está a regra que cada pergunta faz caber no projeto.

## Cabeçalho do projeto

| Campo | Resposta |
|---|---|
| Projeto | |
| Respondido por | |
| Data | |
| Modo padrão *(construção, salvo palavra em contrário)* | |
| Última revisão destas respostas | |

---

## A — Autorização *(P1)*

**A1. Quem autoriza mudança neste projeto?** Uma pessoa, um papel, um par revisor? Se for
você mesmo, a autorização ainda existe — ela vira uma pausa deliberada entre investigar e
agir.

> **Resposta:**
>

**A2. Quais operações exigem confirmação explícita antes, sempre?** A lista-base para
adaptar: alteração de schema ou migration; exclusão ou reescrita integral de arquivo não
lido por completo; inclusão de dependência nova; mudança em contrato consumido por
terceiros; qualquer operação sobre ambiente ou dado real. *O que mais, no seu domínio, é
caro ou irreversível?* (Envio de mensagem a cliente, cobrança, publicação, alteração de
índice de busca, invalidação de cache global, provisionamento de infra.)

> **Resposta** *(uma operação por linha)*:
>
> -
> -
> -

**A3. Qual é o escopo padrão de uma autorização?** Um arquivo? Um módulo? Uma tarefa
inteira? *Recomendado: um arquivo por vez, até o método estar rodando.* E o que uma
autorização dada no chat, sem alvo, significa neste projeto? *(Recomendado: nada — o agente
pergunta o alvo.)*

> **Resposta:**
>

**A4. O que é "menor mudança que resolve" neste projeto?** Existe pressão de cobertura, de
lint, de tipagem que forçará mudanças além do pedido? Declare isso como exceção nomeada, ou
ela vira brecha.

> **Resposta:**
>

**A5. Quais convenções do código o agente deve seguir mesmo discordando?** Nomes, camadas,
formato de resposta de erro, estilo de tratamento de exceção. *Liste as três que mais doem
quando alguém quebra.*

> **Resposta:**
>
> 1.
> 2.
> 3.

**A6. Onde moram os segredos, e o agente pode abri-los?** Arquivos de ambiente, cofres,
variáveis. Diga quais o agente **não abre**, quais abre **sem repetir o valor**, e quem faz
a mudança quando uma chave precisa mudar. *Segredo que o agente não sabe que é segredo vai
parar num teste.*

> **Resposta:**
>
> | Onde | O agente pode… | Quem muda |
> |---|---|---|
> | | não abre / abre sem repetir | |

---

## B — Reversibilidade *(P2)*

**B1. Onde fica o registro de alterações, e como se chama?** *(Um arquivo append-only na
raiz é o mais simples e o mais difícil de ignorar.)*

> **Resposta:**
>

**B2. Onde ficam as cópias físicas, e elas entram no versionamento?** *(Fora do
versionamento é o comum; o que importa é estarem fora do alcance da edição.)*

> **Resposta:**
>

**B3. Qual comando calcula hash na sua plataforma, e qual comando reverte um arquivo a
partir da cópia?** Escreva os dois literalmente — quem vai usá-los é uma sessão futura sem
contexto.

> **Resposta:**
>
> ```
> hash:
> reverter:
> ```

**B4. O que precisa ser reiniciado depois de cada tipo de mudança?** A tabela vai para o
campo "reiniciar" de toda entrada do registro.

> **Resposta:**
>
> | Tipo de mudança | O que reiniciar |
> |---|---|
> | | backend / worker / frontend / nada |

**B5. Existe banco com log de escrita adiada?** Se sim: qual é a API de backup que
consolida, e qual é o procedimento para escrever com o serviço no ar? *(Ou a decisão de
nunca escrever com o serviço no ar.)*

> **Resposta:**
>

**B6. Existe alguma classe de arquivo que fica fora do protocolo?** Gerados, `lock`,
compilados, migrations aplicadas. **Nomeie explicitamente** — exceção não nomeada vira
porta dos fundos.

> **Resposta** *(uma classe por linha, com o motivo)*:
>
> -

---

## C — Verificação *(P3)*

**C1. O que o seu sistema carrega no boot que um script isolado não carrega?** Setup de
logging, registro de plugins, variáveis de ambiente, migrations, inicialização de
container. **Essa lista é o cabeçalho obrigatório de todo script auxiliar** — sem ela você
mede um ambiente que não existe.

> **Resposta:**
>
> -

**C2. Como se descobre se o processo no ar tem o código que está em disco?** Comando
concreto: horário de início do processo, endpoint de versão, hash do build.

> **Resposta:**
>
> ```
>
> ```

**C3. Onde ficam os registros que respondem "o que aconteceu de verdade"?** Logs de
aplicação, histórico de execuções, mensagens persistidas, trilha de auditoria. **Liste os
caminhos** — a regra "leia o registro antes de formular a hipótese" só funciona se você
souber onde ele está.

> **Resposta** *(um caminho por linha, com o que ele responde)*:
>
> -

**C4. Onde entra a hipótese, e como ela é rotulada?** Se você tem um arquivo de pendências
ou de achados, defina o marcador. *(`HIPÓTESE, NÃO MEDIDA` na primeira linha, com o que
decidiria a questão.)*

> **Resposta:**
>

---

## D — Testes *(P4)*

**D1. Qual é o comando que roda a suíte, e quanto tempo ele leva?** Se leva mais de dois
minutos, defina também o subconjunto rápido.

> **Resposta:**
>
> ```
> suíte completa:            (tempo:      )
> subconjunto rápido:        (tempo:      )
> ```

**D2. Como se roda a suíte contra o código de antes?** `git stash`, branch, worktree, cópia
da árvore. **Escreva o procedimento** — é a etapa que mais é pulada, e é a que prova.

> **Resposta:**
>
> ```
>
> ```

**D3. Onde a pessoa acompanha o que está rodando?** Terminal, painel, log ao vivo, CI. **Se
a resposta é "não existe", esse é o primeiro item a construir** — sem visibilidade, não há
freio.

> **Resposta:**
>

**D4. Onde ficam os testes, e qual é a convenção de nome?** Inclua a convenção para o teste
que crava default conservador.

> **Resposta:**
>

**D5. O que conta como refatoração sem mudança de comportamento neste projeto?** É a única
isenção legítima da regra "falha antes, passa depois". Defina a fronteira antes que ela
vire desculpa.

> **Resposta:**
>

**D6. O que se faz com um teste intermitente?** Quantas execuções seguidas provam
estabilidade, onde ele é marcado enquanto está em quarentena, e quem decide se ele sai da
suíte. *Sem isso, "rodar de novo até passar" vira o procedimento padrão sem ninguém ter
decidido.*

> **Resposta:**
>

---

## E — Mudança de comportamento *(P5)*

**E1. Onde vive a configuração, e existe separação entre o default do repositório e a
escolha local?** Se não existe, crie: é o que permite o default nascer conservador sem
atrapalhar quem já decidiu.

> **Resposta:**
>

**E2. Qual é a função que lê a config viva?** Nome exato. Constante de módulo lida no import
não serve — congela o valor.

> **Resposta:**
>

**E3. Quais custos precisam de número medido antes de mudar?** Latência, chamadas a serviço
pago, uso de memória, tamanho de bundle, tempo de build. *Defina o limiar a partir do qual
vira decisão de outra pessoa.*

> **Resposta:**
>
> | Custo | Limiar a partir do qual é decisão de quem paga |
> |---|---|
> | | |

**E4. Como se mede cada um desses custos?** Comando concreto. Sem isso, "custo medido" vira
"custo estimado".

> **Resposta:**
>
> | Custo | Comando que mede |
> |---|---|
> | | |

---

## F — Decisão registrada *(P6)*

**F1. Onde ficam os registros de decisão, e qual é o esquema de numeração?**

> **Resposta:**
>

**F2. Quem decide?** E, mais importante: **quais decisões não são suas para tomar?** Custo,
dependência nova, contrato externo, mudança visível ao usuário, escolha de fornecedor.

> **Resposta:**
>
> | Decisão | De quem é |
> |---|---|
> | | |

**F3. Quais restrições não-técnicas do seu produto precisam estar escritas para não serem
reabertas?** Exemplos reais: "não pode exigir serviço rodando na máquina do usuário", "não
pode depender de rede no boot", "não pode custar mais de X por mês", "tem que rodar
offline". **Estas são as que mais se perdem, e as que mais custam quando alguém as
reabre.**

> **Resposta** *(uma restrição por linha, com quem a impôs)*:
>
> -

**F4. Este projeto é migração de legado?** Se sim: qual é a fronteira do estrangulamento
(rota, módulo, domínio), e quem escreve o critério de paridade antes de cada movimento?

> **Resposta:**
>

---

## G — Ritmo e comunicação *(P7)*

**G1. A pessoa acompanha ao vivo ou revisa depois?** Ao vivo → uma etapa por resposta,
sempre. Revisa depois → o lote pode ser maior, mas o registro tem que ser mais completo,
porque ele é a única testemunha.

> **Resposta:**
>

**G2. Qual é o formato de resposta esperado?** Adapte o bloco de quatro seções ao seu
contexto — o essencial é que **o que falta para responder com certeza** tenha uma seção
própria, e que **achados fora do escopo** tenham outra.

> **Resposta:**
>
> ```
> MUDANÇA
> POR QUÊ
> ACHADOS
> PRECISO VER
> ```

**G3. Qual é o limite de tamanho de uma proposta antes de virar anexo?** *(O protocolo
sugere 200 linhas de teoria.)*

> **Resposta:**
>

**G4. Em que língua o projeto é escrito** — código, comentário, commit, documento? Divergir
disso é atrito diário.

> **Resposta:**
>
> | Código | Comentário | Commit | Documento |
> |---|---|---|---|
> | | | | |

---

## H — A IA dentro do sistema *(P8)*

*Se o produto não tem IA, escreva aqui "não se aplica: o produto não tem IA" e pule a
seção. Exceção nomeada, não omissão.*

> **Aplica-se?**
>

**H1. Quais tarefas manuais são candidatas?** Para cada uma, as seis perguntas do
mapeamento: quem, frequência, entrada, decisão, o que grava, o que acontece quando erra.

> **Resposta:**
>
> | Tarefa | Quem | Frequência | Entrada | Decisão | O que grava | Quando erra |
> |---|---|---|---|---|---|---|
> | | | | | | | |

**H2. Quais dessas tarefas uma regra determinística resolve?** Tire-as da lista. **Costuma
ser a maioria** — e é a economia mais barata que existe.

> **Resposta:**
>

**H3. Quais ações do seu sistema são irreversíveis?** Enviar, pagar, cancelar, excluir,
publicar, aprovar. **Nenhuma delas é executada por IA sem confirmação humana** — escreva a
lista.

> **Resposta** *(uma ação por linha)*:
>
> -

**H4. Onde moram os prompts, e qual é a função que os carrega?** Se ainda não existe, esse é
o primeiro item — antes de escrever o primeiro prompt.

> **Resposta:**
>

**H5. Existe recarga a quente de prompt?** Se sim, o schema tem que ser montado sob demanda,
não no import.

> **Resposta:**
>

**H6. Onde é o gate — o ponto único por onde toda execução de ferramenta passa?** Se não
existe ponto único, essa é a primeira coisa a construir: **sem ele, restrição é decoração.**

> **Resposta:**
>

**H7. Alguma ferramenta alcança outras por dentro?** Ponte, sandbox, executor de código,
sub-agente. Essas escapam do gate por construção — decida agora o que fazer com elas.

> **Resposta:**
>
> | Ferramenta | O que alcança | Decisão |
> |---|---|---|
> | | | |

**H8. Onde fica o registro auditável das decisões da IA?** E ele registra **o silêncio** —
os casos que passaram sem perguntar? *(Se registra só o que nega ou pergunta, a pergunta
"por que isso rodou sem me avisar?" fica sem resposta possível.)*

> **Resposta:**
>

**H9. Por onde entra texto que o sistema não controla** — arquivos do usuário, páginas,
mensagens, resultados de busca, saída de outro modelo — **e como esse texto chega ao modelo
marcado como dado?** E o gate: uma chamada de ferramenta que nasceu desse texto passa por
ele como qualquer outra? *(Se a resposta é "o prompt manda ignorar instruções embutidas",
releia a lei do P8.)*

> **Resposta:**
>
> | Entrada | Como chega marcada como dado | Passa pelo gate? |
> |---|---|---|
> | | | |

**H10. Qual é o teto de cada laço?** Chamadas por pedido, condição de parada, o que
acontece ao estourar. **Escreva os números** — teto que não está escrito não é teto, e
quem descobre isso é a fatura.

> **Resposta:**
>
> | Laço | Chamadas por pedido | Condição de parada | Ao estourar |
> |---|---|---|---|
> | | | | |

---

## I — Registro *(P9)*

**I1. Os três canais existem?** O que a máquina fez, **o que o sistema contou ao modelo**, e
o que o modelo disse. **Se o canal 2 não existe, esse é o primeiro item** — sem ele você não
consegue distinguir modelo que mentiu de modelo que foi mal informado.

> **Resposta:**
>
> | Canal | Existe? | Onde |
> |---|---|---|
> | 1 — o que a máquina fez | | |
> | 2 — o que o sistema contou ao modelo | | |
> | 3 — o que o modelo disse | | |

**I2. Onde é o ponto único por onde toda chamada ao modelo passa?** E toda execução de
ferramenta? Se são muitos pontos, o trabalho é reduzi-los antes de instrumentar. *(Costuma
haver menos portas do que parece: muitos "imports do cliente" são só o tipo.)*

> **Resposta:**
>

**I3. Você usa SDK ou conexão pura?** Se SDK: aceita que o registro para no que foi entregue
a ele, ou vai manter os dois caminhos vivos para medir a diferença?

> **Resposta:**
>

**I4. Quais campos de correlação viajam em toda linha?** A lista-base: sessão, turno, quem
pediu (provedor/modelo), intenção (o que disparou), procedência (arquivo:linha). *Adicione o
que o seu domínio exige.*

> **Resposta:**
>
> -

**I5. Quem decide quanto registrar, e onde essa decisão mora?** Se a resposta é "está no
código", mova para configuração. Se está em configuração que só o time lembra que existe,
**leve para a interface de quem é dono**.

> **Resposta:**
>

**I6. Onde ficam os registros, e por quanto tempo?** Arquivo, banco, ambos? **Escrita dupla
(arquivo primeiro, banco depois) é o desenho seguro.** E: o seu log e o de bibliotecas de
terceiros estão separados?

> **Resposta:**
>

**I7. Qual é a política de redação de segredo, e ela roda antes do armazenamento?** Ela
importa do sistema que protege? *(Se sim: torne-a neutra, ou você terá duas cópias
divergentes.)*

> **Resposta:**
>

**I8. Que perguntas você quer conseguir responder daqui a seis meses?** Escreva-as. **São
elas que definem o que registrar** — não o inverso. Exemplos: *"por que essa ação rodou sem
me perguntar?"*, *"qual modelo decidiu isto?"*, *"o sistema entregou o texto inteiro ou
cortado?"*, *"quanto custou este turno?"*

> **Resposta** *(uma pergunta por linha)*:
>
> -

---

## J — Sessão e Handoff *(P10)*

**J1. Este trabalho cabe numa sessão?** Se não — e trabalho grande nunca cabe — **crie os
três artefatos antes de começar**: mapa, achados, retomada.

> **Resposta:**
>
> | Artefato | Caminho |
> |---|---|
> | Mapa | |
> | Achados | |
> | Retomada | |

**J2. Quais são os limites de orçamento da sua janela?** Número de arquivos editados, de
arquivos lidos sem achado, de setores. **Escreva os números** — limite não escrito não é
limite.

> **Resposta:**
>
> | Limite | Número |
> |---|---|
> | Arquivos editados na sessão | |
> | Arquivos lidos em profundidade sem achado | |
> | Setores por sessão | |

**J3. Como o projeto se divide em setores auditáveis?** Um módulo coeso, ou ~10 arquivos.
Setor grande demais para uma sessão é quebrado em subsetores no próprio mapa.

> **Resposta:**
>

**J4. Quais comandos a próxima sessão precisa saber de cor?** Testes, linter, verificador de
tipos, como subir o sistema. **Vão na retomada, literalmente** — quem vai usá-los não tem
contexto.

> **Resposta:**
>
> ```
> testes:
> linter:
> tipos:
> subir o sistema:
> ```

**J5. O trabalho é arquivo por arquivo?** Se sim, adote o bloco de passagem em vez dos três
artefatos completos — é mais leve e suficiente.

> **Resposta:**
>

---

## O que fazer com as respostas

1. **Monte o documento de regras do projeto:** a Constituição no topo, estas respostas
   embaixo, o documento do modo ativo depois. Um arquivo, na raiz, com o nome que o seu
   projeto usa para isso.
2. **Confira o mínimo que já vale:** A1, A2, A3, B1, B2, B3 e B4 respondidos. Com esses
   sete, a regra "nada é editado sem que o alvo tenha sido nomeado" já muda o comportamento
   do agente na primeira sessão.
3. **Diga ao agente qual modo está ativo.** Sem essa palavra, vale construção.
4. **Revise quando uma resposta mudar de fato** — não por rotina. Toda revisão atualiza o
   cabeçalho, e uma resposta que muda porque uma decisão foi tomada aponta para o ADR que a
   tomou.

---

*© 2026 Ivana Cruz · ivana.gac@gmail.com · Este documento é licenciado sob [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*
