---
title: Adobe Marketing Agent for Microsoft 365 Copilot
description: Saiba como usar o Adobe Marketing Agent for Microsoft 365 Copilot.
hide: true
hidefromtoc: true
source-git-commit: 224c38c54ff1cf73abdb5eca5f0961b41a1daefc
workflow-type: tm+mt
source-wordcount: '1793'
ht-degree: 0%

---

# Adobe Marketing Agent para [!DNL Microsoft 365 Copilot]

O Adobe Marketing Agent para [!DNL Microsoft 365 Copilot] é uma ferramenta habilitada para IA que conecta o Adobe Experience Platform diretamente ao [!DNL Microsoft 365 Copilot]. Com esse agente, você pode fazer perguntas em linguagem natural nos aplicativos do [!DNL Microsoft 365], como [!DNL Teams], [!DNL Word], [!DNL Powerpoint] e [!DNL Excel], para recuperar instantaneamente insights de marketing do Experience Platform sem interromper o fluxo de trabalho. O mesmo agente está disponível nesses aplicativos, e seu histórico de bate-papo com a Adobe Marketing Agent é transferido. Por exemplo, você pode começar a pesquisa em [!DNL Copilot] em [!DNL Teams] e continuar a conversa em [!DNL Word] ou [!DNL Powerpoint] enquanto redige um resumo da campanha ou revisa uma apresentação.

Com o Adobe Marketing Agent para [!DNL Microsoft 365 Copilot], os gerentes de marketing, as equipes de análise e insights e as partes interessadas podem:

- Tome decisões de marketing mais rápidas e orientadas por dados.
- Reduza o tempo gasto alternando entre ferramentas.
- Simplifique o acesso ao público-alvo e aos insights de jornada em equipes.

## Como o agente funciona

>[!IMPORTANT]
>
>Atualmente, o Adobe Marketing Agent para [!DNL Microsoft 365 Copilot] oferece suporte ao Experience Platform Operational Insights, Customer Journey Analytics Data Insights, Audience Agent e Journey Agent.

O Adobe Marketing Agent para [!DNL Microsoft 365 Copilot] fornece uma experiência integrada entre o Experience Platform e os aplicativos [!DNL Microsoft 365]:

- A Adobe Marketing Agent aparece como um agente em [!DNL Microsoft 365 Copilot], incluindo em [!DNL Teams], [!DNL Word], [!DNL Powerpoint] e [!DNL Excel].
- Faça logon com sua conta do Adobe e selecione o ambiente de dados (sandbox, visualização de dados) que deseja usar.

### Acesso aos dados e permissões

As respostas recebidas refletem o **nível de dados e acesso** vinculado à sua identidade da Adobe. O que você pode consultar e ver é o mesmo ao qual tem direito no Experience Platform e suas soluções associadas. O Adobe Marketing Agent **herda** essas permissões e **não** exige uma configuração de permissões separada para a integração [!DNL Microsoft 365]. Para os recursos subjacentes do Assistente de IA do Experience Platform e outros agentes do Adobe AI, os **requisitos de permissão permanecem inalterados** em relação ao uso desses recursos no Experience Platform.

O agente conecta sua instância do [!DNL Microsoft 365] ao Experience Platform e seus aplicativos associados (Real-Time CDP, Adobe Journey Optimizer e Customer Journey Analytics). Com essa integração, você pode usar o Assistente de IA da Experience Platform e agentes para recuperar insights relevantes diretamente para sua instância do [!DNL Microsoft 365]. As respostas retornadas em sua instância [!DNL Microsoft 365] são apresentadas como textos de linguagem conversacional e natural, tabelas e visualizações de dados. Além disso, o suporte para perguntas de acompanhamento e investigações está disponível no mesmo chat do [!DNL Copilot].

## Principais casos de uso e cenários de exemplo

