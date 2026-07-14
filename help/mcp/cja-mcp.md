---
title: Ferramentas do Customer Journey Analytics no Adobe CX Co-worker Gateway
description: Saiba quais ferramentas do Adobe Customer Journey Analytics estão disponíveis por meio do Adobe CX Co-worker Gateway.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 3%

---


# Ferramentas do Customer Journey Analytics no Adobe CX Co-worker Gateway {#cja-mcp}

Use as ferramentas de produto do Customer Journey Analytics para explorar visualizações de dados, descobrir dimensões e métricas, executar relatórios e gerenciar componentes de análise selecionados de um cliente compatível com MCP. Essas ferramentas estão disponíveis por meio do [CX Co-worker Gateway](overview.md) quando sua conta tem a licença e as permissões necessárias da Customer Journey Analytics.

>[!AVAILABILITY]
>
>As ferramentas do Customer Journey Analytics estão disponíveis para clientes com uma licença da Customer Journey Analytics. O acesso é controlado pela permissão **Acesso ao MCP** no Adobe Admin Console. Consulte [Acessar as ferramentas do CX Co-worker Gateway](access.md).

## Principais recursos {#mcp-capabilities}

As ferramentas do Customer Journey Analytics oferecem suporte a workflows de análise controlados do cliente MCP. Você pode:

* Descubra visualizações de dados e inspecione como elas são configuradas.
* Encontre dimensões, métricas, métricas calculadas, segmentos, intervalos de datas, públicos-alvo e projetos.
* Execute relatórios classificados e de tendências com dimensões, métricas, intervalos de datas e filtros de segmento.
* Inspecione as definições de componentes e o uso de componentes.
* Criar ou atualizar componentes analíticos selecionados e projetos do espaço de trabalho.

>[!IMPORTANT]
>
>Ao contrário das ferramentas de produto do [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) e [Journey Optimizer](ajo-mcp.md) somente leitura, as ferramentas do Customer Journey Analytics incluem operações de gravação. Eles podem criar e atualizar segmentos, métricas calculadas, intervalos de datas, projetos e públicos-alvo. Revise e valide todas as alterações iniciadas pelo MCP antes de confiar nelas.

## Ferramentas disponíveis {#mcp-tools}

| Área | Ferramenta | Descrição |
| --- | --- | --- |
| Configuração e guias | `describeCja` | Retorna guias de referência para ferramentas, dimensões, métricas, segmentos, métricas calculadas e estruturas de projeto. |
| Configuração e guias | `setDefaultSessionDataViewId` | Configura a visualização de dados padrão em nível de sessão para chamadas de ferramenta subsequentes. |
| Descoberta | `findDimensions` | Localiza dimensões disponíveis, com suporte à pesquisa semântica. |
| Descoberta | `findMetrics` | Descobre métricas padrão e personalizadas, excluindo métricas calculadas. |
| Descoberta | `findCalculatedMetrics` | Procura métricas calculadas criadas pelo usuário e compartilhadas. |
| Descoberta | `findSegments` | Lista segmentos acessíveis ao usuário atual. |
| Descoberta | `findDateRanges` | Recupera componentes salvos do intervalo de datas. |
| Descoberta | `findDataViews` | Descobre visualizações de dados disponíveis. |
| Descoberta | `findProjects` | Localiza projetos do Workspace. |
| Descoberta | `findAudiences` | Lista os componentes de público disponíveis. |
| Relatórios e análises | `runReport` | Executa relatórios classificados com dimensões, métricas, intervalos de datas e filtros de segmento opcionais. |
| Relatórios e análises | `searchDimensionItems` | Recupera valores de dimensão necessários para relatórios de detalhamento. |
| Detalhes do componente | `describeDimension` | Mostra metadados detalhados de uma dimensão específica. |
| Detalhes do componente | `describeMetric` | Retorna metadados de métrica e detalhes de medição. |
| Detalhes do componente | `describeSegment` | Exibe as informações de definição e compatibilidade de um segmento. |
| Detalhes do componente | `describeCalculatedMetric` | Mostra a fórmula e as métricas base usadas. |
| Detalhes do componente | `describeProject` | Detalha a configuração de um projeto do Workspace. |
| Detalhes do componente | `describeAudience` | Retorna metadados de público-alvo e status de publicação. |
| Uso do componente | `listComponentUsage` | Classifica os componentes por frequência de uso. |
| Uso do componente | `listFrequentlyUsedWith` | Identifica componentes normalmente emparelhados. |
| Uso do componente | `listSimilarTo` | Localiza componentes alternativos atendendo a fins semelhantes. |
| Criar e atualizar | `upsertSegment` | Cria um novo segmento ou modifica um já existente. |
| Criar e atualizar | `upsertCalculatedMetric` | Cria uma nova métrica calculada ou modifica uma métrica existente. |
| Criar e atualizar | `createDateRange` | Cria um componente de intervalo de datas reutilizável. |
| Criar e atualizar | `upsertProject` | Cria um novo projeto do espaço de trabalho ou modifica um já existente. |
| Criar e atualizar | `upsertAudience` | Cria uma nova definição de público-alvo ou modifica uma já existente. |

## Exemplo de prompts {#mcp-use-cases}

| Meta | Exemplo de prompt |
| --- | --- |
| Listar visualizações de dados | &quot;Listar as visualizações de dados disponíveis para mim no Customer Journey Analytics.&quot; |
| Descobrir componentes | &quot;Localizar métricas relacionadas à receita na exibição de dados `[data view name]`.&quot; |
| Executar um relatório | &quot;Execute um relatório de tendências de pedidos por mês do último trimestre.&quot; |
| Analisar uma métrica | &quot;Mostre-me os 10 principais canais de marketing por visitas, divididos por tipo de dispositivo.&quot; |
| Inspecionar um componente | &quot;Descreva o segmento `[segment name]` e mostre-me sua definição.&quot; |
| Auditoria de uso | &quot;Quais dimensões são usadas com mais frequência em meus projetos?&quot; |
| Criar um segmento | &quot;Crie um segmento para usuários que visualizaram a página de preços nos últimos 30 dias.&quot; |

## Contexto e permissões do produto {#mcp-context}

Sua conta deve pertencer a um perfil de produto do Customer Journey Analytics que inclua o item de permissão **Acesso ao MCP**, concedido por um administrador de sistema ou de produto no Adobe Admin Console.

As permissões do produto ainda se aplicam. Sua conta deve ser capaz de visualizar as visualizações de dados, componentes, projetos e públicos-alvo que você consulta, e deve ter as permissões de produto apropriadas para operações de gravação, como criar ou atualizar segmentos, métricas calculadas, intervalos de datas, projetos ou públicos-alvo.

## Assista-o em ação {#mcp-videos}

**Visão geral**

>[!VIDEO](https://video.tv.adobe.com/v/3486319/?captions=por_br&learn=on&enablevpops)

**Em ação**

>[!VIDEO](https://video.tv.adobe.com/v/3486330/?captions=por_br&learn=on&enablevpops)

## Mais informações {#mcp-more}

Para obter a referência completa da ferramenta e o guia de introdução, consulte a [documentação do Customer Journey Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/cja/){target="_blank"}.