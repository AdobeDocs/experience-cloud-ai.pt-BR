---
title: Ferramentas do Adobe Analytics no Adobe CX Enterprise MCP
description: Saiba quais ferramentas do Adobe Analytics estão disponíveis por meio do Adobe CX Enterprise MCP.
source-git-commit: df05761a8555950366fcaa201ce9c0fd47bb0802
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Ferramentas do Adobe Analytics no Adobe CX Enterprise MCP {#aa-mcp}

Você pode usar as ferramentas do Adobe Analytics para explorar conjuntos de relatórios, descobrir dimensões e métricas, executar relatórios e gerenciar componentes de análise selecionados de um cliente compatível com MCP. Essas ferramentas estão disponíveis por meio do [Adobe CX Enterprise MCP](overview.md) unificado, quando sua conta tiver a licença e as permissões necessárias da Adobe Analytics.

>[!AVAILABILITY]
>
>As ferramentas do Analytics estão disponíveis para clientes com uma licença da Adobe Analytics. O acesso é controlado pela permissão **Acesso ao MCP** no Adobe Admin Console. Leia as [Ferramentas de MCP do Access CX Enterprise](access.md) para obter mais informações.

## Principais recursos {#mcp-capabilities}

As ferramentas do Adobe Analytics oferecem suporte à descoberta de análises e aos workflows de relatórios do cliente MCP. Você pode:

- Descubra conjuntos de relatórios e inspecione como eles são configurados.
- Encontre dimensões, métricas, métricas calculadas, segmentos, intervalos de datas e projetos do Workspace.
- Execute relatórios classificados e de tendências com dimensões, métricas, intervalos de datas e filtros de segmento.
- Criar e atualizar componentes reutilizáveis selecionados, como segmentos e intervalos de datas.
- Gere insights a partir de dados do Adobe Analytics usando a linguagem natural.

>[!IMPORTANT]
>
>Algumas ferramentas do Adobe Analytics podem criar ou atualizar componentes de análise. Revise e valide todas as alterações iniciadas pelo MCP antes de confiar nelas.

## Cobertura da ferramenta {#mcp-tools}

| Área | O que você pode fazer |
| --- | --- |
| Conjuntos de relatórios | Descubra conjuntos de relatórios disponíveis para sua conta e inspecione os detalhes de configuração. |
| Componentes | Encontre e descreva dimensões, métricas, métricas calculadas, segmentos e intervalos de datas. |
| Relatório | Execute relatórios classificados e de tendências usando dimensões, métricas, intervalos de datas e filtros de segmento selecionados. |
| Segmentos e intervalos de datas | Crie e atualize segmentos reutilizáveis e intervalos de datas onde suas permissões de produto permitirem. |
| Projetos Workspace | Descubra e descreva projetos da Analysis Workspace. |

Para obter a lista atual completa de ferramentas, consulte a [referência de ferramenta do Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/reference){target="_blank"}.

## Exemplo de prompts {#mcp-use-cases}

| Meta | Exemplo de prompt |
| --- | --- |
| Descobrir conjuntos de relatórios | &quot;Listar os conjuntos de relatórios que posso acessar.&quot; |
| Localizar componentes | &quot;Encontre métricas relacionadas à receita.&quot; |
| Executar um relatório | &quot;Execute um relatório classificado para exibições de página por página nos últimos 7 dias.&quot; |
| Inspecionar um segmento | &quot;Descreva o segmento `[segment name]` e mostre-me sua definição.&quot; |
| Explorar projetos | &quot;Listar meus projetos do Analysis Workspace relacionados à aquisição.&quot; |

## Contexto e permissões do produto {#mcp-context}

Sua conta deve pertencer a um perfil de produto do Adobe Analytics que inclua o item de permissão **Acesso ao MCP**, concedido por um administrador de sistema ou de produto no Adobe Admin Console.

As permissões do produto ainda se aplicam. Sua conta deve ser capaz de visualizar os conjuntos de relatórios, componentes, relatórios e projetos que você consulta, e deve ter as permissões de produto apropriadas para operações de gravação, como criar ou atualizar componentes reutilizáveis.

## Mais informações {#mcp-more}

Para obter a referência completa da ferramenta e o guia de introdução, consulte a [documentação do Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/){target="_blank"}.