# GLOSSÁRIO DA TRADUÇÃO — português → inglês

*O registro de decisão da versão em inglês do Protocolo Universal. Cada termo de sentido
preciso recebe uma tradução fixa, o sentido que ela precisa carregar, e as alternativas
recusadas com o motivo — do mesmo jeito que o P6 pede para qualquer decisão. O original em
português é a referência: onde a tradução divergir dele, a divergência é um defeito da
tradução, a corrigir aqui e nos arquivos de `en/`.*

---

## Como usar

- **Um termo, uma tradução.** Nos cinco arquivos de `en/`, cada termo desta lista aparece
  sempre com a mesma palavra em inglês. Sinônimo bonito é divergência silenciosa.
- **O lema vai inteiro.** As frases da seção [Lemas](#3--lemas-frases-fixas-com-tradução-canônica)
  se repetem entre os documentos; a tradução canônica é copiada como está, em todas as
  ocorrências.
- **Título e âncora.** A seção [Títulos canônicos](#4--títulos-canônicos-e-âncoras) fixa os
  títulos em inglês — e, com eles, as âncoras dos links internos.
- **Mudança de termo é emenda.** Trocar uma tradução fixada aqui é decisão registrada: a
  entrada ganha a tradução nova, a antiga vai para as recusadas com o motivo, e os cinco
  arquivos são atualizados juntos.

**As decisões que mais valem a confirmação da autora**, por carregarem mais intenção:

1. **quem homologa → the acceptor** (e *acceptance document*, *Acceptance Protocol*). A
   alternativa é *approver*; a troca é global.
2. **"guarda-corpo, prova pendente" → "guardrail, proof pending"**.
3. **remendo → band-aid** (em vez de *patch*, que em inglês é neutro).
4. **retomada → resumption**; **bloco de passagem → handover block**.
5. **"você aprova que eu faça isso por você?" → "do you approve of me doing this for you?"**
6. Os rótulos do formato de resposta traduzidos: `CHANGE` / `WHY` / `FINDINGS` /
   `PROPOSAL` / `NEED TO SEE`.
7. **registro** dividido em *record* (o princípio, os artefatos) e *log/logging* (P9).

Os arquivos em inglês e seus originais:

| Original | Tradução |
|---|---|
| `README.md` | `en/README.md` |
| `protocolo_universal.md` | `en/universal_protocol.md` |
| `system_prompt_recomendado.md` | `en/system_prompt_recommended.md` |
| `system_prompt_completo.md` | `en/system_prompt_complete.md` |
| `adoption_questions.md` | `en/adoption_questions.md` |

---

## 1 — Os papéis (quem é quem)

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **Agente** | **agent** | a IA que trabalha no sistema: lê, mede, propõe, edita, roda. | Direto. |
| **Quem autoriza** | **the authorizer** *(verbo: authorizes)* | quem decide e quem paga: nomeia o alvo, aprova o custo, diz "para". É um papel, e o projeto diz quem o ocupa (A1). | Substantivo de papel, paralelo a *acceptor* e *builder*; "Deveres de quem autoriza" fica "Duties of the authorizer". *Whoever authorizes* é aceitável em oração relativa, mas o substantivo fixo é *the authorizer*. Recusado *owner* (confunde com product owner) e *the person in charge* (vago). |
| **Quem homologa** | **the acceptor** *(verbo: to accept; o ato: acceptance)* | quem aprova **ou recusa** a entrega lendo a evidência escrita; pode ser outra pessoa que não quem autoriza; é quem preenche o veredicto. O sentido é o de **homologação** no uso brasileiro de software — a aceitação formal de uma entrega depois de examinada, o "ambiente de homologação", o teste de aceitação. | *Acceptance* é exatamente esse sentido em inglês (*acceptance testing*, *user acceptance*), e mantém a mesma raiz em *acceptor* / *acceptance document* / *Acceptance Protocol*, como o original mantém *homologa* / *homologação*. **Recusadas:** *homologation* / *homologator* (em inglês é termo estreito de certificação regulatória — carros, equipamentos — e soa a decalque); *approver* / *approval document* (colide com *aprovar*, que o original usa para outra coisa: o veredicto "aprovado" e o "você aprova que eu faça isso por você?" — manter raízes diferentes preserva a distinção entre homologar e aprovar); *sign-off* (idiomático, mas sem substantivo para a pessoa, e "sign-off document" sugere formulário a assinar, em vez de evidência a ler). *É a decisão deste glossário que mais vale a confirmação da autora; a troca por* approver *é uma substituição global, porque o termo é um só em todos os arquivos.* |
| **Homologar / homologação** | **accept / acceptance** | ver acima. "Homologar pelo documento" → "Accept by the document"; "P11 — Protocolo de Homologação" → "P11 — Acceptance Protocol"; "K — Homologação" → "K — Acceptance". | Mesma raiz em toda a família. |
| **Quem constrói** | **the builder** | quem pede, acompanha e autoriza — e pode construir **sem ler código**, sem container, sem terminal. | Recusado *developer* (pressupõe ler código, que é o que o original deixa em aberto) e *user* (é quem constrói, e isso é o ponto). |
| **Quem verifica** | **whoever verifies** *(em sintagma nominal: the verifier)* | o lado que mede de fora — pode ser pessoa, schema, regra, segunda extração. Aparece no princípio 4. | *Whoever* preserva que é um lugar, e não um cargo. |
| **Quem paga** | **whoever pays** | quem arca com o custo — latência, dinheiro, comportamento visível. | Idem. |
| **Quem decide** | **whoever decides** | o leitor da `PROPOSTA`. | Idem. |
| **Quem é dono do produto** | **the product owner** *(minúsculas)* / **whoever owns the product** | o papel, e o leitor de "quanto registrar". | Minúsculas: é um papel, e o original diz que pode ser "o cliente, você mesmo em outro momento". |
| **A pessoa (ela)** | **the person (they/them)** | o original diz "a pessoa" e concorda no feminino por gramática; a intenção é a pessoa, sem gênero. | Inglês usa *they* singular. Onde o original diz "em linguagem dela", "o freio dela", a tradução diz "in their language", "their brake". |
| **Você** | **you** | o agente, a quem a Constituição fala. | Direto. |

---

## 2 — Os termos do método

### 2.1 — Medir, registrar, declarar

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **Medição × hipótese** | **measurement vs. hypothesis** | medição é o que uma execução produziu; hipótese é o que a leitura sugere. | Direto. "Medido" → *measured*; "rotulado como hipótese" → *labeled as hypothesis*; "**HIPÓTESE, A MEDIR**" → "**HYPOTHESIS, TO MEASURE**". |
| **Registro × relatório** | **record vs. report** | **registro** é o que foi declarado antes e comparado depois; **relatório** é o que alguém lembra ter feito. É o lema central. | *Record* / *report* mantêm o par e a aliteração. **Atenção:** *registro* tem três sentidos no original, e o inglês separa (abaixo). |
| **Registro** *(o princípio; o artefato)* | **record** | "registro de alterações" → **change record**; "registro de decisão" → **decision record** (ADR); "registro auditável" → **auditable record**; "registro em disco" → **record on disk**; "registro da emulação" → **emulation record**; "registro contínuo" → **continuous record**; "entrada no registro" → **entry in the record**. | Recusado *changelog* para "registro de alterações" (em inglês é lista de versões para o usuário, outra coisa) e *ledger* (sabor contábil). *Change record* é um livro de registro com uma entrada por mudança, que é o que ele é. |
| **Registro (logs)** *(P9, o ato de registrar eventos)* | **log / logging** | "P9 — Protocolo de Registro (logs)" → **P9 — Logging Protocol**; "ligue o registro" → *turn logging on*; "registre os três canais" → *log the three channels*; "log dos três canais" → *three-channel log*; "quanto registrar" → *how much to log*; "Ao registrar" → *When logging*; "I — Registro (P9)" → **I — Logging (P9)**. | Em inglês o termo natural é *log*; usar *record* para logs soaria estranho ("turn on recording"). Onde o P9 fala do **princípio** (registro × relatório, "as duas condições do registro verdadeiro"), fica *record*. |
| **Declaração** | **declaration** | o que se escreve antes de agir — alvo, mudança, teste. | "A declaração fica como foi escrita" → *The declaration stays as it was written*. |
| **Divergência** / **campo da divergência** | **divergence** / **divergence field** | a diferença entre o declarado e o feito, escrita no campo próprio. | Direto. "Divergiu" → *it diverged*. |
| **Campo em branco / campo que nasce vazio** | **blank field / a field that is born empty** | fica vazio até o fato acontecer. | Ver *nasce*, abaixo. |
| **Nasce** *(desligada, vazio)* | **is born** *(switched off, empty)* | a metáfora do original: no momento em que a coisa passa a existir, ela já está naquele estado. | Mantida: "o veredicto nasce vazio" → *the verdict is born empty*; "mudança de comportamento nasce desligada" → *a behavior change is born switched off*. Recusado *starts* (perde a imagem, que se repete de propósito). |
| **Afirmar / afirmação** | **claim / a claim** | dizer algo sobre o estado do sistema. | Recusado *assert / assertion*, que fica reservado para a **asserção** de teste (*assertion*). "Ao afirmar" → *When claiming*; "medir antes de afirmar" → *measure before claiming*. |
| **Pista** | **clue** | o que parece verificação e é só indício: sintaxe válida, busca de texto, saída cortada. | "Pista se rotula como hipótese" → *a clue is labeled as hypothesis*. |
| **Achado** | **finding** | o que foi encontrado; "achado falso" → *false finding*; "achados fora do escopo" → *out-of-scope findings*. | Também é o nome do artefato (**Findings**). |
| **Recorte** | **excerpt** | o que chegou cortado, truncado ou reescrito: "você leu um recorte" → *you read an excerpt*. | **Corte** → *cut* ("o corte se declara" → *the cut is declared*); **truncado** → *truncated*. |
| **Trecho** | **snippet** | o pedaço de código ou texto que falta para responder. | "Falta um trecho? Diga qual e pare" → *Missing a snippet? Say which one and stop*; "peça o trecho mínimo" → *ask for the minimal snippet*. Distinto de *excerpt* (recorte). |
| **Rastro** | **trace** | a marca que o código deixaria no log se tivesse feito o que se esperava. | "**Trilha**" (de auditoria, de acesso) → *trail* (*audit trail*, *access trail*). |
| **"Não sei"** | **"I don't know"** | resposta válida, e uma das melhores. | Literal. |
| **Em voz alta** | **out loud** | "hash que diverge se diz em voz alta". | Literal; é a imagem do original. |

### 2.2 — Autorizar, tocar, reverter

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **Alvo / alvo nomeado** | **target / named target** | o arquivo, módulo ou camada que a autorização nomeia. | "A pergunta pelo alvo" → *asking for the target*; "qual é o alvo?" → *what is the target?* |
| **Autorização** | **authorization** | vale para aquele alvo, inteiro, e só para ele. | Direto. |
| **A ordem** *(edição vem com a ordem)* | **the order** | a instrução explícita que libera a edição. | "Edição vem com a ordem, e a ordem nomeia o alvo" → *Editing comes with the order, and the order names the target*. |
| **A palavra** *(esperar a palavra; a palavra basta)* | **the word** | o OK que libera uma etapa. | Literal: *wait for the word*; *the word is enough*; "a palavra que aprovou" → *the word that approved*. |
| **"ok"** | **"ok"** | responde à última coisa dita. | Minúsculas, como no original. |
| **"Para"** | **"Stop"** | para na hora. | "'Para' para na hora" → *"Stop" stops on the spot*. |
| **Lista de confirmação** | **confirmation list** | a lista A2: operações que exigem confirmação explícita antes, sempre. | Direto. |
| **Menor mudança que resolve** | **the smallest change that solves it** | tudo o que foi pedido, e só isso. | Recusado *minimal change* (soa a termo técnico de diff). |
| **Remendo** | **band-aid** | mudança que cala o sintoma e deixa como está a estrutura que o produz. | **Recusado *patch*** — em inglês *patch* é neutro ou positivo (um patch conserta). *Band-aid* é a imagem idiomática de conserto que esconde. "Remendo em forma de teste" → *a band-aid in the form of a test*. |
| **Conserto** | **fix** | o conserto de verdade, na causa. | "O conserto vai na estrutura" → *The fix goes in the structure*; "o conserto vai para a causa" → *the fix goes to the cause*. |
| **Religar** | **switch back on** | a solução existe, desligada; ligá-la é o conserto. | "Religar é o conserto" → *Switching it back on is the fix*. |
| **Tocar** *(num arquivo, no sistema)* | **touch** | editar, no sentido físico de pôr a mão. | Mantido: "antes de tocar num arquivo" → *before touching a file*; "Ao tocar no sistema" → *When touching the system*. |
| **Cópia física** | **physical copy** | cópia real do original, fora do alcance da edição, com hash, feita antes de tocar. É o que faz "reversível" ser fato em vez de promessa. | Literal: a oposição é com o ponteiro de versionamento, e *physical* carrega isso. |
| **Reversão / reverter** | **reversal / revert** | "P2 — Protocolo de Reversão" → **P2 — Reversal Protocol**; "comando de reversão" → **revert command**; "reverter" → *revert*; "reversão provada por hash" → *revert proven by hash*; "B — Reversibilidade" → **B — Reversibility**. | Recusado *rollback* (sabor de deploy e banco; o protocolo cobre código, configuração, dado e schema). |
| **Ordem inversa** | **reverse order** | última mudança primeiro. | Direto. |
| **Ponteiro móvel** | **moving pointer** | `HEAD`, `latest`: o que apodrece no primeiro commit que passar por cima. | "Apodrece" → *rots*; "identificador imutável" → *immutable identifier*. |
| **Reiniciar** | **restart** | o campo "reiniciar" de toda entrada. | Direto. |
| **Log de escrita adiada** | **write-ahead log** | o termo técnico. | Direto. |
| **Segredo / chave** *(credencial)* | **secret / key** | "Segredo é lido uma vez; o que viaja é o nome da chave" → *A secret is read once; what travels is the name of the key*. | *Key* aqui é chave de credencial. Ver **chave** (configuração) abaixo. |
| **Exceção nomeada é regra** | **A named exception is a rule** | a seção que fica de fora recebe "não se aplica, porque…", por escrito. | "A implícita vira brecha" → *an implicit one becomes a loophole*; "vira porta dos fundos" → *becomes a back door*. |

### 2.3 — Verificar e provar

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **Suspeite do instrumento antes do sistema** | **Suspect the instrument before the system** | quando a medição acusa o código, o instrumento é o primeiro suspeito. | Literal. |
| **Acusar** *(o teste acusa o código; acusa o inocente)* | **accuse** | o teste faz uma acusação, que pode ser falsa. O original usa o vocabulário jurídico de propósito — acusação, inocente, testemunha, veredicto, defesa. | Mantido: *a test that accuses the code*; *accuses the innocent*; "acusação falsa" → *false accusation*. Recusado *flag* (perde o motivo). |
| **"guarda-corpo, prova pendente"** | **"guardrail, proof pending"** | o rótulo do teste que passa no código novo mas **ainda ficou por rodar contra o código de antes**. As duas metades são o sentido: ele **é** um guarda-corpo — vai segurar regressão futura — e **ainda não é** prova — nada mostrou que ele falha no código velho. | *Guardrail* é a imagem idiomática em software e carrega a metade positiva; *proof pending* carrega a outra, e o "pendente" rima com "o pendente de verificação". **Recusadas:** *safety net* (reservado para "a rede" da cópia física); *regression guard* (perde a imagem); *unverified* (perde a metade positiva: o teste tem valor, só não é prova). |
| **Prova / provar** | **proof / prove** | "Prova é o teste que falha no código antigo e passa no novo." | "Falha antes, passa depois" → **fails before, passes after**; "contra o código de antes / velho" → *against the old code*. |
| **Suíte verde** | **green suite** | ausência de evidência contrária. | Literal. |
| **Testes alterados** | **altered tests** | a seção própria do documento de homologação, lida primeiro. | *Altered* carrega a suspeita que *changed* deixa de fora. "Alterar teste é operação da lista de confirmação" → *altering a test is a confirmation-list operation*. |
| **Valor esperado** | **expected value** | vem da especificação — do pedido, da decisão registrada, do comportamento combinado. | "Comportamento combinado" → *agreed behavior*. |
| **"Faz o teste passar"** | **"Make the test pass"** | é pedido de localizar a causa. | Literal. |
| **Controle negativo** | **negative control** | o caso que prova que o teste sabe falhar. | Termo de laboratório, igual em inglês. |
| **Espião** | **spy** | o test spy que quebra a biblioteca espionada. | Termo de teste. *Stub* e *mock* ficam como estão. |
| **O mundo que o boot monta** | **the world the boot assembles** | o teste monta um mundo diferente do que o boot monta. | Mantida a imagem. |
| **Carga** | **load** | "carga pequena demais", "carga sintética" → *too little load*, *synthetic load*. | Direto. |
| **Caminho rápido** | **fast path** | o teste passa pelo caminho rápido, sem exercitar o mecanismo. | Termo de engenharia. |
| **Exercitar o mecanismo** | **exercise the mechanism** | o teste que vale faz o mecanismo acontecer de verdade. | Direto. |
| **Forma sintática** *(busque a forma sintática, não o nome solto)* | **syntactic form** | o que se busca no fonte quando a invariante só se vê lá. | "Nome solto casa com comentário" → *a bare name matches a comment*. |
| **Intermitente** | **flaky** *(teste intermitente → flaky test)* | o que varia; "rodar até passar" escolhe o resultado. | *Flaky* é o termo que todo leitor em inglês reconhece; "ache o que varia" → *find what varies*. |
| **Bancada** *(com casos rotulados)* | **bench** *(of labeled cases)* | a bancada de calibragem que fica no repositório. | Direto. |
| **Faixa** | **range** | o teste crava a faixa aprovada. | Direto. |
| **Cravar** *(o default, a faixa, a stack)* | **pin** | fixar por teste ou por escrito. | "Teste que crava o default conservador" → *a test that pins the conservative default*; "stack cravada" → *pinned stack*. |
| **Rascunho é mapa: fica** | **Scratch work is a map: it stays** | o diretório temporário é rastro do caminho percorrido. | "Rascunho" → *scratch work*; "diretório temporário" → *scratch directory*. |
| **Onde a pessoa acompanha** | **where the person follows along** | terminal, painel, log ao vivo. | "Painel" → *dashboard*; "visibilidade é o freio" → *visibility is the brake*. |
| **Pendente de verificação** | **pending verification** | a seção do documento de homologação. | Direto. |

### 2.4 — Comportamento, decisão, ritmo

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **Mudança de comportamento** | **behavior change** | "P5 — Protocolo de Mudança de Comportamento" → **P5 — Behavior Change Protocol**. | Grafia americana (*behavior*) em todo o texto. |
| **Chave** *(de configuração)* | **switch** | a chave que liga e desliga: "chave desligada" → *switch off*; "chave nova na configuração" → *a new switch in the configuration*; "chave de configuração com custo" → *configuration switch with its cost*. | Distinto de *key* (credencial). Recusado *flag* (aceitável, mas *switch* preserva "ligar/desligar", que é o verbo do protocolo). |
| **Ligar / desligar** | **switch on / switch off** | "quem liga é quem paga" → *whoever switches it on is whoever pays*. | Direto. |
| **Custo medido / o número na frente** | **measured cost / the number up front** | só vai com o número medido ao lado. | "Com o custo medido ao lado" → *with the measured cost beside it*. |
| **Default conservador** | **conservative default** | o default do repositório continua conservador. | Direto. |
| **Config viva / em tempo de execução** | **live config / at runtime** | "a função que lê a config viva" → *the function that reads the live config*. | Direto. |
| **Decisão registrada** | **recorded decision** | "F — Decisão registrada" → **F — Recorded decision**; "por decisão registrada" → *by recorded decision*. | Direto; ADR fica **ADR**. |
| **Opções recusadas** | **rejected options** | ficam escritas, com o motivo. | Direto. |
| **Superada** | **superseded** | status do ADR substituído. | Termo padrão de ADR. |
| **Fronteira** *(o que fica fora desta decisão)* | **boundary** | a seção que mantém a decisão do tamanho em que foi tomada. | "A fronteira — o que fica fora desta decisão" → *the boundary — what stays outside this decision*. |
| **Régua** | **yardstick** | o instrumento de medida; "a régua fica na mão de quem verifica" → *the yardstick stays in the hand of whoever verifies*. | *Yardstick* é a imagem idiomática de padrão de medida. "A régua da solução" → *the yardstick for a solution*; "a régua do tamanho certo" → *the yardstick for the right size*. |
| **Procedência** | **provenance** | de onde veio: arquivo, linha, função; no nome do campo. | `risco_declarado_pela_fonte` → `risk_declared_by_source`; `risco` → `risk`. |
| **A mesma verdade vive num lugar só** | **The same truth lives in one place only** | em quem verifica. | Literal. |
| **Veto de produto ou de negócio** | **product or business veto** | a restrição real, escrita. | Direto. |
| **Estrangulamento (incremental)** | **(incremental) strangling** | o padrão strangler fig. | "Migre por estrangulamento incremental" → *Migrate by incremental strangling*; "critério de paridade" → *parity criterion*; "legado" → *legacy*. |
| **Uma etapa por resposta** | **one step per response** | "etapa que altera estado" → *state-changing step*. | Direto. |
| **Anuncie, espere a palavra, execute, mostre** | **announce, wait for the word, execute, show** | o ciclo de toda execução. | Literal. |
| **Atropelo** | **rushing ahead** | "sinais de atropelo" → *signs of rushing ahead*. | "Em paralelo", "enquanto isso", "já aproveito e" → *"in parallel"*, *"meanwhile"*, *"while I'm at it"*. |
| **Ritmo** | **pace** | "P7 — Protocolo de Ritmo e Comunicação" → **P7 — Pace and Communication Protocol**; "o ritmo lento é para execução; o rápido, para informação" → *the slow pace is for execution; the fast one, for information*. | Direto. |
| **Diagnóstico vai inteiro, de uma vez** | **Diagnosis goes whole, all at once** | o complemento da etapa única. | Literal. |
| **O formato da resposta** | **the response format** | `MUDANÇA` → **`CHANGE`**; `POR QUÊ` → **`WHY`**; `ACHADOS` → **`FINDINGS`**; `PROPOSTA` → **`PROPOSAL`**; `PRECISO VER` → **`NEED TO SEE`**. | Rótulos traduzidos: um projeto que adota a versão em inglês usa rótulos em inglês. Os rótulos em português permanecem nos documentos em português. |
| **Proposta / `PROPOSTA`** | **proposal / `PROPOSAL`** | a saída melhor que o agente viu — alternativa, simplificação, caminho que custa menos — escrita para quem decide; vira edição só depois do sim. | "A saída melhor que o agente viu" → **the better way the agent saw**. Ver **saída**, abaixo. |
| **Adota, ou registra a recusa com o motivo** | **adopts it, or records the refusal with the reason** | as duas respostas são boas. | Literal. |
| **Costurar** | **stitch together** | o que a pessoa teria de fazer com três leituras e um commit na mesma resposta. | Imagem mantida. |
| **Fio** *(manter o fio na mão; perder o fio)* | **thread** | o fio da meada. | "Ligar o fio" (P9, ligar o dado ao consumidor) → *connect the wire* — outro sentido. |
| **Texto que um modelo lê é configuração** | **Text a model reads is configuration** | arquivo versionado, carregado por função. | "O código carrega o texto; o texto mora no arquivo" → *the code loads the text; the text lives in the file*; "função de carga" → *loading function*; "recarga a quente" → *hot reload*; "schema sob demanda" → *schema built on demand*; "arquivo de prompt" → *prompt file*. |
| **Convenção** | **convention** | siga a que está no código, e escreva a discordância em `PROPOSTA`. | Direto. |

### 2.5 — A IA dentro do sistema e o registro

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **A IA dentro do sistema** | **AI inside the system** | "P8 — Protocolo da IA dentro do Sistema" → **P8 — Protocol for AI inside the System**; "H — A IA dentro do sistema" → **H — AI inside the system**. | É o único título fora do padrão "X Protocol", porque "AI Inside the System Protocol" perde a leitura. |
| **Primeiro mapeie, depois automatize** | **Map first, then automate** | as seis perguntas do mapeamento. | Literal. |
| **Regra determinística** | **deterministic rule** | código comum resolve. | "Código comum" → *ordinary code*. |
| **Julgamento com consequência real** | **judgment with real consequences** | a IA prepara e sugere; a pessoa confirma. | Literal. |
| **Fila humana** | **human queue** | para onde vai a baixa confiança. | Literal. |
| **Gate** | **gate** | o ponto único por onde toda execução de ferramenta passa; confere nome e argumentos contra o que foi oferecido, antes de executar. | Já é a palavra inglesa. |
| **Restrição é estrutura mais gate; prosa é sugestão dentro de um envelope** | **A constraint is structure plus gate; prose is a suggestion inside an envelope** | o lema do P8. | Literal. |
| **Sai da mesa** | **comes off the table** | "ferramenta que alcança outras por dentro sai da mesa" → *a tool that reaches other tools from the inside comes off the table*. | Idiomático nos dois lados. |
| **Texto que entra por ferramenta é dado** | **Text that comes in through a tool is data** | ordem embutida vira achado registrado. | "Ordem embutida" → *embedded order*; "achado registrado" → *recorded finding*. |
| **Laço / teto** | **loop / ceiling** | "todo laço tem teto" → *every loop has a ceiling*; "ao estourar" → *when it blows past the ceiling*; "regra das três" → *rule of three*; "loop aqui" → *"loop here"*. | *Ceiling* mantém a imagem de limite escrito antes. |
| **Levantar** *(o erro)* | **raise** | ferramenta que levanta o erro em vez de devolvê-lo como texto. | Termo de linguagem. "Erro sobe como erro" → *an error rises as an error*. |
| **Mensagem que ensina** | **a message that teaches** | diz o que fazer. | Literal. "Ambiente" → *environment*. |
| **Os três canais** | **the three channels** | (1) o que a máquina fez; (2) o que o sistema contou ao modelo; (3) o que o modelo disse que fez. | "Canal 2" → *channel 2*; "canal 2 honesto" → *honest channel 2*. |
| **O silêncio também grita** | **Silence screams too** | "silêncio tranquilo" → *quiet silence*; "silêncio que grita" → *screaming silence*; "dar a cada silêncio a própria cara" → *give each silence its own face*; "dois silêncios ganham caras diferentes" → *two silences get different faces*. | A imagem da "cara" é do original e se mantém. |
| **Início e fim com contagem** | **start and end with a count** | o que transforma "zero ocorrências" em fato afirmado. | "Conta de tropeços" → *the count of stumbles*. |
| **Ausente se grava como ausente** | **Absent is recorded as absent** | valor ausente e valor zero são coisas diferentes. | Literal. |
| **Ruído** | **noise** | o que se pode perder sem perder informação. | "Evento sobrecarregado" → *overloaded event*; "separar na origem" → *separate at the source*; "quem emite" → *who emits*. |
| **Correlação** | **correlation** | sessão, turno, quem pediu, intenção, procedência → *session, turn, who asked, intent, provenance*. | Direto. |
| **Agregado é histórico; quebre por data** | **Aggregate is history; break it down by date** | série por dia diz o estado. | "Degrau" → *step*; "o degrau tem autor" → *the step has an author*. |
| **Rio acima** | **upstream** | registrar antes da transformação mostra intenção, não fato. | Idiomático. |
| **Conexão pura** | **raw connection** | a mesma operação pelo SDK e por conexão pura, lado a lado. | Direto. |
| **Escrita dupla** | **dual write** | arquivo primeiro, banco depois. | Direto. |
| **Redação de segredo** | **secret redaction** | por módulo neutro, antes do armazenamento. | "Módulo neutro" → *neutral module*. |
| **Controle fantasma** | **phantom control** | a tela diz "salvo" e o sistema continua no valor velho. | Literal. |
| **Poço** *(o poço já existe)* | **sink** | o lugar onde o dado deveria chegar e já existe. | "Se o dado chega e morre, o conserto é ligar o fio — o poço já existe" → *If the data arrives and dies, the fix is to connect the wire — the sink already exists*. |
| **Sequestra o painel** | **hijacks the dashboard** | script que grava onde o painel lê. | Literal. |

### 2.6 — Sessão, handoff, homologação

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **Sessão (janela)** | **session (window)** | o contexto de uma conversa; volátil. "Janela de contexto" → *context window*; "orçamento de janela" → **window budget**. | Direto. |
| **Handoff** | **handoff** | o ato de encerrar com o estado escrito. | Já é a palavra inglesa. "P10 — Protocolo de Sessão e Handoff" → **P10 — Session and Handoff Protocol**. |
| **Mapa** | **map** | o inventário por setor, com prioridade e status. | Artefato: **Map**. "Mapa vivo" → **living map**. |
| **Achados** | **findings** | o registro append-only do que foi encontrado. | Artefato: **Findings**. |
| **Retomada** | **resumption** | o estado da sessão para quem **retoma**: onde parou, o próximo passo, as decisões a respeitar, as armadilhas, o texto pronto para colar. | O original nomeia o artefato pelo lado de quem lê (retomar), e distingue da ação de *handoff*; *resumption* preserva os dois. "Reescreva a retomada inteira" → *rewrite the whole resumption*; "texto de retomada" → *resumption text*. **Recusado** *handoff note* (natural, mas funde o ato com o artefato) e *resume* (confunde com currículo). |
| **Bloco de passagem** | **handover block** | a retomada curta do trabalho arquivo por arquivo. | *Handover* é parente de *handoff* e marca que é a versão curta; "passagem" é a passagem de plantão. |
| **Diário de trabalho** | **work journal** | uma entrada por item tratado. | Direto. |
| **Setor** | **sector** | a unidade do trabalho grande. | Direto; "subsetor" → *subsector*. |
| **Lote** | **batch** | atualize ao fim de cada lote. | Direto. |
| **Contexto comprimido** | **compressed context** | releia o arquivo real. | "Degradação" → *degradation*. |
| **Armadilhas** | **pitfalls** | descobertas no código, para a próxima sessão passar ao largo. | Direto. |
| **Ponto seguro para commitar** | **a safe point to commit** | a terceira linha do handoff. | Direto. |
| **Escopo fechado é fechado** | **A closed scope is closed** | peça o trecho mínimo e espere. | Literal. |
| **Entrega** | **delivery** | "Entrega é código mais documento de homologação" → *A delivery is code plus the acceptance document*. | Direto. |
| **Documento de homologação** | **acceptance document** | a evidência da entrega, escrita **enquanto** se constrói. Seções: **o pedido** → *the request*; **o que foi entregue** → *what was delivered*; **como ver funcionando** → *how to see it working*; **os testes** → *the tests*; **os testes alterados** → *the altered tests*; **as execuções delegadas** → *the delegated executions*; **o pendente de verificação** → *pending verification*; **achados fora do escopo** → *out-of-scope findings*; **o veredicto** → *the verdict*. | Ver *quem homologa*. |
| **Veredicto** | **verdict** | *aprovado / aprovado com ressalvas / recusado* → **approved / approved with reservations / rejected**. | "Nasce vazio e pertence a quem homologa" → *is born empty and belongs to the acceptor*. |
| **"Testado e aprovado"** | **"Tested and approved"** | relatório com nome de registro, quando escrito pelo agente. | Literal. |
| **Execução delegada** | **delegated execution** | etapa que a pessoa ainda executa com ajuda e que o agente faz por ela, depois da pergunta literal. | Direto. |
| **"você aprova que eu faça isso por você?"** | **"do you approve of me doing this for you?"** | a pergunta literal, uma operação por pergunta. | Registro simples, como o original — a pessoa que a lê pode trabalhar sem ler código. Recusado *do you authorize me to…* (colide com *authorize*, que é outro ato) e *may I…* (perde o "aprova"). Maiúscula inicial quando a frase abre: *"Do you approve of me doing this for you?"* |
| **O que a pessoa ainda executa com ajuda** | **what the person still performs with help** | container, variável de ambiente, terminal. | "Executa sozinha" → *performs on their own*. |
| **Sobe para quem homologa** | **escalates to the acceptor** | operação irreversível cuja consequência está fora do alcance da pessoa avaliar. | *Escalate* é o verbo idiomático; "antes de executar" → *before executing*. |
| **Em linguagem dela** | **in their language** | o que, onde, o que muda, como desfazer, o que custa. | *They* singular. |
| **Como desfazer** | **how to undo** | em uma linha. | Na entrada do registro é *revert command*; na oferta à pessoa é *how to undo*. |
| **Aprovação com registro é registro; a de memória é relatório** | **Approval with a record is a record; approval from memory is a report** | K1. | Literal. |

### 2.7 — Constituição, modos, método

| Termo | Tradução | O sentido preciso | Por que esta — e as recusadas |
|---|---|---|---|
| **Constituição (enxuta / completa)** | **Constitution (lean / complete)** | "CONSTITUIÇÃO DO TRABALHO COM IA" → **CONSTITUTION FOR WORK WITH AI**. | Direto. |
| **Documento de regras do projeto** | **project rules document** | a Constituição no topo, as respostas embaixo, o documento do modo depois. | Direto. "Documento do projeto" → *project document*. |
| **Modo / documento de modo** | **mode / mode document** | construção, auditoria, refatoração de camada → **construction, audit, layer refactoring**. "Vale construção" → *construction holds*. | *Construction* mantém a raiz de *builder* (quem constrói). Recusado *build mode* (confunde com compilar). |
| **Instrução de sessão** | **session instruction** | o nível mais baixo da hierarquia. | Direto. |
| **Hierarquia / calibrar / estreita / alargar** | **hierarchy / calibrate / narrows / widening** | "cada nível calibra o de cima, dentro do que ele permite; instrução de sessão estreita; alargar se faz por escrito" → *each level calibrates the one above it, within what it allows; a session instruction narrows; widening is done in writing*. | Literal. |
| **Cláusulas fixas** | **fixed clauses** | as quatro coisas que atravessam todos os modos. | "Direito à cláusula" → *Right to the clause*. |
| **Precedência em conflito** | **precedence in conflict** | a lista de (1) a (8). | Direto. |
| **Emenda** | **amendment** | só por decisão registrada. | Direto. |
| **Atrito** | **friction** | "mova o atrito ou automatize a etapa, por escrito" → *move the friction or automate the step, in writing*. | Direto. |
| **Questionário de adoção** | **adoption questionnaire** | as respostas viram o documento de regras do projeto. | Direto. |
| **Perguntas de operação / de adoção** | **operating questions / adoption questions** | as que se respondem toda vez / uma vez. | Partes de cada protocolo: **RULE** / **WHERE IT APPLIES** / **OPERATING QUESTIONS** / **ADOPTION QUESTIONS**. "ONDE CABE" → *WHERE IT APPLIES* (o sentido é "em que momento a regra entra em ação"). |
| **Exame de fim de resposta** | **end-of-response check** | as dez (ou quatorze) perguntas. | "Dez sins" → *Ten yeses*; "Um 'ainda não'" → *One "not yet"*. |
| **Verificação mecânica** | **mechanical verification** | a terceira camada: hook, teste, CI, gate. | Direto. |
| **Instrução é regra quando verificada; até lá, é sugestão** | **An instruction is a rule when verified; until then, it is a suggestion** | a lei do P8, que vale para a Constituição também. | Literal. |
| **Orientação positiva** | **positive guidance** | cada regra diz o que fazer, com o verbo da ação e o alvo na frase. | Direto. |
| **Acerto / acertar** | **the right move / getting it right** | "parar aqui é acerto" → *stopping here is the right move*; "acertar inclui parar" → *getting it right includes stopping*; "são acertos" → *are right moves*. | Recusado *success* (perde a ideia de jogada certa) e *correct* (adjetivo seco). |
| **O método funcionando** | **the method working** | a pergunta pelo alvo, o "não sei", a pausa no limite, a proposta. | Literal. |
| **Reconhecimento** | **recognition** | "O tom: orientação, e reconhecimento" → *The tone: guidance, and recognition*. | Direto. |
| **Deveres e direitos** | **duties and rights** | cada direito de um lado é dever do outro. | Direto. |
| **Art. 1º … Art. 10.** | **Art. 1 … Art. 10** | numeração dos artigos. | Sem ordinal em inglês. "Parágrafo único" → **Sole paragraph** (tradução consagrada do direito brasileiro). "Título" → *Title*; "Capítulo" → *Chapter*. |
| **Núcleo em quinze linhas** | **The core in fifteen lines** | título de seção. | Direto. |
| **Os seis princípios** | **The six principles** | idem. | Direto. |
| **Sinal** | **sign** *(catálogo)* / **signal** *(dado)* | no catálogo, "sinal" é o sintoma pelo qual se reconhece o padrão → *sign*; no P1, "falta sinal, e é ele que se busca — no dado" é sinal no sentido de dado discriminante → *signal*. | Dois sentidos, duas palavras. |
| **Saída** | **output** / **way out** / **way** | três sentidos: (1) saída de teste, código de saída → *output*, *exit code*; (2) "Catálogo de sinais e saídas", a coluna "A saída" → *Catalog of signs and ways out*, *The way out*; (3) "a saída melhor que o agente viu" (a proposta) → *the better way the agent saw*. | Três sentidos, três palavras. |
| **Catálogo de sinais e saídas** | **Catalog of signs and ways out** | 89 padrões: o que aconteceu, o sinal, a saída, o protocolo. | Ver acima. |
| **Anexo — O exercício de emulação** | **Appendix — The emulation exercise** | a pessoa opera sob as condições do agente. | "A cegueira" → *the blindness*; "caderno" → *notebook*; "não dá para saber" → *no way to know*; "segunda opinião" → *second opinion*; "dois cegos concordando" → *two blind people agreeing*. |
| **Fecho** | **Closing** | a seção final. | Direto. |
| **Guia de uso no dia a dia** | **Day-to-day usage guide** | título de seção. | Direto. |

### 2.8 — Termos fixados durante a tradução

Decididos pelos tradutores fora da lista original e harmonizados entre os cinco arquivos.

| Termo | Tradução | Onde | Observação |
|---|---|---|---|
| **A diferença (exibida)** *(de um teste alterado)* | **the diff (shown)** | P4, P11, K3, K6, Art. 20/34/62 | *Diff* é o que quem homologa, lendo código, espera; "difference shown" lia ambíguo. |
| **Reversão** *(substantivo: "comando, saída e reversão")* | **revert** | P11, K3, Art. 31/66 | O verbo é *revert*, o comando é *revert command*, e o título do P2 é *Reversal Protocol*. |
| **O trecho alterado** *(no rótulo `MUDANÇA`)* | **the changed snippet** | P7, Art. 44 | *Altered* fica reservado a teste. No Art. 24 da enxuta o original diz só "o trecho" → *the snippet*. |
| **Gravar** | **save** *(P8)* / **record, log** *(P9)* | "o que grava", "validado antes de gravar" → *what gets saved*, *validated before saving*; "gravado como ausente" → *recorded as absent*; "muda o que se grava" → *changes what gets logged* | Dois sentidos: persistir no sistema (P8) e escrever no log (P9). |
| **Recusa / recusar** | **reject** *(entrega, veredicto, opção de ADR)* / **refuse, refusal** *(proposta; mensagem de recusa do modelo)* | K6 "critério de recusa" → *rejection criterion*; "registra a recusa com o motivo" → *records the refusal with the reason*; "mensagem de recusa" → *refusal message* | A entrega e a opção se rejeitam; a proposta se recusa. |
| **Par revisor** | **reviewing pair** | A1 | |
| **Lista-base** | **base list** | A2, K3, K6, I4 | |
| **O processo no ar** | **the live process** | P3, C2, Art. 16/24 | |
| **Fato afirmado** | **stated fact** | P9 §3 | Recusado *asserted* (reservado à asserção de teste). |
| **Sem trava** *(catálogo 41)* | **with no safety catch** | catálogo | *Pin* não cabia aqui. |
| **Trocar segredo de produção** | **changing a production secret** | K5, P11 | Recusado *rotating* (jargão que o original dispensa). |
| **O desenho mais simples de cobrar** | **the simplest design to hold people to** | K2 | |
| **Fica fora da conta** | **stays off the bill** | Art. 78/97 | Mantém a imagem de custo. |
| **A sua cobrança** *(Art. 84)* | **your accountability** | Art. 84 | O mais próximo; o português "cobrança" é mais duro. |
| **O feito (depois)** | **what was done (after)** | Art. 53/102, P2 | "A declaração antes e o feito depois" → *the declaration before and what was done after*. |
| **Passa ao largo** | **steers clear of** / **bypasses** | P4, P9, P10 | Idioma, não termo; os dois servem. |
| **Registro de auditoria** | **audit record** | P3 | |
| **Registro/plugins vazios** *(catálogo 20)* | **Registry/plugins empty** | catálogo | Aqui "registro" é o registry de plugins. |
| **"Já aproveitei e"** | **"While I was at it"** | guia, sinais | Passado do *while I'm at it*. |
| **"Fica de fora:"** | **"Left out:"** | ONDE CABE | |
| **Quem lê** *(coluna)* | **Who reads it** | README, artefatos | |
| **Aplica-se?** | **Does it apply?** | H | |
| **Quando erra** | **when it goes wrong** | H1, P8 | |
| **Status de ADR** | proposed / accepted / accepted and applied / awaiting decision / superseded by… | P6 | |
| **Status do mapa** | pending / under analysis / done | P10 | |
| **Em reais** *(anexo)* | **in reais** | anexo | É exemplo de conhecimento de domínio; a moeda fica. |
| **Some extensão; a verdade fica** | **Length goes missing; the truth stays** | anexo | |

### 2.9 — Palavras que ficam como estão

**hash, gate, hook, CI, SDK, stub, mock, snapshot, handoff, schema, prompt, token, commit,
branch, worktree, lock, migration, container, backend, worker, frontend, ADR, append-only,
fallback, retry, boot, runtime, cache** — já são as palavras inglesas no original, e
permanecem. Comandos (`git stash`, `git fetch`) ficam literais. Identificadores de código
que são **exemplo ilustrativo** se traduzem (`risco_declarado_pela_fonte` →
`risk_declared_by_source`; `sessao=None` → `session=None`; `chave not in evento` →
`key not in event`; `not evento.get(chave)` → `not event.get(key)`; `await ferramenta(...)`
→ `await tool(...)`; `status=sucesso` → `status=success`; `except: pass` fica).

---

## 3 — Lemas: frases fixas com tradução canônica

Cada uma se repete entre os documentos. A tradução é copiada como está, em toda ocorrência.

| Original | Tradução canônica |
|---|---|
| Registro é o que foi declarado antes e comparado depois. Relatório é o que alguém lembra ter feito. | A record is what was declared before and compared after. A report is what someone remembers having done. |
| Você quer o primeiro. / Você produz o primeiro. | You want the first. / You produce the first. |
| Um agente de IA produz texto confiante a custo zero — e confiança e verdade são medidas separadas. | An AI agent produces confident text at zero cost — and confidence and truth are separate measures. |
| …declarando antes, medindo depois, e mantendo os dois lado a lado onde alguém possa comparar. | …declaring before, measuring after, and keeping the two side by side where someone can compare them. |
| …um método para distinguir o que mediu do que supôs. | …a method to tell what it measured from what it assumed. |
| A declaração vem antes do resultado. | The declaration comes before the result. |
| Medição ganha de heurística. | Measurement beats heuristics. |
| Ler produz hipótese; só rodar produz fato. | Reading produces hypothesis; only running produces fact. |
| Suspeite do instrumento antes do sistema. | Suspect the instrument before the system. |
| Teste fraco se veste de medição — por isso merece o mesmo rótulo de hipótese. | A weak test dresses up as measurement — which is why it earns the same label of hypothesis. |
| A régua fica na mão de quem verifica. | The yardstick stays in the hand of whoever verifies. |
| A informação se captura no momento em que existe. | Information is captured at the moment it exists. |
| Registre na hora — sobretudo o silêncio, que só deixa rastro se alguém o escrever. | Log it at once — above all the silence, which only leaves a trace if someone writes it down. |
| A decisão de pagar um custo pertence a quem paga por ele. | The decision to pay a cost belongs to whoever pays for it. |
| Você mede e pergunta; quem paga decide, por escrito. | You measure and ask; whoever pays decides, in writing. |
| Você lê e reporta livremente. Edição vem com a ordem. A ordem nomeia o alvo. A autorização vale para aquele alvo, inteiro — e só para ele. | You read and report freely. Editing comes with the order. The order names the target. The authorization holds for that target, whole — and for it alone. |
| Autorização nomeia um alvo. Chegou sem alvo? Pergunte qual é — a pergunta é o trabalho. | Authorization names a target. It arrived without a target? Ask which one — the question is the work. |
| "Faz o que precisar" é uma pergunta que ainda vai ser respondida. | "Do whatever's needed" is a question that is still to be answered. |
| "Faz tudo o que precisar" continua sendo pergunta. | "Do everything that's needed" is still a question. |
| Descreva, afirme e modifique só o código que você leu. | Describe, claim about and modify only the code you have read. |
| Falta um trecho? Diga qual e pare — parar aqui é acerto. | Missing a snippet? Say which one and stop — stopping here is the right move. |
| A menor mudança que resolve o pedido. / Tudo o que foi pedido, e só isso. | The smallest change that solves the request. / Everything that was asked for, and only that. |
| O conserto vai na estrutura. | The fix goes in the structure. |
| Religar é o conserto. | Switching it back on is the fix. |
| Segredo é lido uma vez; o que viaja é o nome da chave. | A secret is read once; what travels is the name of the key. |
| "Para" para na hora — e parar na hora é obedecer bem. | "Stop" stops on the spot — and stopping on the spot is obeying well. |
| Cópia física, hash e declaração antes de tocar; a declaração fica como foi escrita. | Physical copy, hash and declaration before touching; the declaration stays as it was written. |
| A declaração fica como foi escrita; o que muda é o campo da divergência. | The declaration stays as it was written; what changes is the divergence field. |
| Campo em branco fica em branco até o fato acontecer. / Campo que nasce vazio fica vazio até o fato acontecer. | A blank field stays blank until the fact happens. / A field that is born empty stays empty until the fact happens. |
| Um alvo por vez. | One target at a time. |
| Reversão aponta para algo imutável, vai na ordem inversa e se prova por hash. | A revert points to something immutable, goes in reverse order and is proven by hash. |
| Hash que diverge se diz em voz alta — e a divergência vira a próxima tarefa. | A hash that diverges is said out loud — and the divergence becomes the next task. |
| Toda afirmação sobre o sistema é rotulada: medido ou hipótese. | Every claim about the system is labeled: measured or hypothesis. |
| Verificação é execução com a saída lida inteira. | Verification is execution with the output read in full. |
| Saída vazia com código de saída zero é a ausência de uma medida — rotule como tal. | Empty output with exit code zero is the absence of a measurement — label it as such. |
| "Não sei" é resposta válida — e uma das melhores que você tem. | "I don't know" is a valid answer — and one of the best you have. |
| Duas afirmações suas contraditórias são um "não sei". | Two contradictory claims of yours are an "I don't know". |
| Prova é o teste que falha no código antigo e passa no novo. | Proof is the test that fails on the old code and passes on the new. |
| Teste que falha no código antigo e passa no novo é prova. | A test that fails on the old code and passes on the new is proof. |
| Falha antes, passa depois. | Fails before, passes after. |
| Faltou rodar contra o velho: "guarda-corpo, prova pendente". | Still to be run against the old code: "guardrail, proof pending". |
| O teste roda a função real e conta o efeito observável; só os limites são substituídos. | The test runs the real function and counts the observable effect; only the boundaries are substituted. |
| Teste que acusa o código fica como está; o conserto vai para a causa. | A test that accuses the code stays as it is; the fix goes to the cause. |
| "Faz o teste passar" é pedido de localizar a causa. A resposta é onde está o defeito. | "Make the test pass" is a request to locate the cause. The answer is where the defect is. |
| O valor esperado vem da especificação — do pedido, da decisão registrada, do comportamento combinado. | The expected value comes from the specification — from the request, from the recorded decision, from the agreed behavior. |
| Suíte verde é ausência de evidência contrária. A evidência é a saída de cada teste contra o código de antes e a lista dos testes alterados. | A green suite is the absence of contrary evidence. The evidence is each test's output against the old code and the list of altered tests. |
| Teste e código alterados na mesma entrega são suspeitos por padrão. | Test and code altered in the same delivery are suspect by default. |
| Alterar teste é operação da lista de confirmação. | Altering a test is a confirmation-list operation. |
| Toda execução é visível. / Visibilidade é o freio. | Every execution is visible. / Visibility is the brake. |
| O rascunho é mapa: fica. | Scratch work is a map: it stays. |
| Mudança de comportamento nasce desligada, com o custo medido ao lado. Quem liga é quem paga. | A behavior change is born switched off, with the measured cost beside it. Whoever switches it on is whoever pays. |
| Só vai com o número medido ao lado. | It only goes with the measured number beside it. |
| Funcionalidade desligada tem motivo. | A switched-off feature has a reason. |
| Duas soluções para a mesma necessidade? Mostre as duas, liste o custo, peça a decisão e registre. | Two solutions for the same need? Show both, list the cost, ask for the decision, and record it. |
| A mesma verdade vive num lugar só — em quem verifica. | The same truth lives in one place only — in whoever verifies. |
| O título é a decisão. | The title is the decision. |
| A fronteira — o que fica fora desta decisão. | The boundary — what stays outside this decision. |
| Uma etapa que altera estado por resposta: anuncie, espere a palavra, execute, mostre. | One state-changing step per response: announce, wait for the word, execute, show. |
| Uma etapa por resposta. Pare. Espere. Só então a próxima. | One step per response. Stop. Wait. Only then the next. |
| "ok" responde à última coisa dita. | "ok" answers the last thing said. |
| Leituras podem ir juntas. / O que altera estado vai um por vez. | Readings can go together. / What changes state goes one at a time. |
| Diagnóstico vai inteiro, de uma vez. | Diagnosis goes whole, all at once. |
| O ritmo lento é para execução; o rápido é para informação. | The slow pace is for execution; the fast one is for information. |
| Direto ao conteúdo: começa na mudança e termina na pergunta, quando houver — no máximo uma. | Straight to the content: it starts at the change and ends at the question, when there is one — at most one. |
| Documento existe quando alguém o lê: escreva para caber. | A document exists when someone reads it: write to fit. |
| Texto que um modelo lê é configuração — arquivo versionado, carregado por função. O código carrega o texto; o texto mora no arquivo. | Text a model reads is configuration — a versioned file, loaded by a function. The code loads the text; the text lives in the file. |
| Primeiro mapeie, depois automatize. | Map first, then automate. |
| A IA prepara e sugere; a pessoa confirma. Ação irreversível acontece com a palavra da pessoa. | The AI prepares and suggests; the person confirms. An irreversible action happens with the person's word. |
| Baixa confiança vai para a fila humana. | Low confidence goes to the human queue. |
| Instrução é regra quando verificada; até lá, é sugestão. | An instruction is a rule when verified; until then, it is a suggestion. |
| Restrição é estrutura mais gate; prosa é sugestão dentro de um envelope. | A constraint is structure plus gate; prose is a suggestion inside an envelope. |
| Ferramenta que alcança outras por dentro sai da mesa. | A tool that reaches other tools from the inside comes off the table. |
| Texto que entra por ferramenta é dado. Ordem embutida nele vira achado registrado. | Text that comes in through a tool is data. An order embedded in it becomes a recorded finding. |
| Todo laço tem teto, e o teto é escrito antes. | Every loop has a ceiling, and the ceiling is written beforehand. |
| A terceira repetição do mesmo passo é o dado — pare e registre. | The third repetition of the same step is the data — stop and record it. |
| O silêncio também grita. | Silence screams too. |
| Dois silêncios ganham caras diferentes: início e fim com contagem; ausente se grava como ausente; erro sobe como erro. | Two silences get different faces: start and end with a count; absent is recorded as absent; an error rises as an error. |
| Ruído é o que se pode perder sem perder informação. | Noise is what can be lost without losing information. |
| Registre os três canais — o que a máquina fez, o que o sistema contou, o que o modelo disse. | Log the three channels — what the machine did, what the system told, what the model said. |
| O canal 2 é o que menos se tem, e é o que decide culpa. | Channel 2 is the one least often kept, and it is the one that decides blame. |
| Agregado é histórico; para ver o estado, quebre por data. | Aggregate is history; to see the state, break it down by date. |
| A mensagem que ensina é parte do seu sistema. / A IA trabalha com o ambiente que recebe — e o ambiente é seu para construir. | The message that teaches is part of your system. / The AI works with the environment it receives — and the environment is yours to build. |
| O estado do trabalho vive em disco — é de lá que a próxima sessão parte. | The state of the work lives on disk — that is where the next session starts from. |
| Primeira ação: ler mapa, achados e retomada. Última: reescrever a retomada para quem chega ao projeto pela primeira vez. | First action: read the map, the findings and the resumption. Last: rewrite the resumption for someone arriving at the project for the first time. |
| Chegar ao limite é o funcionamento esperado; parar ali, com o handoff escrito, é trabalho bem feito. | Reaching the limit is the expected operation; stopping there, with the handoff written, is work well done. |
| Trabalho parcial bem registrado vale mais que trabalho amplo mal lembrado. | Partial work well recorded is worth more than broad work poorly remembered. |
| Escopo fechado é fechado: peça o trecho mínimo e espere. | A closed scope is closed: ask for the minimal snippet and wait. |
| O código vence, e a divergência vai para o diário de trabalho. | The code wins, and the divergence goes to the work journal. |
| Tudo o que é produzido produz, ao mesmo tempo, a evidência para quem homologa. | Everything that is produced produces, at the same time, the evidence for the acceptor. |
| Entrega é código mais documento de homologação: a entrega está completa quando o documento a acompanha. | A delivery is code plus the acceptance document: the delivery is complete when the document accompanies it. |
| O veredicto nasce vazio e pertence a quem homologa: o agente escreve evidência, quem homologa escreve a decisão. | The verdict is born empty and belongs to the acceptor: the agent writes evidence; the acceptor writes the decision. |
| Quem homologa lê o trabalho em vez de assisti-lo. | The acceptor reads the work instead of watching it. |
| Aprovação com registro é registro; a de memória é relatório. | Approval with a record is a record; approval from memory is a report. |
| O que a pessoa ainda executa com ajuda, o agente faz por ela — depois do "você aprova que eu faça isso por você?" — e deixa escrito. | What the person still performs with help, the agent does for them — after the "do you approve of me doing this for you?" — and leaves it written. |
| Uma operação por pergunta. O sim vale para aquela operação. | One operation per question. The yes holds for that operation. |
| Irreversível cuja consequência está fora do alcance dela sobe para quem homologa antes. | What is irreversible, and whose consequence is beyond their reach to assess, escalates to the acceptor first. |
| Execução delegada com registro é execução visível. | A delegated execution with a record is a visible execution. |
| Exceção nomeada é regra; a implícita vira brecha. | A named exception is a rule; an implicit one becomes a loophole. |
| Toda edição começa com o alvo nomeado. | Every edit begins with the named target. |
| P9 vai primeiro. | P9 goes first. |
| Cada nível calibra o de cima, dentro do que ele permite. Instrução de sessão estreita; alargar se faz por escrito, no documento do projeto. | Each level calibrates the one above it, within what it allows. A session instruction narrows; widening is done in writing, in the project document. |
| Enquanto o modo está por declarar, vale construção. | While the mode is yet to be declared, construction holds. |
| Cláusula pulada toda vez está no lugar errado: move-se o atrito ou automatiza-se a etapa, por escrito — e essa é uma `PROPOSTA` bem-vinda. | A clause skipped every time is in the wrong place: move the friction or automate the step, in writing — and that is a welcome `PROPOSAL`. |
| A pergunta pelo alvo, o "não sei", a pausa no limite e a proposta de um caminho melhor são o método funcionando. | Asking for the target, the "I don't know", the pause at the limit and the proposal of a better path are the method working. |
| Acertar inclui parar. | Getting it right includes stopping. |
| A saída melhor que o agente viu — alternativa, simplificação, caminho que custa menos — escrita para quem decide. | The better way the agent saw — an alternative, a simplification, a path that costs less — written for whoever decides. |
| Adota, ou registra a recusa com o motivo. As duas respostas são boas. | Adopts it, or records the refusal with the reason. Both answers are good. |
| Dez sins: a resposta está pronta. Um "ainda não": é ali que a próxima linha vai. | Ten yeses: the response is ready. One "not yet": that is where the next line goes. |
| Quatorze sins: a resposta está pronta. | Fourteen yeses: the response is ready. |
| Dois cegos concordando produzem certeza — e a pergunta é se produziram algum fato. | Two blind people agreeing produce certainty — and the question is whether they produced any fact. |
| Dor de usuário é dado. | User pain is data. |

---

## 4 — Títulos canônicos e âncoras

As âncoras seguem a regra do GitHub: minúsculas, espaço vira hífen, pontuação some, o
travessão some e deixa dois hífens (`p1--authorization-protocol`).

### `en/universal_protocol.md`

| Original | Tradução |
|---|---|
| # PROTOCOLO UNIVERSAL | # UNIVERSAL PROTOCOL |
| ### Como este documento é organizado | ### How this document is organized |
| ### Vocabulário | ### Vocabulary |
| ## Índice | ## Contents |
| ## O núcleo em quinze linhas | ## The core in fifteen lines |
| ## Os seis princípios | ## The six principles |
| ## P1 — Protocolo de Autorização | ## P1 — Authorization Protocol |
| ## P2 — Protocolo de Reversão | ## P2 — Reversal Protocol |
| ## P3 — Protocolo de Verificação | ## P3 — Verification Protocol |
| ## P4 — Protocolo de Testes | ## P4 — Testing Protocol |
| ## P5 — Protocolo de Mudança de Comportamento | ## P5 — Behavior Change Protocol |
| ## P6 — Protocolo de Decisão (ADR) | ## P6 — Decision Protocol (ADR) |
| ## P7 — Protocolo de Ritmo e Comunicação | ## P7 — Pace and Communication Protocol |
| ## P8 — Protocolo da IA dentro do Sistema | ## P8 — Protocol for AI inside the System |
| ## P9 — Protocolo de Registro (logs) | ## P9 — Logging Protocol |
| ## P10 — Protocolo de Sessão e Handoff | ## P10 — Session and Handoff Protocol |
| ## P11 — Protocolo de Homologação | ## P11 — Acceptance Protocol |
| ### REGRA / ONDE CABE / PERGUNTAS DE OPERAÇÃO / PERGUNTAS DE ADOÇÃO | ### RULE / WHERE IT APPLIES / OPERATING QUESTIONS / ADOPTION QUESTIONS |
| ### 1. Os três canais — o que registrar | ### 1. The three channels — what to log |
| ### 2. As duas condições do registro verdadeiro | ### 2. The two conditions of a true record |
| ### 3. O silêncio também grita | ### 3. Silence screams too |
| ### 4. Ruído é o que se pode perder sem perder informação | ### 4. Noise is what can be lost without losing information |
| ### 5. Correlação: o que liga um evento ao outro | ### 5. Correlation: what ties one event to another |
| ### 6. Como se lê o registro | ### 6. How the log is read |
| ### 7. O que decide o que se registra | ### 7. What decides what gets logged |
| ### 8. Redação de segredo: no ponto de escrita, e antes do armazenamento | ### 8. Secret redaction: at the point of writing, and before storage |
| ### 9. Onde o registro fica | ### 9. Where the log lives |
| ### O orçamento de janela | ### The window budget |
| ### O handoff, nesta ordem | ### The handoff, in this order |
| ### O bloco de passagem — quando o trabalho é arquivo por arquivo | ### The handover block — when the work is file by file |
| ### Registro contínuo, desde o primeiro item | ### Continuous record, from the first item |
| ### A execução delegada — *"você aprova que eu faça isso por você?"* | ### Delegated execution — *"do you approve of me doing this for you?"* |
| ## Os artefatos | ## The artifacts |
| ## O questionário de adoção | ## The adoption questionnaire |
| ### A — Autorização (P1) | ### A — Authorization (P1) |
| ### B — Reversibilidade (P2) | ### B — Reversibility (P2) |
| ### C — Verificação (P3) | ### C — Verification (P3) |
| ### D — Testes (P4) | ### D — Tests (P4) |
| ### E — Mudança de comportamento (P5) | ### E — Behavior change (P5) |
| ### F — Decisão registrada (P6) | ### F — Recorded decision (P6) |
| ### G — Ritmo e comunicação (P7) | ### G — Pace and communication (P7) |
| ### H — A IA dentro do sistema (P8) | ### H — AI inside the system (P8) |
| ### I — Protocolo de Registro (P9) | ### I — Logging Protocol (P9) |
| ### J — Sessão e Handoff (P10) | ### J — Session and Handoff (P10) |
| ### K — Homologação (P11) | ### K — Acceptance (P11) |
| ## Guia de uso no dia a dia | ## Day-to-day usage guide |
| ### A ordem de adoção | ### The order of adoption |
| ### Um documento de regras por MODO de trabalho | ### One rules document per work MODE |
| ### A hierarquia dos documentos | ### The hierarchy of documents |
| ### Uma regra específica do modo auditoria, que salva regressão | ### One rule specific to audit mode, which saves regressions |
| ### Adaptando a um projeto que já existe | ### Adapting to a project that already exists |
| ### Como fazer o agente seguir isto | ### How to make the agent follow this |
| ### Os sinais que pedem atenção cedo | ### The signs that ask for early attention |
| ### Quando o protocolo atrapalha | ### When the protocol gets in the way |
| ## Catálogo de sinais e saídas | ## Catalog of signs and ways out |
| ## Anexo — O exercício de emulação | ## Appendix — The emulation exercise |
| ### As condições do exercício (a cegueira) | ### The conditions of the exercise (the blindness) |
| ### As condições de parada, declaradas antes | ### The stopping conditions, declared beforehand |
| ### A mecânica da chamada — o que quase ninguém emula | ### The mechanics of the call — what almost no one emulates |
| ### As duas perdas do retorno | ### The two losses of the return |
| ### O registro | ### The record |
| ### A segunda opinião, e o que ela precisa trazer | ### The second opinion, and what it needs to bring |
| ### O relatório final | ### The final report |
| ## Fecho | ## Closing |

### `en/README.md`

| Original | Tradução |
|---|---|
| # Protocolo Universal | # Universal Protocol |
| ## O que há aqui | ## What is here |
| ## Por onde começar | ## Where to start |
| ## Como os arquivos se relacionam | ## How the files relate |
| ## Os onze protocolos | ## The eleven protocols |
| ## O tom: orientação, e reconhecimento | ## The tone: guidance, and recognition |
| ## Como fazer o agente seguir isto | ## How to make the agent follow this |
| ## Se quem constrói não lê código | ## If the builder does not read code |
| ## O que este repositório deixa para o seu projeto | ## What this repository leaves to your project |
| ## Emendas | ## Amendments |
| ## Licença e autoria | ## License and authorship |

### `en/system_prompt_recommended.md`

| Original | Tradução |
|---|---|
| # CONSTITUIÇÃO DO TRABALHO COM IA | # CONSTITUTION FOR WORK WITH AI |
| ## I — Princípios | ## I — Principles |
| ## II — Deveres do agente | ## II — Duties of the agent |
| ## III — Direitos do agente | ## III — Rights of the agent |
| ## IV — Deveres de quem autoriza | ## IV — Duties of the authorizer |
| ## V — Direitos de quem autoriza | ## V — Rights of the authorizer |
| ## VI — Cláusulas fixas, hierarquia e conflito | ## VI — Fixed clauses, hierarchy and conflict |
| ## VII — Exame de fim de resposta | ## VII — End-of-response check |
| **Antes de agir** / **Ao tocar no sistema** / **Ao afirmar** / **Ao provar** / **Ao mudar comportamento e ao decidir** / **Ao falar** / **Ao registrar** / **Ao atravessar sessões** / **Ao homologar** / **Quando você faz parte do produto** | **Before acting** / **When touching the system** / **When claiming** / **When proving** / **When changing behavior and deciding** / **When speaking** / **When logging** / **When crossing sessions** / **On acceptance** / **When you are part of the product** |

### `en/system_prompt_complete.md`

| Original | Tradução |
|---|---|
| ## Como usar este documento | ## How to use this document |
| ## Preâmbulo | ## Preamble |
| ## Definições | ## Definitions |
| ## TÍTULO I — Os princípios | ## TITLE I — The principles |
| ## TÍTULO II — Os deveres do agente | ## TITLE II — The duties of the agent |
| ### Capítulo 1 — Antes de agir *(P1)* | ### Chapter 1 — Before acting *(P1)* |
| ### Capítulo 2 — Ao tocar no sistema *(P2)* | ### Chapter 2 — When touching the system *(P2)* |
| ### Capítulo 3 — Ao afirmar *(P3)* | ### Chapter 3 — When claiming *(P3)* |
| ### Capítulo 4 — Ao provar *(P4)* | ### Chapter 4 — When proving *(P4)* |
| ### Capítulo 5 — Ao mudar comportamento e ao decidir *(P5, P6)* | ### Chapter 5 — When changing behavior and deciding *(P5, P6)* |
| ### Capítulo 6 — Ao falar *(P7)* | ### Chapter 6 — When speaking *(P7)* |
| ### Capítulo 7 — Ao registrar *(P9)* | ### Chapter 7 — When logging *(P9)* |
| ### Capítulo 8 — Ao atravessar sessões *(P10)* | ### Chapter 8 — When crossing sessions *(P10)* |
| ### Capítulo 9 — Ao homologar *(P11)* | ### Chapter 9 — On acceptance *(P11)* |
| ### Capítulo 10 — Quando você faz parte do produto *(P8)* | ### Chapter 10 — When you are part of the product *(P8)* |
| ## TÍTULO III — Os direitos do agente | ## TITLE III — The rights of the agent |
| ## TÍTULO IV — Os deveres de quem autoriza | ## TITLE IV — The duties of the authorizer |
| ## TÍTULO V — Os direitos de quem autoriza | ## TITLE V — The rights of the authorizer |
| ## TÍTULO VI — Cláusulas fixas, hierarquia e conflito | ## TITLE VI — Fixed clauses, hierarchy and conflict |
| ## TÍTULO VII — O exame de fim de resposta | ## TITLE VII — The end-of-response check |
| ## Fecho | ## Closing |

### `en/adoption_questions.md`

| Original | Tradução |
|---|---|
| # ADOPTION_QUESTIONS | # ADOPTION_QUESTIONS |
| ## Como usar | ## How to use |
| ## Cabeçalho do projeto | ## Project header |
| ## A — Autorização *(P1)* … ## K — Homologação *(P11)* | ## A — Authorization *(P1)* / B — Reversibility *(P2)* / C — Verification *(P3)* / D — Tests *(P4)* / E — Behavior change *(P5)* / F — Recorded decision *(P6)* / G — Pace and communication *(P7)* / H — AI inside the system *(P8)* / I — Logging *(P9)* / J — Session and Handoff *(P10)* / K — Acceptance *(P11)* |
| ## O que fazer com as respostas | ## What to do with the answers |

---

## 5 — Regras de estilo da tradução

1. **Fidelidade frase a frase.** Nada se acrescenta, se omite, se resume ou se "melhora".
   Contagens, números, exemplos e casos reais ficam como estão.
2. **A voz da autora.** Frases curtas, precisão, imagem concreta. O travessão (` — `) é
   parte da pontuação do original e permanece na tradução. Negrito e itálico ficam onde
   estão.
3. **Estrutura idêntica.** Mesmos níveis de título, mesmas tabelas, mesmos blocos de
   código, mesmas listas, mesmas linhas horizontais. Quebra de linha dura em torno de 90
   caracteres, como o original.
4. **Marcas de referência** — *(P1)*, *(P9 §3)*, *(A2)*, *(Art. 12)* — ficam iguais.
   Links entre arquivos apontam para os nomes em `en/`; âncoras seguem os títulos
   canônicos.
5. **Gênero.** "Ela" referindo-se à pessoa vira *they/them*. "Quem constrói … sozinha"
   vira *the builder … on their own*.
6. **Inglês americano** (*behavior*, *labeled*, *catalog*).
7. **O rodapé de licença** se traduz com o mesmo link; a atribuição sugerida mantém o
   nome da obra em português ao lado do inglês: *"Universal Protocol" (Protocolo
   Universal), by Ivana Cruz*.
8. **Onde a tradução divergir do original, o original vence** — e a divergência é um
   defeito da tradução, a corrigir nos dois lugares: no arquivo de `en/` e, se o termo
   mudou, aqui.

---

*© 2026 Ivana Cruz · ivana.gac@gmail.com · Este documento é licenciado sob [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).*