| Caso de uso | Descrição |
| --- | --- |
| Recuperar insights operacionais para públicos-alvo e jornadas do cliente | Com o Adobe Marketing Agent, você pode recuperar facilmente insights operacionais em seus públicos-alvo e jornadas do cliente. Você pode identificar quais públicos-alvo são os maiores ou os mais envolvidos, para que possa priorizar onde concentrar seus esforços. Você pode ver quais jornadas do cliente estão ativas no momento e saber como elas estão se saindo, ajudando você a identificar oportunidades para otimização. O agente também permite rastrear como seus diferentes segmentos estão crescendo ou diminuindo com o tempo, permitindo que você responda às mudanças na dinâmica do público à medida que elas ocorrem. |
| Use a visualização de dados para analisar melhor as jornadas e campanhas do cliente | Você pode analisar o desempenho e as quedas da jornada, comparar o desempenho da campanha ao longo do tempo e entender quais pontos de contato geram conversões. Além disso, você pode gerar relatórios visuais sobre o desempenho da campanha e compará-los entre canais, regiões ou em diferentes períodos de tempo. Você também pode explorar tendências sem precisar criar consultas ou painéis manualmente. |
| Capacite a colaboração e a tomada de decisões | Use os prompts sugeridos para explorar públicos, campanhas e tráfego da Web. Aproveite a interface em linguagem natural para aprender mais facilmente sobre os conceitos do Experience Platform e do Customer Journey Analytics. Além disso, você pode compartilhar insights em [!DNL Teams] canais ou bate-papos durante reuniões de planejamento. Você também pode usar o Adobe Marketing Agent para responder perguntas ad hoc em tempo real enquanto revisa planos ou apresentações, permitindo manter as partes interessadas alinhadas com o mesmo conjunto de métricas e definições. |

## Pré-requisitos

Antes de poder usar o Adobe Marketing Agent para [!DNL Microsoft 365 Copilot], primeiro verifique se você tem o seguinte:

- [!DNL Microsoft 365] com [!DNL Microsoft Teams] ou [!DNL Microsoft Copilot Chat].
- Experience Platform e pelo menos um dos seguintes: Real-Time CDP, Adobe Journey Optimizer e/ou Customer Journey Analytics.
- Direito à Experience Platform Agent Orchestrator e aos agentes.
- Acesso à conta da Adobe Experience Cloud da sua organização (logon e direitos do produto) para as soluções e os dados que você usa. Se você não tiver acesso ao Adobe, entre em contato com o administrador do Adobe.

## Habilitar o agente para sua organização {#enable-the-agent-for-your-organization}

Os usuários finais só podem usar o Adobe Marketing Agent depois que ele é disponibilizado em seu locatário do [!DNL Microsoft 365]. **Trabalhe com o [!DNL Microsoft 365] administrador do Copilot** (ou administrador equivalente para agentes do Copilot em sua organização) para habilitar o acesso e atribuir o agente conforme a necessidade da organização.

Os resultados típicos após a configuração do administrador incluem:

- Você pode abrir o **[!DNL Agent Store]** no [!DNL Teams], localizar o **[!DNL Adobe Marketing Agent]** na sua lista de agentes e escolher **[!DNL Add]** para anexá-lo aos seus agentes Copilot.
- Como alternativa, o administrador do Copilot pode **publicar** o agente para todos na organização ou para grupos específicos, de modo que os usuários não precisem adicioná-lo individualmente.

