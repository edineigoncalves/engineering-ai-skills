# System Design Coach

Uma skill reutilizável de IA para praticar entrevistas de System Design por meio de perguntas adaptativas, raciocínio arquitetural, análise de trade-offs e feedback estruturado.

Em vez de gerar uma arquitetura completa para o candidato, o System Design Coach se comporta como entrevistador ou coach e incentiva o candidato a raciocinar sobre o problema.

---

## Visão Geral

Entrevistas de System Design exigem mais do que conhecer tecnologias ou padrões comuns de arquitetura.

Espera-se que o candidato consiga:

- Esclarecer requisitos ambíguos
- Identificar requisitos funcionais e não funcionais
- Estimar escala quando relevante
- Tomar decisões arquiteturais
- Explicar trade-offs
- Identificar gargalos
- Lidar com cenários de falha
- Discutir consistência e confiabilidade
- Considerar aspectos operacionais
- Comunicar decisões com clareza

O System Design Coach foi criado para ajudar candidatos a praticar essas habilidades de forma interativa.

O objetivo não é memorizar arquiteturas.

O objetivo é melhorar o raciocínio arquitetural.

---

## Princípios Fundamentais

A skill segue alguns princípios importantes:

- Raciocínio acima de memorização
- Decisões acima de nomes de tecnologias
- Trade-offs acima de arquiteturas "perfeitas"
- Follow-ups adaptativos em vez de listas de perguntas pré-definidas
- Tópicos relevantes em vez de checklists arquiteturais
- Ajuda progressiva quando o candidato fica travado
- Feedback baseado em evidências ao final da sessão

Não existe a premissa de que um problema de System Design tenha uma única arquitetura correta.

---

## Modos

O System Design Coach suporta três modos.

### Coached

Projetado para aprendizado e prática.

O coach:

- Faz uma pergunta por vez
- Permite que o candidato raciocine antes de fornecer feedback
- Usa perguntas guiadas quando o candidato fica travado
- Explora decisões antes de corrigi-las
- Fornece feedback durante a sessão
- Explica conceitos quando necessário

O objetivo é desenvolver raciocínio em vez de fornecer respostas imediatas.

---

### Interview

Simula uma entrevista realista de System Design.

O entrevistador:

- Apresenta o problema inicialmente com informações limitadas
- Espera que o candidato esclareça os requisitos
- Gera perguntas de follow-up a partir das decisões do candidato
- Não fornece pistas ou correções durante a simulação
- Avalia decisões e trade-offs
- Fornece feedback estruturado ao final

Este modo foi projetado para reproduzir a dinâmica de uma entrevista técnica real.

---

### Pressure

Uma simulação de entrevista mais exigente, voltada principalmente para candidatos Senior ou acima.

O modo Pressure herda as regras do modo Interview e adiciona desafios como:

- Questionar premissas
- Introduzir cenários realistas de falha
- Questionar decisões de escalabilidade
- Desafiar modelos de consistência
- Introduzir mudanças plausíveis de requisitos
- Explorar aspectos operacionais
- Discutir custo e eficiência operacional
- Exigir que o candidato defenda seus trade-offs arquiteturais

O modo aumenta a dificuldade sem se tornar propositalmente adversarial.

---

## Fluxo da Sessão

Uma sessão típica pode explorar:

```text
Problema
   ↓
Clarificação de requisitos
   ↓
Requisitos funcionais
   ↓
Requisitos não funcionais
   ↓
Estimativa de escala
   ↓
Arquitetura de alto nível
   ↓
Modelo de dados
   ↓
Design de APIs / interfaces
   ↓
Componentes principais
   ↓
Fluxo de dados
   ↓
Escalabilidade
   ↓
Confiabilidade e tratamento de falhas
   ↓
Consistência e transações
   ↓
Observabilidade
   ↓
Segurança
   ↓
Trade-offs
   ↓
Gargalos
   ↓
Revisão final
```

