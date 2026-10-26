# ADOPTION_QUESTIONS

*Questionário de adoção do Protocolo Universal. As respostas viram o documento de regras
do seu projeto — aquele que o agente lê a cada sessão.*

---

## Como usar

- **Responda antes de começar.** Leva de 30 a 60 minutos. **Comece por A e B**: são as que
  fazem as outras funcionarem. **Se quem homologa e quem constrói são pessoas diferentes —
  ou se quem constrói trabalha sem ler código —, K entra no mínimo.**
- **As respostas viram o documento de regras do projeto**, nesta ordem: a Constituição no
  topo *(`system_prompt_recomendado.md` ou `system_prompt_completo.md`)*, as respostas
  deste questionário embaixo, o documento do modo ativo depois.
- **Campo de resposta vazio fica vazio até a resposta existir.** Deixe em branco e volte:
  é mais honesto que "a definir", e um campo em branco volta a ser lido.
- **Onde a pergunta pede comando, escreva o comando literal.** Quem vai usá-lo é uma
  sessão futura, que chega sem contexto.
- **Exceção nomeada é regra.** A seção que fica de fora recebe a frase "não se aplica,
  porque…", escrita — e assim continua sendo decisão, com motivo legível.
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
adaptar: alteração de schema ou migration; exclusão ou reescrita integral de arquivo lido
só em parte; inclusão de dependência nova; mudança em contrato consumido por terceiros;
qualquer operação sobre ambiente ou dado real; **alteração ou remoção de teste existente**
*(P4)*. *O que mais, no seu domínio, é caro ou irreversível?* (Envio de mensagem a cliente,
cobrança, publicação, alteração de índice de busca, invalidação de cache global,
provisionamento de infra.)

> **Resposta** *(uma operação por linha)*:
>
> -
> -
> -

**A3. Qual é o escopo padrão de uma autorização?** Um arquivo? Um módulo? Uma tarefa
inteira? *Recomendado: um arquivo por vez, até o método estar rodando.* E o que uma
autorização dada no chat, sem alvo, significa neste projeto? *(Recomendado: vale como
pergunta — é o momento de o agente perguntar o alvo.)*

> **Resposta:**
>

**A4. O que é "menor mudança que resolve" neste projeto?** Existe pressão de cobertura, de
lint, de tipagem que forçará mudanças além do pedido? Declare isso como exceção nomeada —
exceção nomeada é regra; a implícita vira brecha.

> **Resposta:**
>

**A5. Quais convenções do código o agente deve seguir mesmo discordando?** Nomes, camadas,
formato de resposta de erro, estilo de tratamento de exceção. *Liste as três que mais doem
quando alguém quebra.* A discordância, e o caminho melhor, vão em `PROPOSTA`.

> **Resposta:**
>
> 1.
> 2.
> 3.

**A6. Onde moram os segredos, e o agente pode abri-los?** Arquivos de ambiente, cofres,
variáveis. Diga quais ficam **fechados** para o agente, quais ele abre **repetindo só o
nome da chave**, e quem faz a mudança quando uma chave precisa mudar. *Segredo nomeado
como segredo fica fora do teste.*

> **Resposta:**
>
> | Onde | O agente pode… | Quem muda |
> |---|---|---|
> | | fechado / abre e repete só o nome | |

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
partir da cópia?** Escreva os dois literalmente — quem vai usá-los é uma sessão futura, que
chega sem contexto.

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
escrever só com o serviço parado.)*

> **Resposta:**
>

**B6. Existe alguma classe de arquivo que fica fora do protocolo?** Gerados, `lock`,
compilados, migrations aplicadas. **Nomeie explicitamente** — exceção nomeada é regra; a
implícita vira porta dos fundos.

> **Resposta** *(uma classe por linha, com o motivo)*:
>
> -

---

## C — Verificação *(P3)*

