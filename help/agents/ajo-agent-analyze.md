---
title: Visão geral e guia do usuário do Jornada Analyze Agent Skill
description: Guia completo para a habilidade de análise do Journey Agent, que permite aos usuários analisar jornadas de marketing, detectar problemas, descobrir insights e otimizar o engajamento do cliente.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer,Leader
source-git-commit: 26b579471b591d3c436f4275d07303d297e0fbf8
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 38%

---


# Jornada Analyze Agent: visão geral e guia do usuário da habilidade

## Visão geral

O Journey Agent permitirá que os usuários do Journey Optimizer analisem e otimizem jornadas usando uma interface de linguagem natural. Com o Journey Agent, os profissionais podem identificar e resolver rapidamente conflitos de agendamento e/ou público-alvo, detectar pontos de abandono de usuários em uma jornada e fornecer insights ou recomendações. Ele capacita profissionais de marketing a tomar decisões baseadas em dados, melhorar o engajamento do cliente e simplificar a orquestração da jornada.

Saiba mais e descubra o agente rapidamente nesta [visão geral](https://experienceleague.adobe.com/pt-br/slides/journey-agent-overview).

>[!AVAILABILITY]
>
>O Journey Agent está disponível para todos os clientes que têm acesso ao AI Assistant. No entanto, você precisará das seguintes permissões para usar totalmente os recursos do Journey Agent:
>
>**Exibir Jornadas**: essa permissão permite exibir insights sobre a jornada diretamente no Assistente de IA.
>
>**Gerenciar Jornadas**: a permissão Para permite que você crie novas jornadas diretamente no Assistente de IA.
>
>**Exibir segmentos**: essa permissão permite que você visualize insights sobre os públicos-alvo diretamente no Assistente de IA.
>
>**Gerenciar segmentos**: a permissão Para permite que você crie novos públicos diretamente no Assistente de IA.

![Amostra para o AJO Agent](./images/ajo-agent/ajo-agent-sample.png)

## Casos de uso

### Principais casos de uso da análise do Journey Agent

A habilidade de análise do Journey Agent oferece uma variedade de funcionalidades que podem ser aproveitadas para otimizar os esforços de marketing:

1. **Análise de fallout da jornada**

   - Identifique onde e por que os clientes desistem durante uma jornada.
   - Detecte padrões no comportamento do cliente que levam ao desengajamento.
   - Use insights para refinar o design da jornada e melhorar a retenção.

1. **Análise de sobreposição de público-alvo da jornada**

   - Analise a sobreposição de público-alvo em diversas jornadas.
   - Evite a fadiga de público-alvo causada pelo excesso de direcionamento.
   - Otimize a segmentação para garantir um engajamento equilibrado.

1. **Análise de sobreposição de cronograma da jornada**

   - Detecte conflitos de data entre jornadas programadas que direcionam o mesmo público-alvo.
   - Evite o excesso de comunicação e melhore a eficiência do agendamento.
   - Maximize o impacto no público-alvo garantindo que as jornadas ocorram nos momentos ideais.

1. **Insights operacionais**

   - Insights do Jornada com base em prompts - Surja insights operacionais sobre o jornada, ou seja, &quot;mostrar todas as jornadas ativas para mim&quot;.

Para cada uma dessas análises, o agente não apenas detecta problemas, mas também fornece **recomendações acionáveis para resolvê-los**.


## Habilidades dentro e fora do escopo

### **Dentro do escopo**

Os seguintes recursos são compatíveis com a análise do Journey Agent:

- **Consultas reativas**: permite que usuários façam perguntas específicas sobre o desempenho da jornada, a utilização do público-alvo e conflitos de agendamento.
- **Integração com outros agentes**: colabora com o Audience Agent e o Data Insights Agent para realizar análises mais aprofundadas.
- **Estrutura de resposta do agente**: raciocínio (explique a lógica), resumo da análise (destaque os pontos principais), detalhes do problema (descreva o problema) e recomendação (proponha as próximas etapas).

### **Fora do escopo**

As seguintes funcionalidades não são compatíveis no momento:

- **Criação automatizada de jornadas**
- **Detecção de anomalias em tempo real**
- **Sobreposição de canais**
- **Análise de entrada da jornada**
- **Análise de problemas técnicos**
- **Análise de fadiga**

## Prompts de amostra e prompts de exemplo

### Prompts comuns para a análise da jornada

Estes são alguns exemplos de prompts valiosos que os usuários podem aproveitar para explorar, monitorar e solucionar problemas em suas jornadas.

### Perguntas sobre o ciclo de vida da jornada

- &quot;Quando o [Nome da Jornada] foi publicado?&quot;
- &quot;Quando o [Nome da Jornada] foi interrompido?&quot;
- &quot;Listar todas as jornadas atualmente no modo de teste&quot;

### Perguntas sobre os recursos da jornada

- &quot;Quantas jornadas ao vivo eu tenho?&quot;
- &quot;Forneça uma lista de todas as jornadas recorrentes agendadas e seus tempos de execução esperados.&quot;

### Insights de público-alvo e de jornada

- &quot;Quais públicos-alvo são usados em mais de X jornadas?&quot;
- &quot;Liste todas as jornadas usando o [nome do público-alvo].&quot;

### Análise de fallout

- &quot;Quero analisar o fallout por nó para a Campanha do jornada de 4 de julho.&quot;
- &quot;Execute uma análise de fallout para a Campanha do jornada de 4 de julho.&quot;
- &quot;O que é perda de perfil ao longo da Campanha de 4 de julho do jornada?&quot;
- &quot;Mostrar onde os usuários estão saindo na Campanha do jornada de 4 de julho.&quot;

### Prompts de análise de conflitos

Use estes prompts para analisar potenciais conflitos entre jornadas, incluindo sobreposições de agendamento e de público-alvo:

- &quot;Você pode fazer uma análise abrangente dos conflitos da sua jornada [Nome da Jornada] com informações de tipo de conflito (agendamento/público) com jornadas ativas/em execução?&quot;
- &quot;Faça uma análise de conflito de agendamento para a jornada [Nome da Jornada] com informações de tipo de conflito.&quot;
- &quot;Faça uma análise de sobreposição de público-alvo para a jornada [Nome da Jornada] com informações de tipo de conflito.&quot;
- &quot;Há algum conflito de agendamento para a jornada [Nome da Jornada]?&quot;
- &quot;Mostrar conflitos de sobreposição de público-alvo para a jornada [Nome da Jornada].&quot;
- &quot;Analisar todos os conflitos da jornada [Nome da Jornada] com outras jornadas ativas.&quot;
- &quot;Quais são os conflitos atuais para a jornada [Nome da Jornada]?&quot;
- &quot;Verifique se o [Nome da Jornada] da jornada tem conflitos de público com outras jornadas.&quot;
- &quot;Verifique se há conflitos de agendamento envolvendo o [Nome da Jornada] da jornada.&quot;
- &quot;Quero saber sobre todos os conflitos de jornada para [Nome da Jornada].&quot;
- &quot;Há algum conflito de jornadas ao vivo com [Nome da Jornada] por agenda ou público-alvo?&quot;
- &quot;Identifique tipos de conflito para a jornada [Nome da Jornada] em comparação à execução de jornadas.&quot;
- &quot;Mostrar públicos sobrepostos para a jornada [Nome da Jornada] e outras jornadas.&quot;
- &quot;Destaque as sobreposições de agendamento entre a jornada [Nome da Jornada] e jornadas ativas.&quot;
- &quot;A jornada [Nome da Jornada] está em conflito com alguma outra jornada?&quot;
- &quot;Detecte e liste conflitos para [Nome da Jornada].&quot;
- &quot;Relate todos os tipos de conflitos da jornada [Nome da Jornada].&quot;
- &quot;Detalhamento de conflitos (agendamento e público-alvo) para [Nome da Jornada].&quot;
- &quot;O [Nome da Jornada] possui conflitos que podem afetar o desempenho?&quot;
- &quot;Há algum conflito ativo afetando [Nome da Jornada]?&quot;
- &quot;Listar jornadas em conflito com [Nome da Jornada] por agenda ou público-alvo.&quot;
- &quot;A jornada [Nome da Jornada] acionou alertas de conflito?&quot;
- &quot;Localize possíveis conflitos de público-alvo para a jornada [Nome da Jornada].&quot;
- &quot;Analisar o risco de conflito da jornada [Nome da Jornada].&quot;
- &quot;Forneça diagnósticos de conflito para [Nome da Jornada].&quot;

## Práticas recomendadas

### Práticas recomendadas de criação de prompts

Para maximizar a eficácia da análise do Journey Agent, siga estas práticas recomendadas:

1. **Seja específico(a)**: use prompts claros e concisos para obter insights direcionados. Por exemplo, em vez de perguntar &quot;Quais são minhas jornadas?&quot;, especifique &quot;Listar todas as jornadas criadas no último mês&quot;.
1. **Combine insights**: integre insights do Audience Agent e do Data Insights Agent para obter uma visão integral do desempenho da jornada.
1. **Refinamento iterativo**: use as análises de fallout e de sobreposição para refinar continuamente o design e o agendamento da jornada.

### Práticas recomendadas de configuração

- **Defina objetivos claros**: antes de analisar as jornadas, estabeleça metas claras (por exemplo: melhorar a retenção, aumentar as conversões).
- **Monitore regularmente**: agende revisões regulares do desempenho da jornada para identificar tendências e anomalias.
- **Otimize a segmentação**: mantenha uma segmentação de público-alvo equilibrada para evitar fadiga e maximizar o engajamento.

