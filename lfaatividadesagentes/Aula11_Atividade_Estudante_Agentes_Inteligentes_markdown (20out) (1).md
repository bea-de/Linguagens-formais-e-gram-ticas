# Atividade sobre agentes inteligentes

Aula 20/10/2026 | Professora Kadidja Valéria | Inteligência artificial

**Disciplina:** Linguagens Formais e Autômatos | ciência da Computação

**Estudante:** Beatriz Nevis Miranda | **Turma:** [N1- noturna]

Realize os exercícios 2.3, 2.4 e 2.5 do Capítulo 2 sobre agentes inteligentes. Analise a racionalidade, descreva ambientes de tarefa por meio do modelo PEAS e explique os conceitos com suas próprias palavras. Utilize o capítulo disponibilizado e justifique suas respostas.

**Modalidade sugerida:** individual com consulta. **Tempo estimado:** 2h30. **Prazo:** conforme orientação da professora.

## Preparação
Leia os tópicos sobre racionalidade, ambientes e estrutura dos agentes, especialmente a Seção 2.3.2.

## Exercício 2.3
Para cada afirmação, indique V ou F, justifique e forneça exemplo ou contraexemplo. Explicite as hipóteses utilizadas.

### a. Um agente que detecta apenas informações parciais sobre o estado não pode ser perfeitamente racional.

- Julgamento: F
- Justificativa: A racionalidade depende de maximizar o desempenho esperado com base nas percepções acumuladas até o momento, e não em omnisapiência. Um agente pode tomar a melhor decisão possível sob incerteza ou falta de informação completa.
- Exemplo ou contraexemplo: Um carro autônomo trafegando em uma via com neblina densa ainda pode ser perfeitamente racional ao adotar uma direção defensiva e prudente com base no que seus sensores conseguem captar.

### b. Existem ambientes de tarefa nos quais nenhum agente reativo puro pode comportar-se racionalmente.

- Julgamento: V
- Justificativa: Agentes reativos puros tomam decisões baseadas apenas na percepção atual, sem manter um estado interno para rastrear aspectos do mundo que não estão visíveis no momento (ambientes parcialmente observáveis ou não observáveis).
- Exemplo ou contraexemplo: Em um ambiente parcialmente observável (como o jogo de Pôquer), um agente reativo puro que não considera o histórico das jogadas e cartas ocultas inevitavelmente tomará decisões irracionais no longo prazo.

### c. Existe um ambiente de tarefa em que todo agente é racional.

- Julgamento: V
- Justificativa: Em um ambiente estático, totalmente previsível e trivial — onde há apenas uma ação possível ou todas as ações conduzem exatamente ao mesmo resultado ideal —, qualquer ação escolhida atinge o objetivo máximo.
- Exemplo ou contraexemplo: Um ambiente de tarefa onde o agente está em uma sala sem saída com apenas um botão para pressionar, e qualquer ação gera a recompensa máxima.

### d. A entrada para o programa de agente é a mesma que a entrada para a função de agente.

- Julgamento: F
- Justificativa: A função de agente é um conceito abstrato que mapeia o histórico completo de percepções para uma ação. O programa de agente roda fisicamente na arquitetura e recebe como entrada apenas a percepção atual a cada ciclo de clock, mantendo o histórico internamente.
- Exemplo ou contraexemplo: Enquanto a função matemática avalia toda a sequência de percepções, o programa de software recebe apenas a percepção da iteração atual.

### e. Toda função de agente é implementável por uma combinação de programa/máquina.

- Julgamento: F
- Justificativa: Algumas funções de agente exigem um histórico infinito de percepções ou um poder de computação infinito que excede a capacidade física de qualquer máquina real.
- Exemplo ou contraexemplo: Uma função matemática que calcule a resposta ótima para um problema de xadrez com profundidade e ramificações infinitas em tempo real.

### f. Suponha que um agente selecione sua ação uniformemente ao acaso do conjunto de ações possíveis. Existe um ambiente de tarefa determinista em que esse agente é racional.

- Julgamento: V
- Justificativa: Se o ambiente for extremamente restrito, onde todas as ações possíveis do conjunto levam ao mesmo estado de sucesso ótimo, a escolha aleatória sempre será bem-sucedida.
- Exemplo ou contraexemplo: Um robô em uma sala onde qualquer movimento (frente, trás, esquerda, direita) resulta na conclusão bem-sucedida de uma tarefa simples de limpeza de um único ponto exato sob ele.