**C1. O que o seu sistema carrega no boot, e um script isolado ainda precisa carregar?**
Setup de logging, registro de plugins, variáveis de ambiente, migrations, inicialização de
container. **Essa lista é o cabeçalho obrigatório de todo script auxiliar** — com ela você
mede o ambiente real.

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
caminhos** — a regra "leia o registro antes de formular a hipótese" funciona quando se sabe
onde ele está.

> **Resposta** *(um caminho por linha, com o que ele responde)*:
>
> -

**C4. Onde entra a hipótese, e como ela é rotulada?** Se você tem um arquivo de pendências
ou de achados, defina o marcador. *(`HIPÓTESE, A MEDIR` na primeira linha, com o que
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
da árvore. **Escreva o procedimento** — é a etapa que prova, e a que mais depende de estar
escrita para acontecer toda vez.

> **Resposta:**
>
> ```
>
> ```

**D3. Onde a pessoa acompanha o que está rodando?** Terminal, painel, log ao vivo, CI. **Se
ainda está por construir, esse é o primeiro item** — visibilidade é o freio.

> **Resposta:**
>

**D4. Onde ficam os testes, e qual é a convenção de nome?** Inclua a convenção para o teste
que crava default conservador.

> **Resposta:**
>

**D5. O que conta como refatoração sem mudança de comportamento neste projeto?** É a única
isenção legítima da regra "falha antes, passa depois". Defina a fronteira para que ela
continue sendo isenção.

> **Resposta:**
>

**D6. O que se faz com um teste intermitente?** Quantas execuções seguidas provam
estabilidade, onde ele é marcado enquanto está em quarentena, e quem decide se ele sai da
suíte. *Com isso escrito, o procedimento é decisão — e "rodar de novo até passar" fica fora
dele.*

> **Resposta:**
>

**D7. Quem autoriza a alteração de um teste existente, e onde a justificativa fica?** Mudar
valor esperado, afrouxar ou remover asserção, pular, alargar tolerância, regenerar *snapshot*
— tudo é alteração de teste. *(Recomendado: entra na lista A2; a justificativa vai na seção
de testes alterados do documento de homologação, com a diferença exibida.)* E: **de onde vem o
valor esperado de um teste novo neste projeto** — especificação, decisão registrada,
comportamento combinado — e quem decide quando os três faltam?

> **Resposta:**
>
> | Quem autoriza alterar teste | Onde fica a justificativa | De onde vem o valor esperado | Quem decide na falta de especificação |
> |---|---|---|---|
> | | | | |

---

## E — Mudança de comportamento *(P5)*

**E1. Onde vive a configuração, e existe separação entre o default do repositório e a
escolha local?** Se ainda está por criar, crie: é o que permite o default nascer conservador
e respeitar quem já decidiu.

> **Resposta:**
>

**E2. Qual é a função que lê a config viva?** Nome exato. Constante de módulo lida no import
congela o valor; a função que lê em tempo de execução é a que serve.

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

**E4. Como se mede cada um desses custos?** Comando concreto. Com o comando escrito, "custo
medido" é medido.

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

**F2. Quem decide?** E, mais importante: **quais decisões pertencem a outra pessoa?** Custo,
dependência nova, contrato externo, mudança visível ao usuário, escolha de fornecedor.

> **Resposta:**
>
> | Decisão | De quem é |
> |---|---|
> | | |

**F3. Quais restrições não-técnicas do seu produto precisam estar escritas para ficarem
decididas de vez?** Exemplos reais: "não pode exigir serviço rodando na máquina do
usuário", "não pode depender de rede no boot", "não pode custar mais de X por mês", "tem
que rodar offline". **Estas são as que mais se perdem, e as que mais custam quando alguém as
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

**G2. Qual é o formato de resposta esperado?** Adapte o bloco de cinco seções ao seu
contexto — o essencial é que **o que falta para responder com certeza** tenha uma seção
própria, que **achados fora do escopo** tenham outra, e que **a saída melhor que o agente
viu** tenha lugar para ser lida.

> **Resposta:**
>
> ```
> MUDANÇA
> POR QUÊ
> ACHADOS
> PROPOSTA       a saída melhor que o agente viu, para quem decide
> PRECISO VER
> ```

**G3. Qual é o limite de tamanho de uma proposta antes de virar anexo?** *(O protocolo
sugere 200 linhas de teoria.)*

> **Resposta:**
>

**G4. Em que língua o projeto é escrito** — código, comentário, commit, documento? Manter
isso poupa atrito diário.

> **Resposta:**
>
> | Código | Comentário | Commit | Documento |
> |---|---|---|---|
> | | | | |

---

## H — A IA dentro do sistema *(P8)*

*Se o produto tem IA, responda. Se ainda está sem IA, escreva aqui "não se aplica: o
produto está sem IA" e siga — exceção nomeada é regra.*

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
publicar, aprovar. **Cada uma delas acontece com confirmação humana** — escreva a lista.

> **Resposta** *(uma ação por linha)*:
>
> -

**H4. Onde moram os prompts, e qual é a função que os carrega?** Se ainda está por criar,
é o primeiro item — antes de escrever o primeiro prompt.

> **Resposta:**
>

**H5. Existe recarga a quente de prompt?** Se sim, monte o schema sob demanda — é o que faz
a edição valer na próxima leitura.

> **Resposta:**
>

**H6. Onde é o gate — o ponto único por onde toda execução de ferramenta passa?** Se ainda
está por construir, é a primeira coisa: **é o gate que faz a restrição valer.**

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
os casos que passaram sem perguntar? *(Registrando também o que passou, a pergunta "por que
isso rodou sem me avisar?" ganha resposta.)*

> **Resposta:**
>

**H9. Por onde entra texto de fora do controle do sistema** — arquivos do usuário, páginas,
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
acontece ao estourar. **Escreva os números** — teto é o que está escrito, e é o que a
fatura respeita.

> **Resposta:**
>
> | Laço | Chamadas por pedido | Condição de parada | Ao estourar |
> |---|---|---|---|
> | | | | |

---

## I — Registro *(P9)*

**I1. Os três canais existem?** O que a máquina fez, **o que o sistema contou ao modelo**, e
o que o modelo disse. **Se o canal 2 ainda está por construir, esse é o primeiro item** — é
ele que distingue modelo mal informado de modelo que errou.

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
importa do sistema que protege? *(Se sim: torne-a neutra — uma cópia só.)*

> **Resposta:**
>

**I8. Que perguntas você quer conseguir responder daqui a seis meses?** Escreva-as. **São
elas que definem o que registrar.** Exemplos: *"por que essa ação rodou sem me
perguntar?"*, *"qual modelo decidiu isto?"*, *"o sistema entregou o texto inteiro ou
cortado?"*, *"quanto custou este turno?"*

> **Resposta** *(uma pergunta por linha)*:
>
> -

---

## J — Sessão e Handoff *(P10)*

**J1. Este trabalho cabe numa sessão?** Se é maior que isso — e trabalho grande se faz por
setores — **crie os três artefatos antes de começar**: mapa, achados, retomada.

> **Resposta:**
>
> | Artefato | Caminho |
> |---|---|
> | Mapa | |
> | Achados | |
> | Retomada | |

**J2. Quais são os limites de orçamento da sua janela?** Número de arquivos editados, de
arquivos lidos sem achado, de setores. **Escreva os números** — limite é o que está
escrito.

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
tipos, como subir o sistema. **Vão na retomada, literalmente** — quem vai usá-los chega sem
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

## K — Homologação *(P11)*

*Se quem constrói é quem homologa, e lê código, escreva isso em K1 e responda K2 mesmo
assim: aprovação com registro é registro; a de memória é relatório. Se quem constrói
trabalha sem ler código, esta seção é a que faz a entrega chegar a quem aprova com
evidência escrita.*

**K1. Quem homologa neste projeto — e é a mesma pessoa que autoriza (A1)?** Se for outra
pessoa: ela lê código? A resposta define para quem o documento de homologação é escrito, e
em que linguagem.

> **Resposta:**
>
> | Quem homologa | É quem autoriza? | Lê código? |
> |---|---|---|
> | | | |

**K2. Onde fica o documento de homologação, e como se chama?** Um arquivo por entrega,
numerado, em pasta própria e versionado com o código é o desenho mais simples de cobrar.

> **Resposta:**
>

**K3. O que quem homologa exige ver em toda entrega?** A lista-base: a saída de cada teste,
colada; a saída contra o código de antes; os testes alterados, com a diferença e o motivo; o
passo a passo para ver funcionando; as execuções delegadas, com comando e reversão. *O que
mais, no seu domínio?* (Captura de tela, dado de exemplo, medição de custo, a saída de um
comando específico.)

> **Resposta** *(um item por linha)*:
>
> - saída de cada teste, colada
> - saída contra o código de antes
> - testes alterados, com a diferença e o motivo
> - passo a passo para ver funcionando
> - execuções delegadas, com comando e reversão
> -

**K4. O que quem constrói executa sozinha, e o que executa com ajuda?** Terminal, container,
variável de ambiente, instalação de dependência, banco, publicação. **O que ela executa com
ajuda é a lista do que o agente oferece fazer por ela; o que está fora do alcance dela
avaliar é a lista do que sobe para quem homologa antes de executar.**

> **Resposta:**
>
> | Etapa | Executa sozinha? | O agente faz por ela, depois do "sim"? | Sobe para quem homologa? |
> |---|---|---|---|
> | terminal | | | |
> | container | | | |
> | variável de ambiente | | | |
> | instalação de dependência | | | |
> | banco | | | |
> | publicação | | | |

**K5. Quais operações sobem sempre para quem homologa, mesmo com o "sim" de quem constrói?**
Publicar em produção, apagar dado real, pagar, trocar segredo de produção. É a lista A2
vista por quem homologa: o que pede a assinatura dela.

> **Resposta** *(uma operação por linha)*:
>
> -
> -

**K6. Qual é o critério de recusa, escrito antes da primeira entrega?** A lista-base: teste
alterado sem justificativa; teste sem saída contra o velho; execução delegada sem registro;
documento escrito no fim, de memória; veredicto preenchido pelo agente. **Com o critério
escrito, a recusa é previsível e a aprovação tem peso.**

> **Resposta** *(um critério por linha)*:
>
> - teste alterado sem justificativa na seção própria
> - teste sem saída contra o código de antes
> - execução delegada sem comando, saída e reversão escritos
> - documento de homologação escrito no fim
> - veredicto preenchido pelo agente
> -

---

## O que fazer com as respostas

1. **Monte o documento de regras do projeto:** a Constituição no topo, estas respostas
   embaixo, o documento do modo ativo depois. Um arquivo, na raiz, com o nome que o seu
   projeto usa para isso.
2. **Confira o mínimo que já vale:** A1, A2, A3, B1, B2, B3 e B4 respondidos. Com esses
   sete, a regra "toda edição começa com o alvo nomeado" já muda o comportamento do agente
   na primeira sessão.
3. **Diga ao agente qual modo está ativo.** Enquanto o modo está por declarar, vale
   construção.
4. **Se quem homologa e quem constrói são pessoas diferentes, K1 e K2 entram no mínimo.**
   Com eles, a entrega chega a quem aprova com evidência — e a suíte verde ganha
   companhia: a saída de cada teste e a lista dos testes alterados.
5. **Revise quando uma resposta mudar de fato.** Toda revisão atualiza o cabeçalho, e uma
   resposta que muda porque uma decisão foi tomada aponta para o ADR que a tomou.

---

*© 2026 Ivana Cruz · ivana.gac@gmail.com · Este documento é licenciado sob [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*
