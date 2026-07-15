---
title: Acesse as ferramentas do CX Co-worker Gateway
description: Confirme a disponibilidade do produto, a ativação da organização e as permissões antes de usar as ferramentas do Adobe CX Co-worker Gateway.
source-git-commit: 9f654bc1f7282cad51ef54b86167dbea1757364a
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# Acesse as ferramentas do CX Co-worker Gateway {#mcp-access}

O Adobe CX Enterprise expõe as ferramentas do produto por meio de um único MCP. O acesso é avaliado por ferramentas do produto: sua organização da Adobe deve estar habilitada para as ferramentas do produto relevantes e sua conta de usuário deve ter as permissões de produto necessárias para exibir ou alterar os dados do produto expostos por essas ferramentas.

>[!IMPORTANT]
>
>Sua organização da Adobe deve estar habilitada para que você possa usar as ferramentas do CX Co-worker Gateway. Se sua organização ainda não tiver acesso, entre em contato com a equipe de conta da Adobe para solicitar a ativação da organização.

## Requisitos de acesso {#mcp-requirements}


| Ferramentas do produto | Disponibilidade | Requisitos de acesso |
| --- | --- | --- |
| Real-Time CDP | Beta | Licença ativa do Real-Time CDP, habilitação do Beta para sua organização da Adobe e permissões para exibir os públicos, destinos, fontes, identidade e recursos de ativação que você consulta. |
| Experience Platform | Beta | Licença ativa do Experience Platform, capacitação da Beta para sua organização da Adobe e permissões para visualizar os esquemas, conjuntos de dados, governança, Serviço de consulta, auditoria e recursos de sandbox que você consulta. |
| Journey Optimizer | Beta | Licença ativa do Journey Optimizer, ativação do Beta para sua organização da Adobe e permissões para visualizar campanhas e configurações de canal. |
| Customer Journey Analytics | Disponível | Licença do Customer Journey Analytics ativo e um perfil de produto que inclui o item de permissão **Acesso ao MCP** no Adobe Admin Console. As permissões de produto ainda controlam quais visualizações de dados, componentes, relatórios, projetos e públicos-alvo você pode acessar ou modificar. |
| Adobe Analytics | Disponível | Licença do Adobe Analytics ativo e um perfil de produto que inclui o item de permissão **Acesso ao MCP** no Adobe Admin Console. As permissões de produto ainda governam quais conjuntos de relatórios, componentes, relatórios, segmentos, intervalos de datas e projetos você pode acessar ou modificar. |
| Workfront | Visualização | Licença ativa do Workfront e ativação do Workfront MCP. Consulte a [documentação do Workfront MCP](https://experienceleague.adobe.com/pt-br/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview). |


>[!NOTE]
>
>O MCP supera apenas as ferramentas que sua organização e credenciais estão autorizadas a usar. Se uma ferramenta de produto estiver ausente após o logon, confirme o licenciamento do produto, a ativação da organização e as permissões do usuário.

## Solicitar acesso {#mcp-request}

Para obter ferramentas do produto Beta ou de versões limitadas, entre em contato com o representante de conta da Adobe e especifique quais ferramentas de produto do Adobe for CX Co-worker Gateway você deseja usar. Seu representante pode coordenar a ativação do produto e confirmar quando sua organização da Adobe está pronta.

Para ferramentas de produtos geralmente disponíveis que usam o item de permissão **Acesso ao MCP**, peça a um administrador de sistema ou de produto para adicionar sua conta a um perfil de produto que inclua acesso ao MCP.

## Ativação no produto {#mcp-product-enablement}

Alguns produtos exigem ativação no produto ou permissões específicas do produto, além de acesso ao MCP. Por exemplo:

- O Adobe Analytics e o Customer Journey Analytics exigem o item de permissão **Acesso ao MCP** no Adobe Admin Console.
- As ferramentas do Workfront MCP são ativadas nas configurações do Workfront.
- As ferramentas de produto do Beta exigem a ativação da organização da Adobe antes que suas ferramentas apareçam por meio do MCP.

Verifique a página do produto da ferramenta do produto que você planeja usar para permissões específicas do produto, requisitos de contexto e limitações.

## Antes de instalar {#mcp-prerequisites}

Antes de conectar o cliente MCP, confirme se:

- Sua organização da Adobe está habilitada para as ferramentas de produto necessárias.
- Sua conta de usuário tem as permissões de produto necessárias para os dados e operações que você planeja usar.
- Você tem acesso a um cliente MCP com suporte, como [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] ou [!DNL VS Code].
- Para instalação corporativa, você ou um colega podem gerenciar conectores ou aplicativos personalizados nas configurações da organização do cliente MCP.

Próximo: [Instalar o Adobe CX Co-worker Gateway](install.md).