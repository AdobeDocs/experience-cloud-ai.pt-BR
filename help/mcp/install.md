---
title: Instalar o Adobe CX Co-worker Gateway
description: Saiba como conectar clientes compatíveis com MCP ao Adobe CX Co-worker Gateway.
source-git-commit: 9f654bc1f7282cad51ef54b86167dbea1757364a
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%

---

# Instalar o Adobe CX Co-worker Gateway {#mcp-install}

Leia este guia para saber como conectar um cliente compatível com MCP ao Adobe CX Co-worker Gateway.  O CX Co-worker Gateway usa um endpoint para todas as ferramentas de produto documentadas:

```
https://cx-coworker-gateway.adobe.io/mcp
```

Antes de instalar, confirme se a organização e a conta de usuário podem acessar as ferramentas do produto necessárias. Consulte [Acessar as ferramentas do CX Co-worker Gateway](access.md).

## Como a instalação funciona {#mcp-install-how}

O CX Co-worker Gateway usa um transporte HTTP remoto com um fluxo de logon Adobe baseado em navegador. Em todos os clientes compatíveis, o padrão de configuração é o mesmo:

1. Adicione a URL do ponto de extremidade: `https://cx-coworker-gateway.adobe.io/mcp`.
2. Salve ou habilite a conexão.
3. Conclua o logon do Adobe com base em navegador na primeira vez que o cliente chamar uma ferramenta.
4. Defina o contexto do produto para a sessão se suas ferramentas exigirem — organização para todos os produtos, sandbox para ferramentas baseadas no Experience Platform e visualização de dados para o Customer Journey Analytics. Consulte [Contexto do produto para chamadas de ferramenta](#mcp-connect-params).

>[!NOTE]
>
>Não são necessárias chaves de API, tokens de portador, segredos do cliente ou cabeçalhos adicionais na configuração do cliente MCP. A autenticação é tratada por meio do fluxo de logon do Adobe na primeira utilização.

## Instalação corporativa (gerenciada pelo administrador) {#mcp-install-enterprise}

A maioria dos planos de equipes e clientes MCP empresariais exige que um administrador adicione conectores personalizados à organização. Nesses ambientes, a instalação do tem duas etapas:

1. Um administrador adiciona o endpoint do gateway do CX Co-worker uma vez para a organização.
2. Cada usuário ativa o conector e faz logon com suas próprias credenciais do Adobe.

### Etapa 1: Um administrador adiciona o endpoint {#mcp-install-enterprise-admin}

O administrador adiciona `https://cx-coworker-gateway.adobe.io/mcp` como um conector personalizado ou servidor MCP remoto nas configurações da organização do cliente. O local exato depende do cliente.

#### Claude Team e Enterprise {#mcp-install-enterprise-claude}

Nos planos de Equipe e Empresa do [!DNL Claude], os conectores no nível da organização são gerenciados por um **Proprietário** ou **Proprietário Primário** do espaço de trabalho.

1. Entre em [!DNL Claude] como um **Proprietário** ou **Proprietário Primário**.
2. Vá para **Configurações** > **Administração** > **Conectores**. Em alguns planos, isso aparece como **Configurações da organização** > **Conectores**.
3. Selecione **Adicionar conector personalizado**.
4. Digite `https://cx-coworker-gateway.adobe.io/mcp` como a URL do servidor e use um nome reconhecível, como &quot;Adobe para CX Co-worker Gateway&quot;.
5. Salve o conector.

#### Equipe ChatGPT e Empresa {#mcp-install-enterprise-chatgpt}

Nos espaços de trabalho Equipe e Empresa do [!DNL ChatGPT], os conectores são adicionados por um administrador de espaço de trabalho.

1. Entre no [!DNL ChatGPT] como administrador de espaço de trabalho.
2. Vá para **Configurações** > **Conectores**. Em alguns planos, isso aparece como **Configurações** > **Aplicativos e Conectores**.
3. Selecione **Adicionar conector**.
4. Digite `https://cx-coworker-gateway.adobe.io/mcp` como a URL do servidor.
5. Salve o conector. Dependendo da configuração do espaço de trabalho, essa etapa pode exigir a ativação do modo de desenvolvedor ou a concessão de aprovação no nível do espaço de trabalho.

#### Outros clientes gerenciados pela organização {#mcp-install-enterprise-other}

Para outros clientes que oferecem suporte a conectores remotos gerenciados por organização, adicione o CX Co-worker Gateway como um servidor HTTP MCP remoto usando o `https://cx-coworker-gateway.adobe.io/mcp`. Deixe os cabeçalhos opcionais, os campos de token do portador, os campos de ID do cliente e os campos de segredo do cliente vazios, a menos que o cliente exija um valor de espaço reservado.

### Etapa 2: Usuários habilitam o conector {#mcp-install-enterprise-user}

Depois que um administrador adiciona o CX Co-worker Gateway, cada usuário o habilita para sua própria conta:

1. Abra as configurações de conector pessoal, aplicativo ou MCP no cliente.
2. Localize o conector do CX Co-worker Gateway e ative-o.
3. Inicie uma conversa, chame uma das ferramentas do Adobe e conclua o logon da Adobe com base no navegador quando solicitado.
4. Defina o contexto do produto para a sessão se suas ferramentas exigirem — organização para todos os produtos, sandbox para ferramentas baseadas no Experience Platform e visualização de dados para o Customer Journey Analytics. Consulte [Contexto do produto para chamadas de ferramenta](#mcp-connect-params).

Os usuários não precisam inserir o URL sozinhos quando um administrador já tiver adicionado o conector para a organização.

## Instalação individual (autoatendimento) {#mcp-install-individual}

Se você usar um plano individual, um cliente de desenvolvedor configurado localmente ou uma organização que permita aos membros adicionar seus próprios conectores, adicione o endpoint diretamente nas configurações do seu cliente.

### Claude individual {#mcp-install-individual-claude}

Para a Área de Trabalho `claude.ai` e [!DNL Claude] em um plano individual:

1. Abra **Configurações** > **Conectores**.
2. Selecione **Adicionar conector personalizado**.
3. Digite `https://cx-coworker-gateway.adobe.io/mcp` como a URL do servidor.
4. Salve e ative o conector e conclua o fluxo de logon do Adobe na primeira utilização.

### ChatGPT individual {#mcp-install-individual-chatgpt}

1. Abra **Configurações** > **Conectores**. Em alguns planos, isso aparece como **Configurações** > **Aplicativos e Conectores**.
2. Selecione **Adicionar conector**.
3. Digite `https://cx-coworker-gateway.adobe.io/mcp` como a URL do servidor.
4. Salve e ative o conector e conclua o fluxo de logon do Adobe na primeira utilização.

### Cursor {#mcp-install-individual-cursor}

1. Abra **Configurações** > **MCP**.
2. Selecione **Adicionar novo servidor**.
3. Digite `https://cx-coworker-gateway.adobe.io/mcp` como a URL do servidor.
4. Selecione **Conectar** e conclua o fluxo de entrada da Adobe.

Após a conexão, as ferramentas Adobe para CX Co-worker Gateway estão disponíveis nos modos Composer e Agente do cursor.

### código Claude {#mcp-install-individual-claude-code}

Adicione o endpoint do terminal:

```bash
claude mcp add --transport http cx-enterprise https://cx-coworker-gateway.adobe.io/mcp
```

Em seguida, inicie [!DNL Claude Code] e execute:

```text
/mcp
```

Selecione o servidor `cx-enterprise` e conclua o fluxo de entrada do Adobe em seu navegador.

### Codex {#mcp-install-individual-codex}

Adicione o endpoint do terminal:

```bash
codex mcp add cx-enterprise --url https://cx-coworker-gateway.adobe.io/mcp
```

Autenticar:

```bash
codex mcp login cx-enterprise
```

Verifique a configuração:

```bash
codex mcp list
```

Você também pode adicionar o ponto de extremidade diretamente a `~/.codex/config.toml`:

```toml
[mcp_servers.cx-enterprise]
url = "https://cx-coworker-gateway.adobe.io/mcp"
```

### Configuração JSON geral {#mcp-install-individual-json}

Para clientes que aceitam uma configuração de servidor MCP baseada em JSON, use um dos formatos a seguir, dependendo se o cliente suporta HTTP remoto nativo ou requer uma ponte local.

**Via `mcp-remote` ponte**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://cx-coworker-gateway.adobe.io/mcp"
      ]
    }
  }
}
```

**HTTP remoto nativo**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "url": "https://cx-coworker-gateway.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

### Outros clientes {#mcp-install-individual-other}

Para outros desktops ou clientes Web com suporte a MCP remoto, adicione o Adobe for CX Co-worker Gateway como um servidor HTTP remoto usando o `https://cx-coworker-gateway.adobe.io/mcp`. Deixe os cabeçalhos opcionais, os campos de token do portador, os campos de ID do cliente e os campos de segredo do cliente vazios, a menos que o cliente exija um valor de espaço reservado.