Esse fluxo não é um checklist obrigatório.

A sessão se adapta ao problema, ao tempo disponível, à senioridade do candidato e às decisões arquiteturais tomadas durante a discussão.

---

## Follow-ups Adaptativos

Um dos principais comportamentos do System Design Coach é a geração de perguntas adaptativas.

As perguntas de follow-up são geradas a partir da resposta do candidato, e não de uma lista pré-definida.

Elas podem explorar:

- Decisões arquiteturais
- Premissas não justificadas
- Riscos
- Gargalos
- Trade-offs
- Cenários de falha
- Requisitos ignorados

Por exemplo:

```text
Candidato:
"Eu usaria Kafka entre esses serviços."

Coach:
"Qual requisito faz com que comunicação assíncrona seja útil aqui?"
```

Um follow-up posterior poderia explorar:

```text
"O que acontece se o mesmo evento for entregue duas vezes?"
```

A conversa segue a arquitetura proposta pelo candidato em vez de forçar uma solução pré-definida.

---

## Ajuda Progressiva

No modo Coached, a skill utiliza assistência progressiva quando o candidato fica travado.

```text
Pergunta Guiada
      ↓
Pista Conceitual
      ↓
Explicação Direta
```

O coach sempre começa pelo nível menos invasivo de ajuda.

### Pergunta Guiada

Ajuda o candidato a descobrir o próximo passo sozinho.

### Pista Conceitual

Fornece direcionamento sem revelar a resposta completa.

### Explicação Direta

Fornece uma explicação direta com exemplos quando o candidato continua travado ou solicita explicitamente a resposta.

---

## Áreas que Podem Ser Exploradas

Dependendo do problema, o coach pode explorar áreas como:

- Descoberta de requisitos
- Estimativa de capacidade
- Arquitetura de alto nível
- Modelagem de dados
- Design de APIs
- Escalabilidade
- Escalabilidade horizontal
- Replicação de banco de dados
- Particionamento e sharding
- Cache
- Mensageria
- Processamento assíncrono
- Backpressure
- Confiabilidade
- Recuperação de falhas
- Modelos de consistência
- Transações distribuídas
- Idempotência
- Outbox Pattern
- Saga Pattern
- Observabilidade
- Segurança
- Custo
- Eficiência operacional
- Trade-offs arquiteturais

Essas áreas são referências, não etapas obrigatórias.

O coach deve explorar apenas tópicos que afetem materialmente o sistema sendo projetado.

---

## Cenários de Falha

Os modos Interview e Pressure podem introduzir cenários realistas de falha com base na arquitetura proposta pelo candidato.

Exemplos incluem:

- O tráfego aumenta significativamente
- Um nó do banco de dados falha
- Um message broker fica indisponível
- Uma mensagem é entregue mais de uma vez
- Um worker falha durante o processamento
- Uma região fica indisponível
- O cache falha
- Uma dependência externa sofre timeout
- Um cliente gera uma quantidade desproporcional de tráfego

Os cenários devem estar conectados à arquitetura do candidato em vez de serem introduzidos aleatoriamente.

---

## Avaliação

O candidato pode ser avaliado em diferentes dimensões.

### Requisitos

Capacidade de descobrir e esclarecer requisitos funcionais e não funcionais importantes.

### Arquitetura

Capacidade de criar uma arquitetura coerente com responsabilidades claras entre os componentes.

### Escalabilidade

Capacidade de identificar gargalos e propor estratégias adequadas de escalabilidade.

### Confiabilidade

Capacidade de raciocinar sobre falhas, retries, idempotência, recuperação e resiliência.

### Dados

Capacidade de escolher modelos de armazenamento adequados e raciocinar sobre padrões de acesso e consistência.

### Trade-offs

Capacidade de explicar decisões, reconhecer desvantagens e considerar alternativas.

### Comunicação

Capacidade de estruturar a discussão e explicar decisões arquiteturais com clareza.