### g. É possível para um dado agente ser perfeitamente racional em dois ambientes de tarefa distintos.

- Julgamento: V
- Justificativa: Se dois ambientes compartilharem exatamente as mesmas dinâmicas de transição, funções de recompensa e estruturas de percepção/ação, o mesmo agente poderá maximizar seu desempenho em ambos.
- Exemplo ou contraexemplo: Um agente aspirador de pó projetado para operar perfeitamente em duas salas idênticas em dimensões e disposição de obstáculos.

### h. Todo agente é racional em um ambiente não observável.

- Julgamento: F
- Justificativa: Em ambientes não observáveis, o agente não tem dados sensoriais do estado. No entanto, se ele escolher ações sem critério ou ignorar o estado interno de crenças, ele falhará em atingir seus objetivos, tornando-se irracional.
- Exemplo ou contraexemplo: Um robô cego e sem sensores que tenta navegar por um campo minado escolhendo direções aleatoriamente e explodindo; ele não é racional.

### i. Um agente jogador de pôquer perfeitamente racional nunca perde.

- Julgamento: F
- Justificativa: O pôquer é um jogo de informação incompleta e estocástico (envolve sorte/probabilidade nas cartas). A racionalidade maximiza o ganho esperado com base nas probabilidades, mas não impede perdas pontuais decorrentes da variância estatística.
- Exemplo ou contraexemplo: Um jogador profissional de pôquer (racional) pode perder uma mão devido a uma carta improvável que o oponente receba no river.

## Exercício 2.4
Para cada caso, delimite o agente, preencha o PEAS e justifique todas as classificações. Considere Titã como cenário hipotético do exercício.

### Caso 1 — Jogar futebol.

- Agente analisado: Jogador robótico autônomo
- Objetivo e hipóteses: Marcar mais gols que o adversário respeitando as regras do jogo; assume-se comunicação estável e campo padronizado.
- P — Medida de desempenho: Número de gols marcados, faltas evitadas, posse de bola e vitória na partida.
- E — Ambiente: Campo de futebol, bola, companheiros e adversários.
- A — Atuadores: Pernas/pés mecânicos para chute e movimentação, módulos de comunicação sonora/sem fio.
- S — Sensores: Câmeras de visão computacional, giroscópios e sensores de proximidade.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | O agente não vê o campo inteiro de uma vez e há o posicionamento oculto/encoberto de oponentes. |
| Número de agentes | Multiagente (competitivo e cooperativo) | Envolve equipe própria (cooperação) e adversários (competição). |
| Previsibilidade | Estocástico | As reações dos adversários e o comportamento físico da bola geram incertezas. |
| Dependência entre decisões | Sequencial | As ações atuais impactam diretamente as jogadas e o placar futuro. |
| Mudança durante a decisão | Dinâmico | O jogo continua fluindo e mudando enquanto o agente processa seu cálculo de decisão. |
| Natureza dos elementos | Contínuo | O tempo, as posições espaciais e a força dos movimentos variam de forma contínua. |
| Conhecimento do funcionamento | Conhecido | As regras da física e do futebol são conhecidas pelo projeto do agente. |

### Caso 2 — Explorar os oceanos subterrâneos de Titã.

- Agente analisado: Sonda submersível autônoma
- Objetivo e hipóteses: Mapear o fundo oceânico, coletar amostras de metano líquido e identificar bioassinaturas; assume-se condições extremas de pressão e temperatura.
- P — Medida de desempenho: Volume de dados científicos coletados, integridade estrutural da sonda e diversidade de amostras.
- E — Ambiente: Oceano subterrâneo de Titã, correntes líquidas, fundo rochoso e obstáculos submersos.
- A — Atuadores: Propulsores, braço mecânico articulado e brocas de coleta.
- S — Sensores: Sonar, câmeras de alta profundidade, termômetros e espectrômetros químicos.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | A visibilidade na água/metano densa e escura é limitada ao alcance de luz/sonar. |
| Número de agentes | Agente único | A missão depende primariamente da sonda operando de forma autônoma. |
| Previsibilidade | Estocástico | Correntes subterrâneas desconhecidas e falhas mecânicas tornam o ambiente imprevisível. |
| Dependência entre decisões | Sequencial | Uma manobra errada de navegação pode destruir a sonda ou emperrá-la permanentemente. |
| Mudança durante a decisão | Dinâmico | O ambiente muda continuamente devido a fluxos de fluidos e instabilidade geológica. |
| Natureza dos elementos | Contínuo | Variáveis físicas como temperatura, pressão, coordenadas e tempo são contínuas. |
| Conhecimento do funcionamento | Desconhecido | A geologia e as correntes específicas do oceano de Titã são inicialmente desconhecidas. |

