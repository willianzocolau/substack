# O que uma cerimônia mensal de incident review tem a ver com qualidade técnica

---

## Quando um comportamento inesperado no seu domínio vira armadilha de processo

Um PR sobe na sexta. A funcionalidade principal continua funcionando, os alertas estão tranquilos, ninguém reclama. Alguns dias depois alguém percebe que um fluxo secundário — usado por poucos clientes num cenário bem específico — parou de funcionar do jeito esperado.

O time abre o incidente.

Aí vem a pergunta que, na prática, separa muito o nível de maturidade de um time: isso era um incidente ou um bug crítico?

Em domínios com impacto financeiro direto, quase qualquer comportamento inesperado pode ser enquadrado como incidente se você quiser. O problema é que, quando isso vira padrão, o processo começa a competir com o roadmap, stakeholders recebem comunicações desnecessárias e a engenharia entra num ciclo reativo difícil de sair.

A ambiguidade em torno de quando declarar um incidente custa mais do que o incidente em si. E essa é exatamente a confusão que uma cerimônia mensal de incident review, conduzida com consistência, ajuda a endereçar — não só no calor do momento, mas antes do próximo acontecer.

---

## A ambiguidade custa mais do que o incidente

Nem todo problema técnico é um incidente. Essa distinção parece óbvia no papel, mas na prática ela some rápido quando há pressão, quando o domínio é sensível ou quando o time ainda está calibrando o que de fato importa.

Uma definição que funciona bem na prática:

- **Incidente**: evento adverso cujo impacto excede um limiar mínimo de relevância para o negócio — em volume, valor ou criticidade estratégica — e que exige resposta e comunicação imediata entre diferentes áreas.
- **Bug crítico**: falha que pode potencialmente causar um incidente no futuro, mas que ainda não atingiu esse limiar. Pode exigir ação imediata, mas o tratamento é diferente.

O incidente é uma ferramenta de coordenação, não de priorização. Ele existe para dar visibilidade e articular times diferentes em torno de um problema relevante. Usar esse canal para comunicar algo que poderia ser resolvido como bug crítico gera ruído — e ruído tem custo.

Times evoluem. Pessoas entram, saem, mudam de squad. Isso é natural e esperado. Mas sem um momento regular de realinhamento, cada movimentação traz consigo interpretações diferentes do que é um incidente, como conduzir, o que documentar, quando escalar — e o processo vai se calibrando de formas diferentes em cada parte do time, sem que ninguém perceba.

Outros erros comuns: incidente declarado sem commander definido, comunicação técnica demais num canal que inclui suporte e produto, post-mortem sem causa raiz real, acionáveis sem dono e sem prazo. Cada um parece pequeno isolado. Juntos, constroem um time que reage mal quando o que importa acontece.

---

## Cola entre squads, não bombeiro de plantão

Tech leads têm influência direta sobre o grupo com quem trabalham. Conhecem o contexto, acompanham o dia a dia, participam das decisões técnicas do squad. Mas quando o time cresce e passa a ter múltiplos squads atuando em domínios relacionados, aparece um gap natural: quem tem a visão do todo?

Esse é um dos espaços onde o papel de staff engineer faz mais sentido. Não é sobre estar em todas as decisões — isso não escala e cria dependência. É sobre influenciar o ambiente em que as decisões acontecem.

A cerimônia de incident review é um mecanismo concreto para isso. Num time de 25 a 30 pessoas, com incidentes acontecendo em contextos distintos, conduzir uma revisão mensal com todos os squads presentes cria algo que é difícil de construir de outra forma: **entendimento compartilhado**. As pessoas que não estiveram no incidente aprendem com quem esteve. Quem conduziu tem a oportunidade de desenvolver habilidades de comunicação e análise de causa raiz. O time inteiro calibra junto o que é um incidente, o que é bug crítico, como conduzir, o que esperar.

O staff não precisa ter estado presente no incidente para conduzir bem essa conversa. Pelo contrário — a distância do detalhe ajuda a fazer as perguntas certas: o impacto foi bem avaliado antes de declarar? A causa raiz foi de fato identificada ou apenas o sintoma? Os acionáveis evitam reincidência ou só corrigem o que quebrou?

Essas perguntas, feitas com consistência mês a mês, influenciam como o time pensa — sem precisar de aprovação em cada PR ou presença em cada refinamento.

---

## O que não pode faltar em uma hora por mês

A cerimônia acontece uma vez por mês, na primeira semana — tempo suficiente para os post-mortems do mês anterior estarem concluídos e as informações consolidadas. Uma hora é o suficiente se a estrutura estiver clara.

A agenda segue sempre a mesma ordem:

**1. Boas práticas e processo**
Antes de entrar nos números, um reforço rápido do processo. Definição de incidente vs bug crítico, etapas do fluxo, critérios do post-mortem, boas práticas de comunicação durante um incidente. Parece repetitivo — e é exatamente esse o ponto, que abordo mais à frente.

**2. Métricas do período**
Quatro métricas acompanhadas de forma consistente:

- **MTTA** (início do problema → reportado): quanto tempo o time leva para identificar e declarar
- **MTTS** (reportado → corrigido): velocidade de resposta após a declaração
- **Incident Duration** (reportado → resolvido): duração total do incidente
- **MTTR** (início → resolvido): visão completa do impacto no tempo

Além das métricas de resposta, acompanho a **completude dos acionáveis** e a **reincidência de incidentes**. Um acionável proposto e não executado é um aprendizado que não se concretizou. Um incidente que se repete é um sinal de que o processo falhou em algum ponto.

**3. Revisão dos incidentes do período**
Os commanders de cada incidente apresentam: o que aconteceu, causa raiz, solução e acionáveis. O objetivo não é apontar culpados — é aprender junto. Quem conduziu o incidente ganha visibilidade, pratica comunicação técnica para uma audiência maior e recebe perspectivas que talvez não tenham surgido durante a condução.