## Contexto do produto para chamadas de ferramenta {#mcp-connect-params}

O MCP aplica escopos a cada chamada de ferramenta para uma organização ativa da Adobe. Além disso, os requisitos de contexto dependem do produto:

- **Produtos baseados no Experience Platform** — as ferramentas do Real-Time CDP, Experience Platform e Journey Optimizer operam em uma sandbox Experience Platform. Defina a sandbox uma vez por sessão; todos os três a compartilham.
- **Outros produtos** — Os produtos não criados no Experience Platform não usam o contexto de sandbox. As ferramentas do Adobe Analytics, Customer Journey Analytics, Workfront, Marketo e Target são resolvidas em relação aos próprios recursos do produto — por exemplo, visualizações de dados para o Customer Journey Analytics e conjuntos de relatórios para o Adobe Analytics.

Definir o contexto uma vez no início de uma sessão — as ferramentas de produtos individuais não alternam entre organizações, sandboxes ou exibições de dados no meio da sessão. Consulte [Ferramentas de contexto de sessão](context-tools.md) para obter as ferramentas que definem o contexto de organização, sandbox e visualização de dados.

Exemplo:

> &quot;Use a organização `1234ABCD@AdobeOrg`, a sandbox `prod` e a visualização de dados `My Company — Global` para esta sessão.&quot;

Se você não souber os valores necessários, peça ao cliente MCP para listar as organizações, sandboxes ou visualizações de dados disponíveis para suas credenciais do Adobe.