### Caso 3 — Comprar livros usados de IA na Internet.

- Agente analisado: Robô de compras (crawler/bot financeiro)
- Objetivo e hipóteses: Adquirir livros de IA pelo menor preço total (incluindo frete) em bom estado; assume-se disponibilidade de sites de e-commerce.
- P — Medida de desempenho: Economia financeira obtida, qualidade do livro comprado e tempo de transação.
- E — Ambiente: Sites de e-commerce, sebos virtuais e APIs de livrarias.
- A — Atuadores: Scripts de requisição HTTP, preenchimento de formulários de compra e envio de pagamento digital.
- S — Sensores: Conexão de rede, parsers HTML de páginas web e APIs de inventário.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | O estoque de terceiros e livros que podem surgir ou esgotar a qualquer momento não são totalmente visíveis. |
| Número de agentes | Multiagente (competitivo) | Outros compradores e robôs competem pelos mesmos livros raros em promoção. |
| Previsibilidade | Estocástico | Os preços mudam e os concorrentes podem comprar o livro antes da finalização. |
| Dependência entre decisões | Sequencial | Decisões de esperar o preço baixar ou comprar imediatamente afetam o sucesso final. |
| Mudança durante a decisão | Semidinâmico | O ambiente muda com o tempo (preços alteram), mas não necessariamente enquanto o algoritmo processa uma linha de código específica. |
| Natureza dos elementos | Discreto | A contagem de itens, o preço em centavos e as páginas de produtos são representados discretamente. |
| Conhecimento do funcionamento | Conhecido | As regras de funcionamento da internet, protocolos web e plataformas são conhecidas. |

### Caso 4 — Jogar uma partida de tênis.

- Agente analisado: Jogador humano ou robô humanoide competidor
- Objetivo e hipóteses: Vencer o set/partida marcando pontos através de jogadas válidas; assume-se quadra oficial e oponente ativo.
- P — Medida de desempenho: Número de games e sets vencidos, taxa de erros não forçados e vitória na partida.
- E — Ambiente: Quadra de tênis, rede, raquete, bola e oponente.
- A — Atuadores: Braços e pernas para rebatida e deslocamento em quadra.
- S — Sensores: Visão humana/câmeras e sistema vestibular/propriocepção.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Completamente observável | O agente enxerga a quadra inteira, a posição da bola e do oponente o tempo todo. |
| Número de agentes | Multiagente (competitivo) | Envolve um oponente direto disputando o mesmo objetivo de vitória. |
| Previsibilidade | Estocástico | Os efeitos do vento, o efeito aplicado na bola pelo oponente e os ressaltos geram incerteza. |
| Dependência entre decisões | Sequencial | Cada rebatida define a jogada seguinte e afeta a estratégia do oponente. |
| Mudança durante a decisão | Dinâmico | A bola se movimenta velozmente enquanto o jogador planeja o golpe. |
| Natureza dos elementos | Contínuo | Trajetória da bola, tempo, força e posições espaciais ocorrem em espectro contínuo. |
| Conhecimento do funcionamento | Conhecido | As leis físicas do movimento da bola e as regras do tênis são conhecidas. |

### Caso 5 — Praticar tênis contra uma parede.

- Agente analisado: Jogador solitário (humano ou robô)
- Objetivo e hipóteses: Manter a bola em movimento contínuo rebatendo-a na parede; assume-se parede plana e rebote previsível.
- P — Medida de desempenho: Número de rebatidas consecutivas sem deixar a bola cair e precisão dos golpes.
- E — Ambiente: Parede de treino, piso da quadra, raquete e bola.
- A — Atuadores: Movimentos corporais e balanço da raquete.
- S — Sensores: Visão e percepção espacial da trajetória da bola.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Completamente observável | Todo o espaço de interação (parede, bola, próprio corpo) está visível. |
| Número de agentes | Agente único | Não há oponente estratégico interferindo ativamente nas decisões. |
| Previsibilidade | Determinístico | A parede reflete a bola de maneira previsível baseada na física do impacto. |
| Dependência entre decisões | Sequencial | Um erro mecânico na rebatida atual interrompe o exercício (sequência contínua). |
| Mudança durante a decisão | Dinâmico | O ambiente e a posição da bola mudam de forma contínua no tempo. |
| Natureza dos elementos | Contínuo | Ângulos, velocidades e coordenadas espaciais são contínuos. |
| Conhecimento do funcionamento | Conhecido | As leis físicas que regem o rebote na parede são totalmente compreendidas. |

