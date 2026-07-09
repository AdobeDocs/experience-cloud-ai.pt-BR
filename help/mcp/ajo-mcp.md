---
title: Ferramentas Adobe Journey Optimizer no CX Enterprise MCP
description: Saiba quais ferramentas do Adobe Journey Optimizer estão disponíveis por meio do CX Enterprise MCP.
source-git-commit: 6c73b4d2e452a82597565d71279df2dba605a977
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 3%

---

# Ferramentas Adobe Journey Optimizer no CX Enterprise MCP {#ajo-mcp}

Use as ferramentas de produto do Adobe Journey Optimizer para inspecionar campanhas e configurações de canal de um cliente compatível com MCP. Essas ferramentas estão disponíveis por meio do [CX Enterprise MCP](overview.md) quando sua organização está habilitada e sua conta de usuário tem as permissões necessárias do Journey Optimizer.

>[!AVAILABILITY]
>
>As ferramentas do produto Journey Optimizer estão no Beta. O acesso é apenas por convite e requer a habilitação da organização da Adobe. Consulte [Acessar ferramentas do CX Enterprise MCP](access.md).

## Principais recursos {#mcp-capabilities}

As ferramentas do Journey Optimizer fornecem uma superfície somente leitura para análise de configuração de campanha e canal. Você pode:

- Listar campanhas do Journey Optimizer e filtrar por status.
- Recupere detalhes da campanha, incluindo o direcionamento, a programação, o canal e os metadados de configuração de conteúdo.
- Listar configurações de canal para canais de email, SMS, push e WhatsApp.
- Analise a configuração da campanha e do canal em linguagem natural, sem navegar pelas telas do produto.

>[!IMPORTANT]
>
>Todas as ferramentas do Journey Optimizer na Beta atual são somente leitura. Não há suporte para criar, atualizar, excluir, iniciar, parar ou publicar campanhas.

## Ferramentas disponíveis {#mcp-tools}

| Ferramenta | Descrição |
| --- | --- |
| `ajo_campaign_list` | Navegue pelas campanhas de marketing do Journey Optimizer. Suporta filtragem por status, como `DRAFT`, `LIVE`, `STOPPED` e `COMPLETED`. |
| `ajo_campaign_get` | Busque detalhes e a configuração de uma campanha específica por ID, incluindo o direcionamento de público, a programação, o canal e os metadados de configurações de conteúdo. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | Exibir predefinições de superfície e de marca para email, SMS, push ou [!DNL WhatsApp] canais. |

## Exemplo de prompts {#mcp-use-cases}

| Meta | Exemplo de prompt |
| --- | --- |
| Visão geral da campanha | &quot;Mostre-me todas as minhas campanhas do Journey Optimizer.&quot; |
| Auditoria de status | &quot;Quais campanhas estão ativas no momento?&quot; |
| Detalhes da campanha | &quot;Obtenha os detalhes completos da campanha `[campaign ID]`.&quot; |
| Público-alvo e direcionamento | &quot;Qual público-alvo é direcionado na campanha `[campaign ID]`?&quot; |
| Agendamento e tempo | &quot;Quando a campanha `[campaign ID]` está agendada para execução?&quot; |
| Solução de problemas | &quot;Revise a configuração da campanha `[campaign ID]` e sinalize possíveis problemas.&quot; |
| Configuração de canais | &quot;Quais configurações de canal de email estão disponíveis?&quot; |
| Auditoria de canal | &quot;Quais configurações de canal estão ausentes ou incompletas?&quot; |

## Contexto e permissões do produto {#mcp-context}

Sua conta de usuário deve ter permissão para exibir as campanhas do Journey Optimizer e as configurações de canal que você consulta. O MCP não ignora permissões de produto.

Se sua organização usar várias sandboxes, especifique a sandbox ou o contexto de ambiente no prompt quando precisar de resultados de uma sandbox específica.

## Limitações conhecidas {#mcp-limitations}

| Limitação | Descrição | Solução alternativa |
| --- | --- | --- |
| Superfície somente leitura | As ferramentas do Journey Optimizer só expõem as operações de recuperação. Não é possível criar, atualizar, excluir, iniciar, parar ou publicar campanhas. | Use a interface do usuário do Journey Optimizer ou as APIs para operações de gravação. |
| Sem envolvimento ou métricas de desempenho | As ferramentas não retornam dados de relatório como impressões, taxas de click-through, conversões ou estatísticas de delivery. | Use os relatórios do Journey Optimizer, as ferramentas do Customer Journey Analytics ou as ferramentas do Adobe Analytics para obter métricas de desempenho. |
| A paginação de lista de campanhas é limitada | A listagem de campanha retorna a primeira página de resultados, até 50 campanhas classificadas alfabeticamente. Os valores de deslocamento e limite não são aplicados. | Use `Get Campaign` diretamente se a ID da campanha for conhecida. Use a interface do usuário do Journey Optimizer para navegação e filtragem completas. |
| Nenhuma filtragem do lado do servidor por data, canal ou programação | A listagem de campanha oferece suporte à filtragem de status, mas não à filtragem de data de publicação, data de agendamento, canal ou tipo de campanha. | Use a lista de campanha da interface do usuário do Journey Optimizer para filtragem de data nativa e canal. |
| Recuperação de conteúdo de mensagem indisponível | O HTML de mensagem, as linhas de assunto, os tokens de personalização e o conteúdo da oferta não estão disponíveis por meio das ferramentas atuais. | Visualize o conteúdo da mensagem e a personalização diretamente na interface do usuário do Journey Optimizer. |