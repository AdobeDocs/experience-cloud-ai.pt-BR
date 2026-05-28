---
solution: Real-Time Customer Data Platform
title: Real-Time CDP MCP (Beta)
description: Saiba como conectar o Adobe Real-Time CDP a clientes MCP usando o servidor MCP.
feature: Integrations
topic: Content Management, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: b2c93fd31bb72ebaf79aaa07aab68d39e63dc9b5
workflow-type: tm+mt
source-wordcount: '2634'
ht-degree: 0%

---

# Real-Time CDP MCP (Beta) {#rtcdp-mcp}

Você pode usar a integração do Adobe Real-Time CDP MCP para consultar públicos, destinos e integridade da ativação usando prompts em linguagem simples, sem gravar chamadas de API ou navegar nas telas dos produtos. Essa integração atende clientes do Adobe Real-Time CDP e do Adobe Real-Time CDP B2B edition, fornecendo uma maneira conversacional de inspecionar dados e workflows compatíveis do Real-Time CDP de clientes compatíveis com MCP. Leia este guia para saber como a integração funciona, o que você pode fazer com ela e como começar.

>[!AVAILABILITY]
>
>O Real-Time CDP MCP está no Beta. O recurso e a documentação estão sujeitos a alterações. O servidor MCP do Real-Time CDP é distribuído como um **servidor de transporte HTTP remoto** que os usuários instalam e configuram em clientes MCP e plataformas de aplicativos com suporte (por exemplo, [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] ou [!DNL VS Code]). A autenticação é tratada por meio de um **fluxo de logon baseado em navegador** — quando o cliente se conecta ao servidor pela primeira vez, ele abre o navegador padrão para que você possa entrar com as credenciais da Adobe e autorizar o acesso. Entre em contato com o representante da Adobe para acessar este programa da Beta.

## Beta, segurança e avisos legais {#mcp-notices}

**aviso sobre a documentação do Beta:** esta documentação abrange um recurso do Beta e não constitui a documentação final. O conteúdo descrito aqui está relacionado a uma versão do Beta e está sujeito a alterações até sua disponibilização geral. A Adobe não faz declarações sobre a integridade ou a precisão desta documentação.

Ao usar o Adobe Real-Time CDP MCP Server (Beta) (&quot;Beta&quot;), você reconhece que o Beta é fornecido **&quot;no estado em que se encontra&quot; sem garantias de qualquer tipo**. A Adobe não tem nenhuma obrigação de manter, corrigir, atualizar, alterar, modificar ou oferecer suporte à Beta. É recomendável ter cuidado e não depender de forma alguma do funcionamento ou desempenho correto desse Beta e/ou dos materiais que o acompanham. O Beta é considerado Informações confidenciais da Adobe. Qualquer &quot;Feedback&quot; (informação sobre o Beta incluindo, mas não se limitando a, problemas ou defeitos encontrados durante o uso do Beta, sugestões, melhorias e recomendações) fornecido por Você ao Adobe é atribuído ao Adobe, incluindo todos os direitos, cargos e interesses no e no Feedback.

>[!WARNING]
>
>O protocolo de contexto de modelo (MCP) é um padrão de código aberto emergente e pode apresentar riscos de segurança ou confiabilidade. As integrações do servidor Adobe MCP e a documentação relacionada são fornecidas &quot;no estado em que se encontram&quot;, sem garantias de nenhum tipo.
>
>Conectar clientes ou servidores MCP a produtos da Adobe é uma configuração selecionada pelo cliente. Os clientes são responsáveis por avaliar a segurança e a adequação de qualquer integração de MCP. O Adobe não é responsável por problemas resultantes de configuração incorreta, uso incorreto do MCP, vulnerabilidades em implementações de terceiros ou ações não intencionais executadas por meio de fluxos de trabalho habilitados para MCP.
>
>Para reduzir os riscos, a Adobe incentiva o teste de integrações em um ambiente de sandbox antes do uso produtivo e a análise e validação cuidadosas de todas as ações e respostas iniciadas pelo MCP antes de confirmar ou confiar nelas.

