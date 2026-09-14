# Interview Coach

Interview Coach é uma skill de IA criada para ajudar desenvolvedores seniores a se preparar para entrevistas técnicas e comportamentais.

Ela avalia os requisitos da vaga em relação à experiência real do candidato, identifica riscos de preparação e gaps de conhecimento, prioriza o que deve ser estudado e oferece suporte para simulações de entrevista nos modos guiado e realista.

## O que a skill faz

O Interview Coach pode ajudar você a:

- Analisar uma vaga antes da entrevista
- Comparar os requisitos da vaga com sua experiência
- Identificar pontos fortes, gaps técnicos e áreas desconhecidas
- Priorizar a preparação com base no impacto para a entrevista
- Criar um backlog de preparação
- Praticar perguntas técnicas
- Praticar perguntas comportamentais utilizando STAR
- Melhorar respostas técnicas e comportamentais
- Realizar entrevistas simuladas com feedback
- Realizar entrevistas simuladas em modo realista
- Avaliar o nível de preparação para uma entrevista
- Utilizar projetos públicos do GitHub como evidência técnica complementar

## Modos de operação

### Preparation Mode

Utilize este modo antes de uma entrevista.

O coach realiza o seguinte fluxo:

```text
Requisitos da vaga
        ↓
Experiência do candidato
        ↓
Avaliação dos requisitos
        ↓
Pontos fortes / Riscos / Gaps
        ↓
Prioridades de preparação
        ↓
Backlog de preparação
```

Os requisitos técnicos são classificados como:

- `Strong Match`
- `Partial Match`
- `Gap`
- `Unknown`

As prioridades de preparação são classificadas como:

- `High`
- `Medium`
- `Low`

Quando houver evidência suficiente, o fit geral com a vaga pode ser classificado como:

- `Strong Fit`
- `Moderate Fit`
- `Low Fit`
- `Insufficient Evidence`

### Mock Interview Mode

O Mock Interview Mode possui dois estilos de simulação.

#### Coached Mock

O coach faz uma pergunta por vez, avalia a resposta, fornece feedback e continua a entrevista.

Esse modo é recomendado quando o objetivo é aprender e melhorar durante a simulação.

#### Realistic Mock

O coach se comporta de forma mais próxima a um entrevistador real.

Durante a simulação, ele não fornece:

- Dicas
- Correções
- Respostas sugeridas
- Feedback

A avaliação é apresentada somente depois que a entrevista simulada termina.

## Entrevistas técnicas

Respostas técnicas podem ser avaliadas com base em:

### Conhecimento

- Correção técnica
- Profundidade

### Engineering Judgment

- Justificativa
- Trade-offs

### Production Readiness

- Escalabilidade
- Segurança
- Observabilidade
- Monitoramento
- Custo
- Comportamento em cenários de alto volume

O objetivo não é apenas verificar se uma resposta está tecnicamente correta, mas também se ela demonstra capacidade de tomada de decisão compatível com um engenheiro sênior.

## Entrevistas comportamentais

A preparação comportamental utiliza o framework STAR:

```text
Situation
Task
Action
Result
```

O coach também procura sinais de senioridade como:

- Ownership
- Decision making
- Trade-offs
- Impact

O Interview Coach nunca inventa experiências, responsabilidades, decisões, resultados ou métricas do candidato.

## Contexto do candidato

A skill pode utilizar informações disponíveis sobre o candidato, como:

- Currículo ou resume
- Experiência profissional
- Projetos
- Tecnologias
- Respostas anteriores
- Contexto da conversa
- Perfil público do GitHub

Ausência de informação não é automaticamente considerada um gap.

Quando não houver evidência suficiente para avaliar um requisito, ele é classificado como `Unknown`.

## Análise do GitHub

Quando um perfil público do GitHub for fornecido, o Interview Coach pode utilizar os repositórios como evidência complementar da experiência técnica do candidato.

A análise pode considerar aspectos como:

- Linguagens
- Frameworks
- Arquitetura
- Testes
- Documentação
- CI/CD
- Infrastructure as Code
- Práticas de engenharia

O GitHub é tratado como evidência complementar e não como uma representação completa da experiência profissional do candidato.

## Exemplo — Preparação para entrevista

```text
Use Interview Coach.

Tenho uma entrevista para Senior Backend Engineer amanhã.

Esta é a descrição da vaga:

[cole a descrição da vaga]

Este é meu currículo:

[cole seu currículo]

Analise meu fit, identifique os gaps de maior risco
e crie um backlog de preparação.
```

## Exemplo — Coached Mock

```text
Inicie uma Coached Mock Interview para uma vaga de Senior Backend Engineer.

Foque em Java, Spring Boot, Kafka, PostgreSQL,
sistemas distribuídos e AWS.

Faça uma pergunta por vez.
```

## Exemplo — Realistic Mock

```text
Inicie uma Realistic Mock Interview para uma vaga de Senior Backend Engineer.

Não forneça dicas ou feedback durante a entrevista.

Apresente a avaliação completa somente depois que a entrevista terminar.
```

## Exemplo — Preparação rápida

```text
Tenho uma entrevista para Senior Backend Engineer em 30 minutos.

Me prepare para Java, Spring Boot, microservices,
Kafka, PostgreSQL e AWS.

Priorize somente os tópicos de maior risco.
```

## Definição da skill

O comportamento da IA e as regras de avaliação estão definidos em:

`SKILL.md`

## Idioma

A definição oficial da skill é escrita em inglês, mas o Interview Coach pode interagir com o candidato no idioma de sua preferência.

Para entrevistas internacionais, o candidato pode solicitar explicitamente que a simulação seja realizada em inglês ou no idioma esperado durante a entrevista.

## Princípios de design

O Interview Coach segue alguns princípios centrais:

- Evidências acima de suposições
- `Unknown` não significa automaticamente `Gap`
- Priorizar em vez de tentar estudar tudo
- Avaliar julgamento de engenharia e não apenas conhecimento memorizado
- Nunca fabricar experiências do candidato
- Preservar o comportamento realista durante uma `Realistic Mock`
