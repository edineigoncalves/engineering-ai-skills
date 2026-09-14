# Skill Reviewer

Skill Reviewer é uma skill de IA criada para revisar outras skills de IA antes de publicação ou versionamento.

Ela avalia definições de skills de forma semelhante a um code review, identificando problemas estruturais, instruções ambíguas, regras conflitantes, riscos de manutenção, regressões e bloqueadores de release.

O objetivo é melhorar a qualidade da skill sem redesenhar ou reescrever automaticamente o comportamento original.

## O que a skill faz

O Skill Reviewer pode ajudar você a:

- Revisar um `SKILL.md`
- Validar uma skill antes de publicá-la
- Preparar uma skill para uma nova release
- Identificar instruções contraditórias ou ambíguas
- Detectar regras duplicadas ou desnecessárias
- Avaliar consistência de workflows
- Identificar problemas de manutenção
- Revisar constraints e edge cases
- Comparar duas versões de uma skill
- Detectar possíveis regressões
- Avaliar readiness para release
- Priorizar correções obrigatórias antes de melhorias opcionais

## Fluxo principal de revisão

O reviewer segue este processo geral:

```text
COLLECT
   ↓
Entender o propósito da skill
Entender o estágio atual
Identificar arquivos e contexto disponíveis

   ↓

ANALYZE
   ↓
Estrutura
Instruções
Workflows
Consistência
Constraints
Ambiguidades
Duplicações
Conflitos
Manutenibilidade

   ↓

CLASSIFY
   ↓
Critical
Important
Improvement

   ↓

OUTPUT
   ↓
Review Summary
Findings
Release Status
Next Steps
```

## Filosofia de revisão

O Skill Reviewer segue um princípio simples:

> Revisar antes de reescrever.

Por padrão, ele não reescreve automaticamente a skill.

Em vez disso, ele:

1. Entende a intenção original.
2. Identifica problemas específicos.
3. Classifica cada finding por severidade.
4. Explica o impacto.
5. Recomenda uma mudança específica.
6. Reescreve somente quando solicitado explicitamente.

O reviewer também evita transformar preferências pessoais de estilo em problemas funcionais.

Ele não deve adicionar novas funcionalidades apenas porque seriam possíveis ou interessantes.

## Níveis de severidade

Cada finding é classificado como:

### `Critical`

Utilizado para problemas que podem quebrar ou alterar significativamente o comportamento da skill.

Exemplos:

- Instruções contraditórias
- Regras que impedem a execução correta
- Definições de comportamento conflitantes
- Problemas que geram resultados significativamente diferentes do propósito da skill

### `Important`

Utilizado para problemas relevantes que normalmente devem ser resolvidos antes da release.

Exemplos:

- Ambiguidade significativa
- Workflows incompletos
- Regras importantes sem definição suficiente
- Duplicações que podem gerar inconsistências futuras

### `Improvement`

Utilizado para melhorias não bloqueantes.

Exemplos:

- Melhor clareza
- Melhor organização
- Melhorias de nomenclatura
- Simplificação
- Melhorias de documentação
- Sugestões de manutenibilidade

Preferências puramente estilísticas não devem ser classificadas como `Critical` ou `Important`.

## Critérios de revisão

O reviewer avalia áreas como:

### Purpose

- O objetivo está claro?
- O escopo está definido?
- O comportamento está alinhado ao propósito?

### Triggering

- Está claro quando a skill deve ser utilizada?
- Ela pode ser acionada incorretamente?
- Existem cenários importantes de uso que não estão cobertos?

### Instructions

- As instruções são claras e executáveis?
- Existem regras vagas?
- Existem contradições?

### Workflow

- O workflow está completo?
- Existem etapas ausentes ou redundantes?
- Modos ou fluxos diferentes estão claramente definidos?

### Consistency

- Os conceitos são utilizados de forma consistente?
- As classificações mantêm o mesmo significado?
- Alguma seção contradiz outra?

### Constraints

- Os limites da skill estão claros?
- Comportamentos proibidos estão definidos quando necessário?
- As constraints estão alinhadas ao propósito da skill?

### Edge Cases