## Qual é o protocolo de contexto do modelo? {#mcp-overview}

As equipes de marketing, dados e experiência do cliente dependem cada vez mais de aplicativos baseados em bate-papo e ferramentas de desenvolvedor — como Anthropic Claude, OpenAI ChatGPT, Cursor e Microsoft Copilot Studio — para simplificar seu trabalho diário. Esses aplicativos oferecem suporte ao **Protocolo de Contexto de Modelo (MCP)**, um padrão aberto que permite que os aplicativos exponham ferramentas de back-end a grandes modelos de idioma (LLMs) de maneira uniforme.

O Real-Time CDP agora fornece um servidor MCP que exibe operações de público-alvo, destino e ativação diretamente dentro de qualquer aplicativo compatível com MCP. Com a integração do Real-Time CDP MCP, diferentes personalidades podem colaborar em torno da mesma segmentação e dados de ativação — sem gravar consultas nas APIs REST do Adobe Experience Platform ou navegar por várias telas de interface do usuário. Os clientes podem descrever a intenção por conversação e permitir que o LLM chame as ferramentas de MCP apropriadas.

## Principais recursos {#mcp-capabilities}

O servidor MCP do Real-Time CDP é uma superfície de monitoramento e triagem **somente leitura**. Ele expõe APIs de recuperação em públicos, destinos, fontes, identidade e resolução de perfil como respostas em linguagem simples no assistente de IA, sem escrever consultas ou navegar pelas telas do produto. Nenhum dado pode ser criado, modificado ou excluído por meio do servidor MCP.

>[!IMPORTANT]
>
>Todas as ferramentas no Beta atual são **somente leitura**. Operações de gravação — incluindo criação, ativação, atualização ou exclusão de públicos, destinos ou fluxos de dados — não são compatíveis.

A versão do Beta inclui as 18 ferramentas a seguir:

| Ferramenta | Descrição |
| --- | --- |
| `search_audiences` | Liste e pesquise públicos-alvo por nome, tipo de entidade, estado do ciclo de vida, namespace de identidade ou origem. |
| `preview_audience_membership` | Estime o tamanho de uma expressão de segmento do PQL ou SDD antes de salvá-la como um público. |
| `inspect_audience_evaluation_jobs` | Recupere registros de trabalho de avaliação do segmento para diagnosticar por que um público-alvo em lote não está sendo atualizado ou para confirmar o histórico de avaliação recente. |
| `inspect_audience_export_jobs` | Recupere registros de trabalho de exportação de público-alvo para confirmar as exportações concluídas ou exibir detalhes de falha. |
| `search_destination_connectors` | Liste os tipos de conectores de destino disponíveis na plataforma (por exemplo, [!DNL Amazon S3], [!DNL Google Ads], [!DNL Salesforce] CRM). |
| `search_destination_accounts` | Listar contas de destino autenticadas — instâncias configuradas de um tipo de conector de destino. |
| `search_destination_input_connections` | Recupere a entrada do lado do Experience Platform de um fluxo de destino — o público-alvo ou conjunto de dados que está sendo exportado. |
| `search_destination_output_connections` | Recuperar o endpoint externo de um fluxo de destino — caminho de destino, formato de arquivo e configuração de entrega. |
| `search_destination_flows` | Liste e inspecione os fluxos de ativação de destino configurados, incluindo seu estado, mapeamentos e agendamento. |
| `inspect_flow_runs` | Recuperar histórico de execução para fluxos de origem e destino — status, tempo, contagens de registros e detalhes de falhas por execução. |
| `search_source_connectors` | Liste os tipos de conector de origem disponíveis na plataforma. |
| `search_source_accounts` | Listar contas de origem autenticadas — instâncias configuradas de um tipo de conector de origem. |
| `search_source_input_connections` | Recupere a camada de seleção de dados de um fluxo de origem — o que está sendo extraído de uma conta. |
| `search_source_output_connections` | Recupere o destino do conjunto de dados do Experience Platform de um fluxo de origem — onde os dados assimilados chegam. |
| `search_source_flows` | Liste e inspecione os pipelines configurados de assimilação de origem, incluindo estado, mapeamentos e agendamento. |
| `search_identity_namespaces` | Listar definições de namespace de identidade em sua sandbox — tanto namespaces padrão quanto personalizados da Adobe. |
| `search_merge_policies` | Registros da política de mesclagem de listas que controlam como os Perfis de clientes em tempo real são montados a partir de fragmentos de perfil. |
| `search_organizations` | Listar as organizações da Adobe acessíveis ao usuário autenticado. |