### Caso 6 — Realizar um salto de altura.

- Agente analisado: Atleta (humano ou robô)
- Objetivo e hipóteses: Ultrapassar a maior altura possível na barra sem derrubá-la; assume-se pista e equipamento padronizados.
- P — Medida de desempenho: Altura máxima do sarrafo ultrapassada com sucesso.
- E — Ambiente: Pista de atletismo, colchão de queda, varão e barra de salto.
- A — Atuadores: Musculatura das pernas, tronco e braços para impulsão e transposição.
- S — Sensores: Visão para balizamento da corrida e propriocepção corporal.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Completamente observável | A barra, a pista e a distância até o obstáculo estão totalmente visíveis. |
| Número de agentes | Agente único | A execução física depende exclusivamente do desempenho isolado do atleta. |
| Previsibilidade | Determinístico | A biomecânica do salto e a gravidade operam de forma previsível e constante. |
| Dependência entre decisões | Sequencial | A fase de aproximação (corrida) condiciona o impulso, que condiciona a curva de voo. |
| Mudança durante a decisão | Dinâmico | O movimento ocorre em tempo real de forma fluida e rápida. |
| Natureza dos elementos | Contínuo | Tempo, altura, velocidade de corrida e forças aplicadas são contínuos. |
| Conhecimento do funcionamento | Conhecido | A biomecânica e as leis da gravidade são conhecidas. |

### Caso 7 — Participar de um leilão de um item, realizando lances.

- Agente analisado: Agente de leilão automatizado (software de lances)
- Objetivo e hipóteses: Arrematar o item desejado pelo menor preço possível, abaixo de um teto orçamentário; assume-se leilão online padrão.
- P — Medida de desempenho: Obtenção do item e economia financeira em relação ao valor máximo estipulado.
- E — Ambiente: Plataforma de leilão online e concorrentes virtuais.
- A — Atuadores: Submissão de valores de lances via interface web ou API.
- S — Sensores: Leitura de lances atuais da página, cronômetro da sessão e status do leilão.

| Propriedade | Classificação | Justificativa |
|---|---|---|
| Observabilidade | Parcialmente observável | O orçamento máximo e a estratégia oculta dos outros licitantes não são totalmente visíveis. |
| Número de agentes | Multiagente (competitivo) | Outros participantes disputam o mesmo lote oferecendo lances concorrentes. |
| Previsibilidade | Estocástico | O comportamento de lance de terceiros introduz incerteza no resultado. |
| Dependência entre decisões | Sequencial | Os lances passados influenciam as reações dos concorrentes e definem a estratégia futura. |
| Mudança durante a decisão | Semidinâmico | O tempo corre e o leilão avança, mas as decisões ocorrem em momentos discretos de envio de lances. |
| Natureza dos elementos | Discreto | Os valores monetários dos lances são finitos e segmentados em unidades discretas (centavos). |
| Conhecimento do funcionamento | Conhecido | As regras do leilão e os termos da plataforma são conhecidas. |

### Comparação final
1. O que muda entre jogar tênis contra outra pessoa e praticar contra uma parede?
​2. Por que comprar livros usados pode exigir decisões com informações incompletas?
3. Como outros agentes influenciam futebol e leilões?

Respostas: 
1. Contra outra pessoa, o ambiente é multiagente competitivo e estocástico, exigindo teoria da mente e estratégia adaptativa. Contra a parede, o ambiente é de agente único e determinístico, onde a resposta física é mecânica e previsível.
2. Porque o estoque de sebos digitais é volátil e limitado; livros raros podem ser vendidos por concorrentes a qualquer segundo, e o estado real de conservação pode diferir da descrição.
3. No futebol, os adversários atuam estrategicamente para bloquear e contra-atacar, exigindo cooperação e competição direta. Nos leilões, os concorrentes competem elevando os preços e alterando o valor esperado do item.

## Exercício 2.5
Defina cada termo com suas palavras em duas a quatro linhas e apresente um exemplo.

### Agente

- Definição: Entidade autônoma capaz de perceber seu ambiente por meio de sensores e agir sobre ele utilizando atuadores para atingir determinados objetivos.
- Exemplo: Um robô aspirador que limpa a casa identificando sujeira pelos sensores e movendo-se pelas rodas.

### Função de agente

