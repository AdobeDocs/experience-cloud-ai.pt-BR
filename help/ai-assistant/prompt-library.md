---
title: Biblioteca de prompts do assistente do AI
description: Saiba mais sobre os diferentes tipos de prompts e padrões de prompt que você pode usar ao consultar o Assistente de IA.
TQID: https://experienceleague.adobe.com/QICjh9cNBT3XeKObkXqSDEGQT26zpv86V36L0tqvSgo
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 813
ht-degree: 16%

---

# Biblioteca de prompts do assistente do AI

Leia este guia para obter os diferentes tipos de prompts que você pode usar no Assistente de IA.

## Audience Agent

As seções a seguir fornecem exemplos de prompts que você pode usar com o Audience Agent para explorar e analisar seus públicos. Isso inclui maneiras de investigar características do público-alvo, detectar públicos-alvo duplicados, recuperar tamanhos de público-alvo e monitorar alterações significativas no tamanho do público ao longo do tempo. Use esses prompts para obter insights mais profundos e manter a qualidade dos dados do público-alvo.

### Exploração de público-alvo de conversa

- &quot;Mostre-me campos para compradores ricos.&quot;
- &quot;Quais públicos-alvo não foram ativados ou usados em nenhuma campanha nos últimos 30 dias?&quot;
- &quot;Listar todos os públicos mapeados para novos destinos nos últimos três meses.&quot;

### Detectar públicos-alvo duplicados

- &quot;Tenho públicos-alvo com descrições idênticas ou semelhantes?&quot;
- &quot;Identifique públicos que tenham as mesmas regras, mas nomes diferentes.&quot;
- &quot;Mostre-me todos os públicos-alvo que têm as mesmas regras, mas destinos de ativação diferentes.&quot;

### Recuperar tamanho do público

- &quot;Qual é o tamanho atual do meu público-alvo &quot;Membros Gold-star na Califórnia_f153e1&quot;?&quot;
- &quot;Qual é meu maior público-alvo?&quot;

### Detectar alterações significativas no tamanho do público

- &quot;Quais públicos-alvo aumentaram de tamanho em mais de 20% na última semana?&quot;
- &quot;Quais públicos-alvo diminuíram em tamanho em mais de 15% no último mês?&quot;
- &quot;Qual é o meu público que cresce mais rápido?&quot;

## Data Insights Agent

Os prompts de exemplo a seguir podem ser usados com o Data Insights Agent para analisar seus dados, identificar tendências e descobrir insights acionáveis.

### Data visualization

- &quot;Show me profits in September.&quot;
- &quot;Trend orders in September.&quot;
- &quot;Show revenue by region in September.&quot;
- &quot;Share of revenue by product category.&quot;
- &quot;Orders by day of week, from January to May.&quot;
- &quot;Show orders by gender, from March to June.&quot;
- &quot;What is the profit across SKUs from February to May.&quot;
- &quot;Revenue by store name in September.&quot;
- &quot;What were my top 10 SKUs by profit in September?&quot;
- &quot;Proportion of purchases by month of year.&quot;
- &quot;Total profit in September.&quot;

## Journey Agent

The following example prompts can be used with the Journey Agent to help you analyze journey lifecycles, manage journey resources, gain insights into audience and journey relationships, and detect conflicts between journeys. Use these prompts to optimize your journey orchestration and resolve issues efficiently.

### Perguntas sobre o ciclo de vida da jornada

- &quot;When was {JOURNEY_NAME} published?&quot;
- &quot;When was {JOURNEY_NAME} stopped?&quot;
- &quot;List all journeys currently in test mode&quot;

### Perguntas sobre os recursos da jornada

- &quot;How many live journeys do I have?&quot;
- &quot;Give me a list of all scheduled recurring journeys and their expected run times.&quot;

### Insights de público-alvo e de jornada

- &quot;Which audiences are used in more than X journeys?&quot;
- &quot;List all journeys using the {AUDIENCE_NAME} audience.&quot;

### Prompts de análise de conflitos

Use estes prompts para analisar potenciais conflitos entre jornadas, incluindo sobreposições de agendamento e de público-alvo:

+++Select to view list

- &quot;Can you do a comprehensive analysis of conflicts for our journey {JOURNEY_NAME} with conflict type (scheduling/audience) information with live/running journeys?&quot;
- &quot;Please do a scheduling conflict analysis for journey {JOURNEY_NAME} with conflict type information.&quot;
- &quot;Faça uma análise de sobreposição de público-alvo para a jornada {JOURNEY_NAME} com informações de tipo de conflito.&quot;
- &quot;Há algum conflito de agendamento para a jornada {JOURNEY_NAME}?&quot;
- &quot;Mostrar conflitos de sobreposição de público-alvo para a jornada {JOURNEY_NAME}.&quot;
- &quot;Analisar todos os conflitos da jornada {JOURNEY_NAME} com outras jornadas ativas.&quot;
- &quot;Quais são os conflitos atuais para a jornada {JOURNEY_NAME}?&quot;
- &quot;Verifique se a jornada {JOURNEY_NAME} tem conflitos de público com outras jornadas.&quot;
- &quot;Verifique se há conflitos de agendamento envolvendo a jornada {JOURNEY_NAME}.&quot;
- &quot;Quero saber sobre todos os conflitos de jornada para {JOURNEY_NAME}.&quot;
- &quot;Algum jornada ao vivo entra em conflito com {JOURNEY_NAME} por agendamento ou público-alvo?&quot;
- &quot;Identifique tipos de conflito para a jornada {JOURNEY_NAME} em comparação com jornadas em execução.&quot;
- &quot;Mostrar públicos sobrepostos para a jornada {JOURNEY_NAME} e outras jornadas.&quot;
- &quot;Destaque as sobreposições de agendamento entre a jornada {JOURNEY_NAME} e as jornadas ativas.&quot;
- &quot;A jornada {JOURNEY_NAME} está em conflito com alguma outra jornada?&quot;
- &quot;Detecte e liste conflitos para {JOURNEY_NAME}.&quot;
- &quot;Relate todos os tipos de conflitos da jornada {JOURNEY_NAME}.&quot;
- &quot;Detalhamento de conflitos (agendamento e público-alvo) para {JOURNEY_NAME}.&quot;
- &quot;{JOURNEY_NAME} tem algum conflito que possa afetar o desempenho?&quot;
- &quot;Há algum conflito ativo afetando {JOURNEY_NAME}?&quot;
- &quot;Listar jornadas em conflito com {JOURNEY_NAME} por agenda ou público-alvo.&quot;
- &quot;A jornada {JOURNEY_NAME} acionou algum alerta de conflito?&quot;
- &quot;Encontre possíveis conflitos de público-alvo para a jornada {JOURNEY_NAME}.&quot;
- &quot;Analisar o risco de conflito para a jornada {JOURNEY_NAME}.&quot;
- &quot;Forneça diagnósticos de conflito para {JOURNEY_NAME}.&quot;

+++

## Agente de suporte ao produto

O Agente de suporte do produto ajuda a solucionar problemas, criar casos de suporte e rastrear o status dos tíquetes de suporte. Use os seguintes prompts de exemplo para obter assistência.

### Troubleshooting help

- &quot;Por que minha contagem de perfis é diferente no Painel de Uso da Licença e na home page do Experience Platform?&quot;
- &quot;Quais são as razões para uma jornada não ser acionada?&quot;
- &quot;Como o Adobe Experience Platform cria experiências em tempo real?&quot;
- &quot;Como você configura e usa alertas no Adobe Experience Platform?&quot;
- &quot;Qual é o limite para trabalhos de segmentação em lote na Ativação do Adobe Experience Platform?&quot;
- &quot;Qual é o limite médio de riqueza de perfil na Ativação do Adobe Experience Platform?&quot;

### Criação de caso de suporte

- &quot;Criar um tíquete de suporte.&quot;
- &quot;Você pode me ajudar a criar um tíquete de suporte?&quot;

### Rastrear progresso do caso

- &quot;Qual é a última novidade no meu caso E-12345?&quot;
- &quot;Qual é a atualização no ticket E-67890?&quot;