Para obter as etapas do administrador e as opções de política no centro de administração do [!DNL Microsoft 365], consulte [Gerenciar agentes para Microsoft 365 Copilot](https://learn.microsoft.com/en-us/microsoft-365-copilot/extensibility/manage) na documentação do Microsoft.

## Introdução

Depois que sua organização tiver habilitado o agente (consulte [Habilitar o agente para sua organização](#enable-the-agent-for-your-organization)), navegue até [!DNL Microsoft 365 Copilot] no aplicativo de sua escolha e use a navegação à esquerda para selecionar **[!DNL All Agents]**.

![Navegação à esquerda do Microsoft 365 Copilot com Todos os Agentes selecionados.](../agents/images/ama/all-agents.png)

Localize o cartão para [!DNL Adobe Marketing Agent] ou use a barra de pesquisa para procurar manualmente o agente. Depois que tiver o agente, selecione o cartão.

![Cartão do Adobe Marketing Agent ou resultado da pesquisa na galeria de agentes.](../agents/images/ama/select-ama.png)

Use a janela pop-up para saber mais sobre o agente. Quando estiver pronto, selecione **[!DNL Add]**.

![pop-up de detalhes do Adobe Marketing Agent com o botão Adicionar realçado.](../agents/images/ama/add-ama.png)

O painel [!DNL Microsoft 365 Copilot] é atualizado com a marca [!DNL Adobe Marketing Agent] agora na página principal.

![Página inicial do Microsoft 365 Copilot mostrando o Adobe Marketing Agent no painel principal.](../agents/images/ama/home.png)

### Fazer logon e definir seu contexto

Em seguida, avise o agente para fazer logon e siga as etapas necessárias para autenticar sua conta. Durante essa etapa, será necessário copiar um código numérico que o agente retorna e fazer logon na organização da Adobe. Se não conseguir concluir a entrada ou se não tiver acesso às soluções da Adobe para sua organização, contate o **administrador do Adobe**.

![Etapa de entrada da Adobe mostrando um código numérico a ser copiado e instruções para autenticação com sua organização da Adobe.](../agents/images/ama/sign-in.png)

Quando bem-sucedido, use o definidor de contexto para estabelecer a fonte de documentação, a sandbox e a visualização de dados que você usará para suas consultas.

![Interface do usuário do configurador de contexto para escolher a fonte da documentação, a sandbox e a exibição de dados para consultas.](../agents/images/ama/context.png)

### Usar o agente para recuperar insights operacionais

Depois de fazer logon, você pode usar os prompts fornecidos na página principal para começar. Você também pode aproveitar um prompt inicial que pode se ramificar para analisar públicos de marketing, revisar o desempenho da campanha e monitorar as jornadas da campanha. Por exemplo, selecione **[!DNL Review campaign performance]** e **[!DNL Analyze engagement - Show web visitors for top 10 products last week]**.

![Prompts de início na página inicial do agente, incluindo Revisar desempenho da campanha e Analisar opções de engajamento.](../agents/images/ama/starter-guide.png)

Aguarde alguns momentos para o agente calcular e, em seguida, ele responde com uma representação visualizada dos seus dados. Você pode usar o gráfico de barras apresentado ou pode selecionar **[!DNL View data]** para exibir os dados em tabelas.

![Resposta do agente com um gráfico de barras visualizando visitantes da Web para os principais produtos e a opção Exibir dados.](../agents/images/ama/response.png)

![Os mesmos insights mostrados como uma tabela de dados após selecionar Exibir dados.](../agents/images/ama/tables.png)

Você pode investigar mais detalhadamente selecionando perguntas de acompanhamento que o agente recomenda. Como alternativa, você pode girar e tentar prompts de início diferentes, verificar as fontes de informações às quais o agente fez referência ou fornecer feedback usando o mecanismo de feedback.

![Perguntas de acompanhamento sugeridas abaixo da resposta do agente para investigação adicional.](../agents/images/ama/follow-up.png)

Para obter mais informações sobre os recursos da interface do usuário do Assistente de IA, leia o manual no [usando o Assistente de IA](../ai-assistant/ai-assistant-ui.md).

## Segurança, privacidade e IA responsável

**Manuseio e governança de dados**

O Adobe Marketing Agent depende dos mesmos controles e governança que se aplicam ao Experience Platform e [!DNL Microsoft 365]. Sua organização mantém a propriedade e o controle de seus dados. Os insights retornados por meio do agente têm escopo para as permissões de Adobe e direitos de dados de cada usuário; nenhum modelo de permissão adicional é introduzido para a superfície [!DNL Microsoft 365] além do que já se aplica aos agentes do Experience Platform e Adobe AI relacionados.

**Uso da IA responsável**

O agente deve retornar insights somente leitura e não modifica os dados do cliente no Experience Platform. Você deve revisar quaisquer resumos e análises gerados antes de usá-los para tomar decisões comerciais.

**Idiomas e escopo com suporte**

A versão inicial está disponível em inglês. Os recursos estão limitados a insights somente leitura; o agente não cria ou atualiza ativos ou configurações de marketing.

## Apêndice

Leia a seguir para obter informações adicionais sobre o Adobe Marketing Agent para [!DNL Microsoft 365 Copilot].

### Etapas de administração do Adobe Marketing Agent [!DNL Microsoft 365 Copilot]

Para configurar agentes de um provedor externo (desenvolvedores de terceiros ou o Microsoft Commercial Marketplace), primeiro verifique se as configurações do locatário permitem aplicativos externos e depois os gerencie por meio da seção Aplicativos ou Agentes Integrados do centro de administração.

#### Ativar agentes externos nas configurações do locatário

Antes de implantar agentes externos, a política da organização deve permitir a implantação.

- Faça logon no [centro de administração do Microsoft 365](https://admin.microsoft.com/).
- Vá para **Agentes** > **Configurações** > **Acesso de usuário**.
- Em **Tipos de agente permitidos**, verifique se **Permitir aplicativos e agentes criados por editores externos** está selecionado.

>[!IMPORTANT]
>
>Se esta configuração estiver desabilitada, os agentes externos não aparecerão no [Repositório de Agentes](https://devblogs.microsoft.com/microsoft365dev/introducing-the-agent-store-build-publish-and-discover-agents-in-microsoft-365-copilot/) para seus usuários.

#### Adquirir e aprovar o agente

Normalmente, você pode encontrar agentes externos em [[!DNL Microsoft Commercial Marketplace]](https://appsource.microsoft.com/).

- **No Marketplace**: encontre o agente desejado e selecione **Obter agora**. Isso frequentemente o redirecionará de volta para a página **Aplicativos integrados** do seu centro de administração.
- **Permissões de Revisão**: na lista [Aplicativos Integrados](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide), selecione o agente externo.
- Revise as guias **Dados e ferramentas** e **Segurança e conformidade** para ver quais dados o provedor externo acessará.
- Selecione **Aprovar** ou **Ativar** para movê-lo para o inventário da sua organização.

#### Implantar para determinados usuários

Depois de aprovado, você pode controlar exatamente quem vê o agente na barra lateral do Copilot.

- No [[!DNL Microsoft 365] centro de administração](https://admin.microsoft.com/), navegue até **Agentes** > **Todos os agentes**.
- Selecione o agente externo na lista.
- Selecione **Implantar** (ou **Editar atribuição**).
- Escolha **Usuários/grupos específicos** e procure os indivíduos ou [!DNL Entra ID] grupos que devem tê-los.
- Selecione **Concluir implantação**. Isso &quot;envia&quot; o agente para esses usuários para que ele seja exibido automaticamente na interface do Copilot.

#### Gerenciar atualizações

Os provedores externos atualizam os agentes com frequência. Para gerenciar essas atualizações, siga as práticas recomendadas abaixo:

- Verifique o [[!DNL Agent Registry]](https://learn.microsoft.com/en-us/microsoft-365/admin/manage/agent-registry?view=o365-worldwide) periodicamente.
- Se uma atualização exigir novas permissões, o agente poderá mostrar um status de **Atualização Pendente**.
- Você deve **Aprovar atualizações** manualmente antes que a nova versão seja implantada para os usuários atribuídos.