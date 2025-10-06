---
title: Visão geral e guia do usuário do Jornada Analyze Agent Skill
description: Guia abrangente para as habilidades do Journey Agent Analyze, permitindo que os usuários analisem jornadas de marketing, detectem problemas, descubram insights e otimizem o engajamento do cliente.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer,Leader
source-git-commit: 26b579471b591d3c436f4275d07303d297e0fbf8
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 0%

---


# Jornada Analyze Agent: visão geral e guia do usuário da habilidade

## Visão geral

O Journey Agent permitirá que os usuários do Journey Optimizer analisem e otimizem jornadas usando uma interface de linguagem natural. Com o Journey Agent, os profissionais podem identificar e resolver rapidamente conflitos de agendamento e/ou público-alvo, detectar pontos de abandono de usuários em uma jornada e fornecer insights ou recomendações. Ele capacita os profissionais a tomar decisões orientadas por dados, melhorar o envolvimento do cliente e simplificar a orquestração de jornadas.

Saiba mais e descubra o agente rapidamente nesta [visão geral](https://experienceleague.adobe.com/en/slides/journey-agent-overview).

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

### Principais casos de uso do Journey Agent Analyze

A habilidade do Journey Agent Analyze oferece uma variedade de funcionalidades que podem ser aproveitadas para otimizar esforços de marketing:

1. **Análise de Fallout de Jornada**

   - Identifique onde e por que os clientes caem durante uma jornada.
   - Detectar padrões no comportamento do cliente que levam à desvinculação.
   - Use insights para refinar o design da jornada e melhorar a retenção.

1. **Análise de sobreposição de público-alvo de Jornada**

   - Analise a sobreposição de público-alvo em várias jornadas.
   - Evite a fadiga do público-alvo causada pelo excesso de direcionamento.
   - Otimize a segmentação para garantir um engajamento equilibrado.

1. **Análise de Sobreposição de Agendamento de Jornada**

   - Detectar conflitos de tempo entre jornadas agendadas direcionadas para o mesmo público-alvo.
   - Evite a comunicação excessiva e melhore a eficiência da programação.
   - Maximize o impacto do público-alvo garantindo que as jornadas sejam executadas em momentos ideais.

1. **Insights operacionais**

   - Insights do Jornada com base em prompts - Surja insights operacionais sobre o jornada, ou seja, &quot;mostrar todas as jornadas ativas para mim&quot;.

Para cada uma dessas análises, o agente não apenas detecta problemas, mas também fornece **recomendações acionáveis para resolvê-los**.


## Habilidades dentro e fora do escopo

### **No Escopo**

Os seguintes recursos são compatíveis com o Journey Agent Analyze:

- **Consultas reativas**: permite que os usuários façam perguntas específicas sobre o desempenho da jornada, o uso do público-alvo e os conflitos de agendamento.
- **Integração com outros agentes**: colabora com a Audience Agent e a Data Insights Agent para uma análise mais profunda.
- **Estrutura de resposta do agente**: raciocínio (explique a lógica), resumo da análise (destaque os pontos principais), detalhes do problema (descreva o problema) e recomendação (proponha as próximas etapas).

### **Fora de escopo**

As seguintes funcionalidades não são suportadas no momento:

- **Criação de Jornada automatizada**
- **Detecção de anomalias em tempo real**
- **Sobreposição de canais**
- **Análise de entrada de Jornada**
- **Análise de problemas técnicos**
- **Análise de fadiga**

## Prompts de amostra / Prompts de exemplo

### Prompts comuns para a análise de Jornadas

Estes são exemplos de prompts valiosos que os usuários podem utilizar para explorar, monitorar e solucionar problemas de suas jornadas.

### Jornada perguntas sobre o ciclo de vida

- &quot;Quando o [Nome da Jornada] foi publicado?&quot;
- &quot;Quando o [Nome da Jornada] foi interrompido?&quot;
- &quot;Listar todas as jornadas atualmente no modo de teste&quot;

### Jornada perguntas sobre recursos

- &quot;Quantas jornadas ao vivo eu tenho?&quot;
- &quot;Forneça uma lista de todas as jornadas recorrentes agendadas e seus tempos de execução esperados.&quot;

### Insights de público-alvo e Jornada

- &quot;Quais públicos-alvo são usados em mais de X jornadas?&quot;
- &quot;Liste todas as jornadas usando o [nome do público-alvo].&quot;

### Análise de fallout

- &quot;Quero analisar o fallout por nó para a Campanha do jornada de 4 de julho.&quot;
- &quot;Execute uma análise de fallout para a Campanha do jornada de 4 de julho.&quot;
- &quot;O que é perda de perfil ao longo da Campanha de 4 de julho do jornada?&quot;
- &quot;Mostrar onde os usuários estão saindo na Campanha do jornada de 4 de julho.&quot;

### Prompts da Análise de Conflito

Use estes prompts para analisar possíveis conflitos entre jornadas, incluindo a programação e sobreposições de público-alvo:

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

### Solicitação de práticas recomendadas

Para maximizar a eficácia do Journey Agent Analyze, siga estas práticas recomendadas:

1. **Seja específico**: use prompts claros e concisos para obter insights direcionados. Por exemplo, em vez de perguntar &quot;Quais são minhas jornadas?&quot;, especifique &quot;Listar todas as jornadas criadas no último mês&quot;.
1. **Combinar insights**: integre insights do Audience Agent e do Data Insights Agent para obter uma visão holística do desempenho do jornada.
1. **Refinamento iterativo**: use o fallout e a análise de sobreposição para refinar iterativamente o design e o agendamento da jornada.

### Configurar práticas recomendadas

- **Definir objetivos claros**: antes de analisar jornadas, estabeleça metas claras (por exemplo, melhorar a retenção, aumentar as conversões).
- **Monitorar Regularmente**: agende revisões regulares do desempenho da jornada para identificar tendências e anomalias.
- **Otimizar segmentação**: certifique-se de que a segmentação de público esteja balanceada para evitar fadiga e maximizar o engajamento.

