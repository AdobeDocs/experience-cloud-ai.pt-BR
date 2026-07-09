---
title: Ferramentas de contexto de sessão no CX Enterprise MCP
description: Saiba mais sobre as principais ferramentas que definem o contexto de organização, sandbox e visualização de dados para todas as chamadas de ferramenta do CX Enterprise MCP.
source-git-commit: 023a4c15ca787c9b110b52914fd18d0e6eecd23d
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Ferramentas de contexto de sessão no Adobe CX Enterprise MCP {#mcp-core}

O Adobe CX Enterprise MCP inclui um conjunto de ferramentas de contexto de sessão que estabelecem a organização da Adobe, a sandbox da Adobe Experience Platform e a visualização de dados da Customer Journey Analytics em que todas as outras ferramentas de produto operam. Não é necessária nenhuma licença ou habilitação adicional — essas ferramentas estão disponíveis para todos os usuários autenticados após a conexão com o [CX Enterprise MCP Server](overview.md).

## Como o contexto funciona {#mcp-core-how}

O CX Enterprise MCP aplica escopos a cada chamada de ferramenta para uma organização ativa da Adobe. Além disso, os requisitos de contexto dependem do produto:

- **Produtos baseados em Experience Platform** — [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) e [Journey Optimizer](ajo-mcp.md) ferramentas operam em uma sandbox Experience Platform. Definir a sandbox uma vez por sessão com `core-set_sandbox`; todos os três a compartilham.
- **Outros produtos** — Os produtos não criados no Experience Platform não usam o contexto de sandbox. Por exemplo, as ferramentas do [Customer Journey Analytics](cja-mcp.md) são resolvidas em relação a uma exibição de dados e as ferramentas do [Adobe Analytics](analytics-mcp.md) são resolvidas em relação aos conjuntos de relatórios.

Definir o contexto uma vez no início de uma sessão — as ferramentas de produtos individuais não alternam entre organizações, sandboxes ou exibições de dados no meio da sessão.

## Ferramentas disponíveis {#mcp-core-tools}

| Ferramenta | Descrição |
| --- | --- |
| `core-list_orgs` | Lista as organizações da Adobe acessíveis ao usuário autenticado. Retorna o nome para exibição e o identificador `@AdobeOrg` de cada organização. Use-a para pesquisar a ID da organização antes de chamar `core-switch_org`. |
| `core-switch_org` | Define a organização ativa da Adobe para a sessão. Todas as chamadas de ferramenta subsequentes têm escopo para essa organização até que a sessão termine ou a organização seja trocada novamente. |
| `core-list_sandboxes` | Lista as sandboxes da Experience Platform disponíveis na organização ativa. Retorna o nome, o título, o tipo (produção ou desenvolvimento) e o estado de cada sandbox. Use isso para procurar um nome de sandbox antes de chamar `core-set_sandbox`. |
| `core-set_sandbox` | Define a sandbox ativa do Experience Platform para a sessão. As ferramentas do Real-Time CDP, Experience Platform e Journey Optimizer colocam os dados no escopo dessa sandbox. |
| `core-list_dataviews` | Lista as visualizações de dados do Customer Journey Analytics disponíveis para o usuário autenticado no contexto atual. Retorna IDs de visualizações de dados e nomes de exibição. Use esta opção para procurar uma visualização de dados antes de chamar `core-set_dataview`. |
| `core-set_dataview` | Define a visualização de dados padrão do Customer Journey Analytics para a sessão. Quando definidas, as ferramentas do CJA que exigem uma visualização de dados — como `findDimensions`, `findMetrics` e `runReport` — usam esse valor automaticamente, a menos que uma visualização de dados diferente seja especificada na chamada de ferramenta individual. |

## Configuração típica de sessão {#mcp-core-setup}

Defina o contexto no início de uma sessão antes de chamar as ferramentas do produto:

1. **Organização** — Ligue para `core-list_orgs` para listar suas organizações acessíveis e, em seguida, para `core-switch_org` com a ID da organização de destino.
2. **Sandbox** — Se você planeja usar as ferramentas do Real-Time CDP, Experience Platform ou Journey Optimizer, chame `core-list_sandboxes` para listar as sandboxes disponíveis e `core-set_sandbox` com o nome da sandbox de destino.
3. **Visualização de dados** (somente CJA) — Se você planeja usar as ferramentas Customer Journey Analytics, chame `core-list_dataviews` para listar as visualizações de dados disponíveis e `core-set_dataview` com a visualização de dados escolhida.

Você pode solicitar ao cliente MCP que conclua essa configuração em uma única solicitação em idioma natural:

> &quot;Use a organização `1234ABCD@AdobeOrg`, a sandbox `prod` e a visualização de dados `My Company — Global` para esta sessão.&quot;

O cliente chamará as ferramentas apropriadas e confirmará quando o contexto for definido.

>[!TIP]
>
>Se suas credenciais do Adobe pertencerem a apenas uma organização, `core-list_orgs` e `core-switch_org` ainda funcionarão, mas a organização efetiva será a mesma independentemente. Você ainda precisa chamar `core-set_sandbox` se planeja usar as ferramentas do Real-Time CDP, Experience Platform ou Journey Optimizer e `core-set_dataview` se planeja usar as ferramentas do Customer Journey Analytics.

## Exemplo de prompts {#mcp-core-examples}

| Meta | Exemplo de prompt |
| --- | --- |
| Descobrir organizações disponíveis | &quot;A quais organizações da Adobe eu tenho acesso?&quot; |
| Definir contexto da organização | &quot;Alternar para a organização `My Org (1234ABCD@AdobeOrg)`.&quot; |
| Descobrir sandboxes disponíveis | &quot;Listar as sandboxes disponíveis em minha organização atual.&quot; |
| Definir contexto da sandbox | &quot;Use a sandbox `prod` para esta sessão.&quot; |
| Descubra as visualizações de dados disponíveis | &quot;Quais visualizações de dados do Customer Journey Analytics posso acessar?&quot; |
| Definir contexto de visualização de dados | &quot;Defina `My Company — Global` como a visualização de dados padrão.&quot; |
| Configuração completa da sessão | &quot;Configure uma sessão usando a organização `1234ABCD@AdobeOrg`, a sandbox `prod` e a visualização de dados `My Company — Global`.&quot; |

## Páginas relacionadas {#mcp-core-related}

- [Instalar o Adobe CX Enterprise MCP](install.md) — como conectar seu cliente MCP, incluindo a seção de configuração de contexto do produto.
- [Acesse as ferramentas do CX Enterprise MCP](access.md) — acesse os requisitos por produto.