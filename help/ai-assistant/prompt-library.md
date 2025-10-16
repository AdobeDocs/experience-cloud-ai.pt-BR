---
title: Biblioteca de prompts do assistente do AI
description: Saiba mais sobre os diferentes tipos de prompts e padrões de prompt que você pode usar ao consultar o Assistente de IA.
source-git-commit: 4bb6da3fe1abee98446df62c94730274e0931493
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 3%

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

### Visualização de dados

- &quot;Mostre-me lucros em setembro.&quot;
- &quot;Pedidos em tendência em setembro.&quot;
- &quot;Mostre a receita por região em setembro.&quot;
- &quot;Participação da receita por categoria de produto.&quot;
- &quot;Pedidos por dia da semana, de janeiro a maio.&quot;
- &quot;Mostre pedidos por gênero, de março a junho.&quot;
- &quot;Qual é o lucro em SKUs de fevereiro a maio?&quot;
- &quot;Receita por nome de loja em setembro.&quot;
- &quot;Quais foram meus 10 SKUs principais por lucro em setembro?&quot;
- &quot;Proporção de compras por mês do ano.&quot;
- &quot;Lucro total em setembro.&quot;

## Journey Agent

Os exemplos de prompts a seguir podem ser usados com o Journey Agent para ajudar você a analisar ciclos de vida de jornadas, gerenciar recursos de jornadas, obter insights sobre relacionamentos de público-alvo e jornada e detectar conflitos entre jornadas. Use essas instruções para otimizar a orquestração de jornadas e resolver problemas com eficiência.

### Perguntas sobre o ciclo de vida da jornada

- &quot;Quando o {JOURNEY_NAME} foi publicado?&quot;
- &quot;Quando {JOURNEY_NAME} foi interrompido?&quot;
- &quot;Listar todas as jornadas atualmente no modo de teste&quot;

### Perguntas sobre os recursos da jornada

- &quot;Quantas jornadas ao vivo eu tenho?&quot;
- &quot;Forneça uma lista de todas as jornadas recorrentes agendadas e seus tempos de execução esperados.&quot;

### Insights de público-alvo e de jornada

- &quot;Quais públicos-alvo são usados em mais de X jornadas?&quot;
- &quot;Liste todas as jornadas usando o público-alvo {AUDIENCE_NAME}.&quot;

### Prompts de análise de conflitos

Use estes prompts para analisar potenciais conflitos entre jornadas, incluindo sobreposições de agendamento e de público-alvo:

+++Selecione para exibir a lista

- &quot;Você pode fazer uma análise abrangente dos conflitos para nossa jornada {JOURNEY_NAME} com informações de tipo de conflito (agendamento/público-alvo) com jornadas ativas/em execução?&quot;
- &quot;Faça uma análise de conflito de agendamento para a jornada {JOURNEY_NAME} com informações de tipo de conflito.&quot;
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

### Ajuda para solução de problemas

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