- Definição: Descrição abstrata puramente matemática que mapeia qualquer histórico de percepções possíveis para uma ação correspondente.
- Exemplo: Uma tabela de regras fixa que associa a percepção "sujo" à ação "ligar aspirador".

### Programa de agente

- Definição: A implementação concreta da função de agente executada em uma arquitetura física para rodar o algoritmo de tomada de decisão.
- Exemplo: O código implementado no processador do robô aspirador que lê os dados do sensor a cada ciclo.

### Racionalidade

- Definição: Propriedade de agir de forma a maximizar o desempenho esperado com base nas percepções acumuladas e no conhecimento prévio do agente.
- Exemplo: Um termostato que liga o ar-condicionado quando a temperatura sobe acima do limite configurado.

### Autonomia

- Definição: Grau de independência com que um agente opera, aprendendo e tomando decisões com base em suas próprias experiências em vez de depender exclusivamente de instruções rígidas pré-programadas.
- Exemplo: Um carro autônomo que decide desviar de um buraco novo na pista por conta própria.

### Agente reativo

- Definição: Agente que toma decisões baseando-se estritamente na percepção atual, desconsiderando o histórico de percepções passadas.
- Exemplo: Um sensor de presença que acende a luz imediatamente ao detectar movimento.

### Agente baseado em modelo

- Definição: Agente que mantém um estado interno para modelar aspectos do mundo que não estão visíveis no momento, compreendendo como o mundo funciona e evolui.
- Exemplo: Um robô aspirador que armazena internamente um mapa dos cômodos da casa já limpos.

### Agente baseado em objetivos

- Definição: Agente que utiliza informações sobre metas e objetivos desejados para selecionar ações que o aproximem do estado final almejado.
- Exemplo: Um aplicativo de GPS que calcula a rota ideal para chegar a um endereço específico.

### Agente baseado em utilidade

- Definição: Agente que mede o grau de sucesso ou felicidade (utilidade) de diferentes estados possíveis, escolhendo a ação que maximiza essa utilidade quando há múltiplos caminhos ou objetivos conflitantes.
- Exemplo: Um GPS que escolhe não apenas a rota mais curta, mas a que equilibra menor tempo, menor custo e menor estresse.

### Agente com aprendizagem

- Definição: Agente dotado de capacidade para melhorar seu desempenho futuro a partir de experiências passadas e do feedback recebido do ambiente.
- Exemplo: Um algoritmo de recomendação de streaming que ajusta os filmes sugeridos conforme o histórico de visualizações anteriores.

## Síntese com autômatos
Escolha um caso do item 2.4. Apresente três estados internos, três percepções, três ações e duas regras no formato estado atual + percepção → próximo estado e ação. Explique como estados internos representam informação passada e cite uma limitação da simplificação.

Resposta: 
- **Caso escolhido:** Caso 3 — Comprar livros usados de IA na Internet.
- **Estados internos:** 
  1. `ProcurandoLivro`
  2. `LivroEncontradoNoPreço`
  3. `CompraFinalizada`
- **Percepções:** 
  1. `PrecoAlto`
  2. `PrecoBom`
  3. `LivroEsgotado`
- **Ações:** 
  1. `ContinuarBusca`
  2. `ExecutarCompra`
  3. `ReiniciarPesquisa`
- **Regras:**
  1. `ProcurandoLivro` + `PrecoBom` $\rightarrow$ `LivroEncontradoNoPreço` e `ExecutarCompra`
  2. `LivroEncontradoNoPreço` + `LivroEsgotado` $\rightarrow$ `ProcurandoLivro` e `ContinuarBusca`
- **Explicação:** Os estados internos representam a memória persistente da experiência passada, permitindo que o agente saiba em qual etapa do fluxo de compra ele se encontra.
- **Limitação:** A modelagem por autômatos finitos possui uma quantidade limitada de estados discretos, o que dificulta lidar com variáveis contínuas complexas (como flutuações infinitas de preços em tempo real).

## Entrega e avaliação
Confira: identificação; nove análises no item 2.3; sete casos completos no item 2.4; dez conceitos no item 2.5; síntese; referências.
Nome sugerido: `Beatriz Miranda_AgentesInteligentes`. Prazo e envio conforme orientação da professora.

## Referências
Material-base: Capítulo 2 — Agentes inteligentes, disponibilizado para a aula de 19/10/2026.
Referências adicionais: RUSSELL, Stuart; NORVIG, Peter. **Inteligência Artificial: uma abordagem moderna**. 3. ed. Rio de Janeiro: Elsevier, 2013.