## Casos de uso {#mcp-use-cases}

O servidor MCP do Real-Time CDP foi criado para **monitoramento e triagem**. Como o servidor funciona com IDs em vez de nomes, um fluxo de trabalho típico começa com uma lista — peça a Claude para mostrar o que está disponível, escolha o item desejado e faça perguntas de acompanhamento usando a ID retornada.

| Meta | Exemplo de prompt |
| --- | --- |
| **Listar seus públicos-alvo** | &quot;Listar meus públicos-alvo na sandbox do `prod`.&quot; |
| **Inspecionar um público-alvo específico** | &quot;Mostre-me os detalhes e o estado do ciclo de vida da ID de público-alvo `abc123`.&quot; |
| **Diagnosticar uma falha de avaliação** | &quot;Mostre-me os trabalhos de avaliação mais recentes e sinalize as falhas.&quot; |
| **Verificar um trabalho de exportação** | &quot;Liste os trabalhos de exportação de público-alvo recentes e mostre-me o status de cada um.&quot; |
| **Estimar tamanho do público** | &quot;Estime o tamanho desta expressão PQL antes de salvá-la: `homeAddress.country = 'US'`.&quot; |
| **Listar tipos de conectores de destino** | &quot;Quais tipos de conector de destino estão disponíveis na minha sandbox?&quot; |
| **Listar contas de destino configuradas** | &quot;Listar minhas contas de destino e o estado da conexão.&quot; |
| **Listar fluxos de destino** | &quot;Listar meus fluxos de ativação de destino e mostrar quais estão habilitados ou desabilitados.&quot; |
| **Inspecionar um fluxo de destino** | &quot;Mostrar a configuração completa da ID de fluxo de destino `xyz789`.&quot; |
| **Verificar integridade da conta de destino** | &quot;Listar minhas contas de destino e sinalizar qualquer uma que esteja em estado de erro.&quot; |
| **Monitorar execuções de ativação recentes** | &quot;Mostrar execuções de fluxo das últimas 24 horas e sinalizar falhas.&quot; |
| **Investigar uma execução com falha** | &quot;Mostrar o histórico de execuções da ID de fluxo `xyz789` e resumir os erros.&quot; |
| **Listar fluxos de origem** | &quot;Listar meus fluxos de assimilação de origem e mostrar o estado atual deles.&quot; |
| **Inspecionar um fluxo de origem** | &quot;Mostre-me a configuração para a ID do fluxo de origem `src456` — o que ele está assimilando e onde ele chega?&quot; |
| **Verificar integridade da execução de assimilação** | &quot;Mostrar histórico de execuções recentes para a ID do fluxo de origem `src456` e sinalizar falhas.&quot; |
| **Listar namespaces de identidade** | &quot;Quais namespaces de identidade são configurados na minha sandbox?&quot; |
| **Listar políticas de mesclagem** | &quot;Listar minhas políticas de mesclagem e mostrar qual é o padrão.&quot; |
| **Encontrar a ID da organização** | &quot;Listar as organizações da Adobe às quais tenho acesso.&quot; |

## Acesso e habilitação {#mcp-access}

>[!AVAILABILITY]
>
>O servidor MCP do Real-Time CDP está no Beta e não está aberto para inscrição de autoatendimento. O acesso é feito apenas por convite e exige que sua organização da Adobe seja explicitamente solicitada antes que você possa se conectar.

Para solicitar acesso:

1. Entre em contato com seu representante de conta da Adobe (Gerente de sucesso do cliente, Gerente técnico de conta ou Executivo de conta) e expresse seu interesse no programa Real-Time CDP MCP Beta.
2. O representante da Adobe entrará em contato com a equipe de produtos para avaliar a qualificação e habilitar a ID da organização.
3. Depois de ativado, o representante da Adobe confirmará o acesso e fornecerá material de integração adicional.

>[!NOTE]
>
>Somente as organizações que foram explicitamente ativadas podem se conectar ao servidor MCP do Real-Time CDP. Tentar conectar-se antes da ativação resultará em um erro de autenticação.

## Pré-requisitos {#mcp-prerequisites}

Antes de conectar o servidor MCP do Real-Time CDP ao seu cliente MCP, verifique o seguinte:

* Você tem uma licença ativa do Real-Time CDP.
* Sua organização da Adobe foi habilitada para o programa Beta pelo representante da Adobe (consulte [Acesso e habilitação](#mcp-access)).
* Você tem acesso a um cliente MCP com suporte, como [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] ou [!DNL VS Code].
* Você tem a ID da organização e o nome da sandbox que deseja consultar.
* Você tem as permissões necessárias no Adobe Experience Platform para exibir públicos, destinos e entidades de serviço de fluxo.

## Conectar o servidor MCP do Real-Time CDP {#mcp-connect}

O ponto final do servidor MCP do Real-Time CDP é:

```
https://rtcdp-mcp.adobe.io/mcp
```

O servidor usa um **transporte HTTP remoto** com um **fluxo de entrada do Adobe baseado em navegador**. Em todos os clientes, o padrão de configuração é o mesmo:

1. Adicionar a URL do servidor: `https://rtcdp-mcp.adobe.io/mcp`
2. Salve ou habilite a conexão.
3. Conclua o **logon do Adobe baseado em navegador** na primeira vez que o cliente chamar uma ferramenta.
4. Forneça `imsOrgId` e `sandboxName` no início de cada sessão.

### Configuração JSON geral {#mcp-connect-json}

Para clientes que aceitam uma configuração de servidor MCP baseada em JSON, como Claude Desktop (`claude_desktop_config.json`), Código VS ou qualquer cliente que leia um arquivo `mcp.json`, use um dos seguintes formatos, dependendo se o cliente oferece suporte a HTTP remoto nativo ou requer uma ponte local:

**Via ponte `mcp-remote` (Claude Desktop e outros clientes que requerem uma ponte local)**

```json
{
  "mcpServers": {
    "rtcdp": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://rtcdp-mcp.adobe.io/mcp"
      ]
    }
  }
}
```

**HTTP remoto nativo (clientes que dão suporte a ele diretamente)**

```json
{
  "mcpServers": {
    "rtcdp": {
      "url": "https://rtcdp-mcp.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

>[!NOTE]
>
>Nenhuma chave de API, tokens de portador ou cabeçalhos adicionais são necessários na configuração. A autenticação é totalmente realizada por meio do fluxo de logon do Adobe baseado em navegador na primeira utilização.

### Instalar em clientes baseados em interface do usuário {#mcp-connect-ui}

#### Claude

Para `claude.ai` e Claude Desktop, adicione o servidor MCP do Real-Time CDP como um **conector personalizado** usando a URL do servidor `https://rtcdp-mcp.adobe.io/mcp`.

* **Planos individuais** — Em Claude, navegue até **Personalizar → Conectores**, selecione **Adicionar conector** e insira a URL do servidor.
* **Planos de Equipe e Empresa** — Um espaço de trabalho **Proprietário** ou **Proprietário Primário** adiciona o conector em **Configurações da organização → Conectores**. Depois de adicionado, cada usuário o ativa em suas próprias configurações do Claude.

Depois que o conector for adicionado, ative-o em uma conversa e conclua o logon no navegador do Adobe na primeira utilização. Claude descobre o servidor de autorização do Adobe automaticamente — nenhuma ID do cliente ou segredo do cliente é necessário.

#### ChatGPT

Em [!DNL ChatGPT], adicione o servidor MCP do Real-Time CDP como um **conector personalizado**:

1. Navegue até **Configurações → Conectores** (ou **Configurações → Aplicativos e conectores**, dependendo do seu plano).
2. Selecione **Adicionar conector** e insira `https://rtcdp-mcp.adobe.io/mcp` como a URL do servidor.
3. Salve o conector. Dependendo do seu plano do [!DNL ChatGPT], esta etapa pode exigir **Modo de desenvolvedor** ou aprovação do administrador do espaço de trabalho.
4. Quando o conector estiver ativado, autentique por meio do logon no navegador da Adobe quando solicitado na primeira vez que usar o.

#### Cursor

No Cursor, adicione o servidor MCP do Real-Time CDP como um servidor MCP remoto:

1. Abra **Configurações → MCP**.
2. Selecione **Adicionar novo servidor** e insira `https://rtcdp-mcp.adobe.io/mcp` como a URL do servidor.
3. Selecione **conectar** para acionar a entrada da Adobe baseada em navegador e autenticar.

Depois de conectadas, as ferramentas do Real-Time CDP ficam disponíveis nos modos Compositor e Agente do cursor.

#### Outros clientes com base na interface do usuário

Para clientes como o Código VS ou outros aplicativos Web e de área de trabalho com suporte a MCP remoto, adicione o servidor MCP do Real-Time CDP como um servidor HTTP **remoto** usando `https://rtcdp-mcp.adobe.io/mcp`. Se o cliente suportar cabeçalhos opcionais ou tokens de portador, deixe-os vazios. A autenticação é realizada por meio do fluxo de logon do Adobe com base em navegador na primeira utilização.

### Instalar em clientes técnicos {#mcp-connect-technical}

#### código Claude

Adicione o servidor do terminal:

```bash
claude mcp add --transport http rtcdp https://rtcdp-mcp.adobe.io/mcp
```

Em seguida, inicie o Claude Code e execute:

```text
/mcp
```

Selecione o servidor `rtcdp` e conclua o fluxo de logon do Adobe em seu navegador. Se você já tiver adicionado o servidor no `claude.ai`, ele poderá aparecer automaticamente no Código Claude quando ambos estiverem conectados à mesma conta.

#### Codex

Adicione o servidor do terminal:

```bash
codex mcp add rtcdp --url https://rtcdp-mcp.adobe.io/mcp
```

Autentique o servidor:

```bash
codex mcp login rtcdp
```

Verifique a configuração:

```bash
codex mcp list
```

Você também pode adicionar o servidor diretamente a `~/.codex/config.toml`:

```toml
[mcp_servers.rtcdp]
url = "https://rtcdp-mcp.adobe.io/mcp"
```

### Parâmetros de solicitação obrigatórios {#mcp-connect-params}

Cada chamada de ferramenta requer dois parâmetros que definem o escopo da solicitação para o locatário do Adobe Experience Platform:

* `imsOrgId` — sua ID de organização, mapeada para o cabeçalho `x-gw-ims-org-id` nas chamadas downstream de API do Experience Platform.
* `sandboxName` — o nome da sandbox do Experience Platform, mapeado para o cabeçalho `x-sandbox-name`.

Forneça-os no início de cada sessão. Por exemplo:

> &quot;Use a organização `1234ABCD@AdobeOrg` e a sandbox `prod` para esta sessão.&quot;

Se você não souber a ID da organização, peça para o seu assistente de IA ligar para `search_organizations` — ele retornará todas as organizações que suas credenciais da Adobe puderem acessar.

## Limitações conhecidas (Beta) {#mcp-limitations}

As seguintes limitações se aplicam à versão atual do Beta do servidor MCP [!DNL Adobe Real-Time CDP]:

| Limitação | Descrição | Solução alternativa |
| --- | --- | --- |
| **Superfície somente leitura** | O servidor MCP expõe apenas APIs de recuperação. Não é possível criar, atualizar, ativar ou excluir públicos, destinos ou fluxos de dados. | Use a interface do usuário do Real-Time CDP ou as APIs REST do Experience Platform para operações de gravação. |
| **Nenhuma métrica de envolvimento ou entrega** | O servidor MCP não retorna estatísticas de delivery downstream, engajamento ou métricas de conversão das plataformas de destino. | Use os relatórios da própria plataforma de destino, o Customer Journey Analytics MCP ou o Adobe Analytics MCP para dados de engajamento e conversão. |
| **A consulta de segmento deve ser criada externamente** | `Preview Audience Membership` requer uma expressão PQL ou SDD válida como entrada; o servidor MCP não compõe a consulta para você. | Crie a expressão PQL/SDD na interface do usuário do Construtor de segmentos ou por meio da API do serviço de segmentação e cole no prompt do MCP. |
| **Paginação via tokens de continuação** | As ferramentas de lista retornam resultados paginados. A enumeração completa em sandboxes muito grandes requer o encadeamento de chamadas `continuationToken`. | Restrinja as consultas usando filtros (nome, estado, especificação de conexão, intervalo de tempo) em vez de enumerar a lista completa. |
| **A filtragem de execução de ativação é baseada apenas no tempo** | O `Inspect Activation Runs` oferece suporte à filtragem por status e carimbo de data/hora de conclusão (ms UTC de época), mas não diretamente por tipo de erro ou plataforma de destino. | O filtro por `flowId` primeiro (obtido de `List Configured Destinations`) para escopo é executado para um destino específico. |
| **ID da organização necessária no início da sessão** | Cada chamada de ferramenta (exceto `search_organizations`) requer `imsOrgId` e `sandboxName` como parâmetros explícitos. Se elas não forem fornecidas, as chamadas de ferramenta falharão. | No início de cada sessão, informe ao seu assistente de IA: &quot;Use a organização `<YOUR_ORG_ID>` e a sandbox `<SANDBOX_NAME>` para esta sessão.&quot; Se você não souber a ID da organização, chame `search_organizations` primeiro. Ela retornará as organizações que suas credenciais podem acessar. |

## Perguntas frequentes {#mcp-faq}

+++Quais clientes MCP são compatíveis?

O servidor MCP do Real-Time CDP funciona com qualquer cliente que suporte servidores MCP remotos ou conectores personalizados — incluindo [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] e [!DNL VS Code]. O fluxo de configuração depende do cliente: os clientes baseados em interface do usuário normalmente adicionam o servidor de um painel de configurações ou conectores, enquanto os clientes técnicos, como Claude Code e Codex, podem adicioná-lo a partir da linha de comando ou dos arquivos de configuração.
+++

+++Como faço para obter acesso?

O acesso é por convite somente durante a Beta. Entre em contato com o representante de conta da Adobe (Gerente de sucesso do cliente, Gerente técnico de conta ou Executivo de conta) para solicitar a inscrição. Seu representante da Adobe entrará em contato com a equipe de produtos para habilitar sua organização. Consulte [Acesso e habilitação](#mcp-access) para obter detalhes.
+++

+++Como funciona a autenticação?

A autenticação é tratada por meio de um **logon baseado em navegador**. Quando o cliente MCP chama uma ferramenta pela primeira vez, ele abre o navegador padrão para uma página de logon do Adobe. Depois de autenticar e autorizar o cliente, a sessão é estabelecida e as chamadas de ferramenta subsequentes o reutilizam. Nenhuma chave de API ou credenciais de longa duração precisam ser armazenadas na configuração do cliente.
+++

+++Quais objetos do Real-Time CDP posso acessar via MCP?

Você pode acessar públicos, tipos de destino, contas de destino configuradas, fluxos de dados de destino, conexões de origem e de destino e histórico de execuções de ativação. As operações são somente leitura (recuperar APIs); as operações de gravação não são compatíveis com a versão atual.
+++

+++Preciso de acesso de desenvolvedor para usar o servidor MCP do Real-Time CDP?

Não. O servidor MCP foi projetado para personas técnicas e de marketing. Os profissionais de marketing podem interagir com ele usando prompts de linguagem natural em qualquer cliente MCP compatível, enquanto os engenheiros de dados e desenvolvedores podem usá-lo nas ferramentas de desenvolvedor que oferecem suporte ao MCP.
+++