- Situações excepcionais importantes estão cobertas?
- Informações ausentes são tratadas corretamente?
- O comportamento está definido quando o contexto é insuficiente?

### Maintainability

- Existem regras duplicadas?
- A skill pode evoluir sem gerar inconsistências facilmente?
- As seções possuem responsabilidades claras?
- Existe complexidade desnecessária?

### Release Readiness

- Existem findings `Critical`?
- Existem findings `Important`?
- O comportamento principal está suficientemente definido?
- Existem regressões que impedem a release?

## Comparação entre versões

Quando duas versões de uma skill são fornecidas, o Skill Reviewer pode comparar e identificar:

- Comportamento adicionado
- Comportamento removido
- Comportamento alterado
- Constraints modificadas
- Possíveis regressões
- Mudanças somente de documentação

Para mudanças funcionais relevantes, ele também pode descrever:

- Comportamento anterior
- Novo comportamento
- Impacto
- Risco de regressão

Uma versão mais nova não é automaticamente considerada melhor.

## Saída da revisão

Uma revisão pode conter:

### Review Summary

Uma avaliação resumida da qualidade geral e dos principais riscos.

### Findings

Cada finding pode conter:

- Severity
- Area
- Issue
- Evidence
- Impact
- Recommendation

Exemplo:

```text
Severity: Important

Area:
Workflow

Issue:
A skill define dois modos de execução, mas não especifica
qual comportamento deve ser utilizado quando o usuário
não seleciona nenhum deles.

Evidence:
A seção Operating Modes define Mode A e Mode B,
mas não existe comportamento padrão.

Impact:
Execuções diferentes podem selecionar modos diferentes.

Recommendation:
Definir um modo padrão ou exigir que o usuário selecione um.
```

### Release Status

O Skill Reviewer utiliza quatro estados de release.

```text
Existe finding Critical?
        ↓ sim
      Blocked

        não
        ↓
Existe finding Important?
        ↓ sim
  Needs Changes

        não
        ↓
Existe finding Improvement?
        ↓ sim
Ready with Improvements

        não
        ↓
      Ready
```

#### `Ready`

Não existem findings relevantes pendentes e o comportamento principal está suficientemente definido.

#### `Ready with Improvements`

Existem apenas findings não bloqueantes classificados como `Improvement`.

#### `Needs Changes`

Existe pelo menos um problema `Important` que deve ser resolvido antes da release.

#### `Blocked`

Existe pelo menos um problema `Critical`.

## Exemplo — Revisar uma skill

```text
Use Skill Reviewer.

Revise este SKILL.md antes de eu publicar a versão 1.0.0.

Identifique problemas estruturais, contradições,
ambiguidades e bloqueadores de release.

Não reescreva a skill ainda.

[cole o SKILL.md]
```

## Exemplo — Release Readiness

```text
Revise esta skill e diga se ela está pronta para a v1.0.0.

Use os níveis de severidade e o release status definidos.

Reporte somente findings que possuam evidência na skill.
```

## Exemplo — Comparar versões

```text
Compare estas duas versões da minha skill.

Identifique:

- comportamento adicionado
- comportamento removido
- comportamento alterado
- regressões
- mudanças apenas de documentação

Versão 1:
[cole a versão]

Versão 2:
[cole a versão]
```

## Exemplo — Revisar antes de reescrever

```text
Revise esta skill primeiro.

Não reescreva nada ainda.

Para cada problema, informe:

- Severity
- Area
- Issue
- Evidence
- Impact
- Recommendation
```

## Definição da skill

O comportamento da IA e as regras de revisão estão definidos em:

`SKILL.md`

## Princípios de design

O Skill Reviewer segue alguns princípios centrais:

- Revisar antes de reescrever
- Evidências acima de suposições
- Preservar o propósito original da skill
- Separar problemas funcionais de preferências estilísticas
- Não inventar problemas
- Não adicionar funcionalidades automaticamente
- Tornar decisões de release determinísticas
- Diferenciar mudanças funcionais de mudanças editoriais
- Priorizar bloqueadores antes de melhorias opcionais

## Idioma

A definição canônica da skill é escrita em inglês.

O reviewer pode interagir com o usuário no idioma de sua preferência, a menos que outro idioma seja solicitado explicitamente.