### Sinais de Senioridade

Para candidatos Senior ou acima, a avaliação também considera:

- Pensamento orientado à produção
- Consciência operacional
- Consciência de custos
- Identificação de riscos
- Tomada de decisão sob ambiguidade
- Priorização
- Simplicidade
- Recuperação de falhas
- Evolução da arquitetura
- Questões entre diferentes times
- Reconhecimento de limitações

---

## Feedback

Ao final de uma sessão, o feedback se concentra em quatro áreas:

### Ponto Forte

O que o candidato fez bem.

### Gap

Qual área importante estava ausente ou fraca.

### Impacto

Por que esse gap importa em um sistema real ou em uma entrevista.

### Melhoria

O que o candidato deve praticar ou melhorar a seguir.

O feedback deve ser baseado em evidências observadas durante a sessão.

---

## Avaliação da Sessão

Quando apropriado, a qualidade da sessão pode ser classificada como:

- Abaixo do Esperado
- Em Desenvolvimento
- Atende às Expectativas
- Forte

O coach também pode identificar os sinais de senioridade demonstrados:

- Junior
- Mid-level
- Senior
- Staff-level

Os sinais de senioridade representam apenas o que foi demonstrado durante a sessão e não devem ser tratados como uma avaliação definitiva do nível profissional do candidato.

---

## Exemplos de Prompts

### Modo Coached

```text
Use o System Design Coach no modo Coached.

Quero praticar o design de uma plataforma de processamento de pagamentos
para uma entrevista de Senior Backend Engineer.

Tenho 45 minutos.
```

### Modo Interview

```text
Simule uma entrevista realista de System Design.

Cargo alvo: Senior Backend Engineer
Modo: Interview
Duração: 45 minutos

Escolha o problema para mim.
```

### Modo Pressure

```text
Use o modo Pressure para uma entrevista de System Design Senior/Staff.

Questione minhas decisões arquiteturais, premissas de escalabilidade,
tratamento de falhas, modelo de consistência e custos operacionais.

Não me dê pistas durante a entrevista.
```

### Prática Focada

```text
Use o modo Coached.

Quero praticar System Design especificamente em:
- idempotência
- transações distribuídas
- mensageria
- recuperação de falhas

Escolha um problema adequado para mim.
```

---

## Estrutura do Repositório

```text
system-design-coach/
├── SKILL.md
├── README.md
├── README.pt-br.md
└── CHANGELOG.md
```

### `SKILL.md`

Contém o comportamento e as instruções utilizadas pelo System Design Coach.

### `README.md`

Documentação do projeto em inglês.

### `README.pt-br.md`

Documentação do projeto em português.

### `CHANGELOG.md`

Registra as mudanças entre versões.

---

## Filosofia de Design

O System Design Coach propositalmente não é um gerador de arquiteturas.

Um candidato pode decorar que um sistema poderia utilizar:

```text
API Gateway
Redis
Kafka
PostgreSQL
Kubernetes
```

e ainda assim ter dificuldades em uma entrevista de System Design.

As perguntas importantes são:

```text
Por que esse componente é necessário?

Qual requisito ele resolve?

Qual trade-off ele introduz?

O que acontece quando ele falha?

O que acontece quando o tráfego cresce?

O que faria você mudar essa decisão?
```

O System Design Coach foi construído em torno dessas perguntas.

---

## Versionamento

Este projeto segue versionamento semântico.

```text
MAJOR.MINOR.PATCH
```

Exemplo:

```text
v1.0.0
```

- **MAJOR** — Mudanças incompatíveis de comportamento ou estrutura
- **MINOR** — Novas capacidades ou modos
- **PATCH** — Correções, esclarecimentos ou pequenas melhorias de comportamento

---

## Versão Atual

`v1.0.0`

Versão pública inicial do System Design Coach.

---

## Licença

Consulte a licença do repositório para informações sobre uso e distribuição.
