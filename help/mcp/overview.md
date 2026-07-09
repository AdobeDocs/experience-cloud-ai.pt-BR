---
title: Servidor MCP corporativo Adobe CX
description: O servidor MCP Adobe CX Enterprise é o MCP unificado para Adobe CX Enterprise, oferecendo aos clientes MCP uma única conexão com as ferramentas de produtos compatíveis.
source-git-commit: b40034bdc866a2737b909386b79c028793f324cb
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 4%

---

# Servidor MCP corporativo Adobe CX {#mcp-overview}

O servidor MCP do Adobe CX Enterprise é o MCP (Protocolo de contexto de modelo unificado) para Adobe CX Enterprise. Com uma conexão, os clientes compatíveis com MCP podem acessar as ferramentas de produto do Adobe que sua organização e conta têm direito a usar.

>[!IMPORTANT]
>
>Sua organização da Adobe deve estar habilitada para que você possa usar as ferramentas do CX Enterprise MCP. Se sua organização ainda não tiver acesso, entre em contato com a equipe de conta da Adobe para solicitar a ativação da organização.

Use o endpoint do CX Enterprise para todas as configurações de cliente MCP:

```
https://cx-enterprise.adobe.io/mcp
```

Após se conectar, o endpoint expõe as ferramentas disponíveis para sua organização e credenciais da Adobe. As páginas específicas do produto neste guia descrevem o que cada ferramenta de produto pode fazer, quais dados pode acessar e quaisquer limitações específicas do produto.

## O que é o protocolo de contexto de modelo? {#mcp-what-is}

O MCP (Model Context Protocol) é um padrão de código aberto para conectar aplicativos de IA a sistemas externos. Os clientes compatíveis com MCP, como [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] e [!DNL VS Code], podem usar essas ferramentas para recuperar o contexto do produto, executar operações com suporte e retornar respostas em linguagem natural.

O CX Enterprise fornece um endpoint controlado para ferramentas de produtos CX Enterprise. Em vez de adicionar servidores de produtos separados, conecte-se uma vez ao endpoint e use as ferramentas de produto exibidas para suas soluções qualificadas.

## Ferramentas de produto disponíveis {#available-product-tools}

As seguintes ferramentas de produto estão documentadas neste guia:


| Ferramentas do produto | O que ele expõe por meio do endpoint | Disponibilidade | Documentação |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Real-Time CDP** | Públicos, destinos, origens, namespaces de identidade e integridade da ativação (somente leitura) | Beta | [Ferramentas do Real-Time CDP](rtcdp-mcp.md) |
| **Experience Platform** | Esquemas, conjuntos de dados, governança de dados, Serviço de consulta e eventos de auditoria (somente leitura) | Beta | [Ferramentas do Experience Platform](aep-mcp.md) |
| **Journey Optimizer** | Campanhas e configurações de canal (somente leitura) | Beta | [Ferramentas do Journey Optimizer](ajo-mcp.md) |
| **Customer Journey Analytics** | Visualizações de dados, dimensões, métricas, relatórios, segmentos, intervalos de datas, projetos e públicos-alvo (leitura e gravação) | Disponível | [Ferramentas do Customer Journey Analytics](cja-mcp.md) |
| **Adobe Analytics** | Conjuntos de relatórios, dimensões, métricas, relatórios, segmentos, intervalos de datas e projetos do espaço de trabalho (leitura e gravação para componentes compatíveis) | Disponível | [Ferramentas do Adobe Analytics](analytics-mcp.md) |
| **Workfront** | Ferramentas de gerenciamento de trabalho para projetos, tarefas e fluxos de trabalho de aprovação | Visualização | [Servidor MCP do Workfront](https://experienceleague.adobe.com/pt-br/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview) |


>[!NOTE]
>
>A disponibilidade da ferramenta depende das licenças do produto, da habilitação da organização, das permissões do produto e das credenciais do Adobe usadas para a autenticação. O MCP apenas supera as ferramentas que sua organização e conta de usuário têm direito de acesso. Consulte [Acessar ferramentas do CX Enterprise MCP](access.md).



## Introdução {#mcp-get-started}

1. Revise as [ferramentas do CX Enterprise MCP](access.md) para confirmar a disponibilidade, a habilitação e as permissões do produto.
2. Siga [Instalar o Adobe para CX Enterprise MCP](install.md) para conectar seu cliente MCP ao endpoint.
3. Revise a página do produto para cada ferramenta de produto que você planeja usar.