A discussão aberta com o time frequentemente traz ângulos novos: um cenário que ninguém tinha considerado, uma dependência que outros squads conhecem melhor, uma solução mais simples que ficou fora do radar durante o stress do incidente.

**4. Melhoria contínua**
O encerramento é reservado para quem fez algo proativamente interessante no período — uma melhoria de monitoramento, uma refatoração que reduziu risco, uma documentação que destrancou um processo. Não precisa ser grande. Precisa ser reconhecido.

Esse momento envia uma mensagem clara para o time: qualidade não é só sobre resolver incidentes, é sobre evitá-los.

---

## Times aprendem com consistência, não com eventos

Existe uma tendência natural de tratar processos como algo que se explica uma vez e fica. Escreve o playbook, apresenta para o time, segue em frente. Na prática, não funciona assim.

Sem reforço, o aprendizado não se consolida. Isso vale para conceitos técnicos, para processos operacionais e para julgamentos que dependem de calibração coletiva, como decidir quando declarar um incidente ou como conduzir um post-mortem com qualidade.

O que faz a cerimônia funcionar não é a sofisticação da agenda. É o fato de acontecer todo mês, com a mesma estrutura, enquanto o objetivo ainda faz sentido. Se o objetivo é reduzir reincidência, a cerimônia continua até esse comportamento estar incorporado no time. Se surgir um novo objetivo, ela se recalibra em torno dele. A consistência é o que transforma uma reunião em um mecanismo de aprendizado.

Cada vez que o processo é retomado, ele é reforçado para quem já conhece e apresentado de forma contextualizada para quem chegou recentemente. As métricas analisadas calibram coletivamente o que é uma resposta adequada. Os incidentes revistos em grupo constroem uma memória compartilhada que documentação isolada não consegue substituir.

O livro *Accelerate*, de Forsgren, Humble e Kim, aponta que times de alta performance são 2,5x mais propensos a usar falhas como oportunidade de aprendizado. O Google SRE usa o que chama de *Wheel of Misfortune*, reencenações de post-mortems anteriores para treinar engenheiros com situações reais. A lógica é a mesma: aprendizado técnico se consolida com repetição deliberada.

A cerimônia mensal cumpre esse papel. Não porque o time não entendeu da primeira vez, mas porque entender uma vez não é suficiente para mudar comportamento.

---

## Menos capacity em acionáveis, mais espaço para entregar valor

Um dos efeitos mais diretos de um processo de incidentes bem calibrado é a redução do tempo que o time gasta em acionáveis reativos. Menos reincidência significa menos interrupção, menos contexto trocado no meio de uma entrega, menos engenheiro desviado do que estava fazendo para resolver algo que já aconteceu antes.

Esse espaço liberado não necessariamente vira feature. Pode virar trabalho estruturante de engenharia — aquele que não aparece no roadmap de produto mas que habilita o negócio a crescer com mais segurança. Uma migração que estava travada, uma dívida técnica que aumentava o risco a cada sprint, uma melhoria de observabilidade que vai detectar o próximo problema antes que vire incidente.

O efeito não aparece no primeiro mês. Aparece no acúmulo — quando o time começa a agir de forma mais preventiva, quando os alertas que antes exigiam intervenção manual passam a se resolver sozinhos, quando a discussão em torno de qualidade deixa de ser reativa e passa a fazer parte do dia a dia.

Nenhum desse resultado vem de uma iniciativa pontual. Vem da repetição consistente de um processo simples, todo mês.

---

## Por onde começar

Antes de marcar a primeira reunião, vale um passo atrás: qual é o objetivo?

A cerimônia de incident review pode servir a propósitos diferentes dependendo do momento do time. Alguns exemplos:

- O time declara tudo como incidente e o processo está competindo com o roadmap — o objetivo é **remover ambiguidade**
- Os mesmos problemas voltam com nomes diferentes — o objetivo é **reduzir reincidência**
- A condução dos incidentes é inconsistente, a comunicação é técnica demais, o post-mortem não tem causa raiz real — o objetivo é **melhorar o processo**
- Qualidade técnica não é um tema recorrente nas discussões do time — o objetivo é **influenciar cultura**
- O time está sempre em modo reativo, sem espaço para trabalho estruturante — o objetivo é **sair do ciclo de apagar incêndio**

Você provavelmente vai se identificar com mais de um. Tudo bem — mas ter clareza sobre a prioridade ajuda a montar uma agenda que faça sentido para o momento.

O segundo passo é conhecer bem o seu domínio. Os limiares que definem um incidente no contexto de billing são diferentes dos de uma plataforma de comunicação, que são diferentes dos de uma ferramenta interna. Não existe uma definição universal que funcione para todos — existe uma definição que faz sentido para o impacto que o seu sistema tem no negócio.

A ferramenta que você usa para registrar e acompanhar incidentes importa menos do que a consistência com que o processo é seguido. O que importa é ter um lugar onde as métricas são geradas automaticamente a partir das etapas do incidente, onde o post-mortem fica documentado e onde os acionáveis têm dono e prazo.

Comece pequeno, com o objetivo claro, e mantenha por tempo suficiente para ver os efeitos. A cerimônia ganha valor com o acúmulo.

---

Se quiser ir além na definição dos limiares que determinam o que é um incidente no seu contexto, um passo importante é ter SLOs bem definidos para o seu domínio. Escrevi sobre como abordar isso na prática aqui: [Escalando Sidekiq no Kubernetes: uma abordagem orientada a SLOs](https://www.linkedin.com/pulse/escalando-sidekiq-kubernetes-uma-abordagem-orientada-slos-zocolau-cvx4c/)
