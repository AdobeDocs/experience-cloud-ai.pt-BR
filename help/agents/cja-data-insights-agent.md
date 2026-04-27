---
description: Saiba como visualizar dados com o Data Insights Agent no Customer Journey Analytics
title: Visualizar dados com a Data Insights Agent no Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/UtKIDlN2x7MOAiHNRRQ8b5OO4fIwzV74r1fnfMwblcQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b743a5d9-dc51-41ed-8b2f-86a1f8de430f
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 2690
ht-degree: 4%

---

# Visualizar dados com o Data Insights Agent

>[!AVAILABILITY]
>
>O Data Insights Agent está disponível para clientes qualificados por um período limitado. O acesso ao Data Insights Agent estará disponível até 31 de março de 2026. Para continuar usando o Data Insights Agent além dessa data sem interrupção, entre em contato com o representante de conta da Adobe para saber mais sobre como licenciar o Adobe Experience Platform Agent Orchestrator.

O Data Insights Agent, acessível pelo [Assistente de IA](/help/ai-assistant/ai-assistant-ui.md), é um agente de conversação de IA generativo que responde de forma rápida e eficiente a perguntas sobre seus dados. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e de dados reais.

Usar o Data Insights Agent para responder perguntas centradas em dados no Analysis Workspace pode economizar um tempo significativo, permitindo que você gaste criando visualizações manualmente no Analysis Workspace e se familiarizando com os componentes de visualização de dados.

![Data Insights Agent no Assistente de IA](/help/agents/images/cja-agent/cja-ai-asst-da.gif)

## Recursos dentro e fora do escopo

| Recurso | No escopo | Fora do escopo |
| --- | --- | --- |
| **Tipos de visualização** | <ul><li>Linha</li><li>Várias linhas</li><li>Tabela de forma livre</li><li>Barra</li><li>Rosquinha</li><li>Número do resumo</li></ul> | <ul><li>Fluxo</li><li>Fallout</li><li>Tabela de coorte</li><li>Área, Área empilhada</li><li>Bar Stacked</li><li>Marcador</li><li>Combo</li><li>Histograma</li><li>Horizontal Bar, Horizontal Bar Stacked</li><li>Key Metric Summary</li><li>Dispersão</li><li>Summary Change</li><li>Texto</li><li>Mapas de árvore</li><li>Venn</li><li>Guided analysis: Active growth, Conversion trends, Engagement, First use impact, Frequency, Funnel, Net growth, Release impact, Retention, Timeline, Trends</li></ul> |
| **Workspace actions and agent capabilities** | <ul><li>Build and update visualizations<p>Generates a freeform table and associated visualization (such as a line, bar, donut, and so forth).</p><p>For example, *What is the profit across SKUs from February to May?*</p></li><li>Ask follow-up questions<p>Respond to a prompt in the context from any prior prompts. Por exemplo:</p> <ul><li>Prompt 1: *Trend events from March.*</li><li>Prompt 2: *Show me the data from March to April instead*</li></ul> </li><li>Out-of-scope prompt detection<p>If you submit a prompt that is out of scope, such as *Export this project*, Data Insights Agent responds by informing you that the question is out of scope.</p></li></ul> | <ul><li>Compartilhar</li><li>Exportar</li><li>Baixar</li><li>Manage user preferences</li><li>Manage data view</li><li>Analytics Dashboards app</li><li>Atribuição</li><li>In-line summary or response<p>Data Insights Agent cannot respond in-line in the chat rail with a summary answer of a user prompt. Examples of out-of-scope prompts are, *Give me a summary of the insights from my last prompt* and *Summarize the highlights from the line visualization.*</p></li></ul> |
| **Clarifying questions** | If you ask a question that does not have enough context for Data Insights Agent to answer, or is too generic, Data Insights Agent responds with a clarifying question or suggested options. <p>The following clarifying questions are examples of component-related questions:</p><ul><li>Metric: *Which &quot;revenue&quot; metric did you mean?*</li><li>Dimension: *Which of the below &quot;regions&quot; do you want to focus on?*</li><li>Segment: *Which &quot;Account&quot; segment did you want to apply?*</li><li>Date Range: *By &quot;last month,&quot; did you mean the last full month or the last 30 days?*</li></ul><p>The following clarifying question is an example of a question related to dimension items:</p> <ul><li>Which &quot;store name&quot; did you mean? (For example, Store #5274, Store #2949, and so forth.)</li></ul> | Clarifying questions are limited to components and dimension items. Data Insights Agent cannot clarify things such as data views, visualizations, data granularity, comparison, and scope. When clarifying questions cannot be used, the agent defaults to what you are most likely asking for. If it returns an unexpected visualization or data granularity, you can ask a follow-up question or adjust the visualization and data. |
| **Data verifiability and correctness** | Data verifiability and correctness can be confirmed by viewing the generated freeform table and data visualization. <p>For example, if you ask Data Insights Agent to *Trend orders last month*, you can confirm that the correct metric (&quot;orders&quot;) and date range (&quot;last month&quot;) were selected in the newly generated panel, data visualization, and freeform table.</p> | Data Insights Agent does not respond by informing you which components or visualizations were added. |
| **Feedback mechanisms** | <ul><li>Thumbs up</li><li>Thumbs down</li><li>Sinalizar</li></ul> |  |


## Gerenciar acesso ao Data Insights Agent {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="Habilitar para o Data Insights Agent"
>abstract="Essa opção habilita essa visualização de dados para uso com o Data Insights Agent. O Data Insights Agent é um agente de conversação de IA generativa acessível pelo Assistente de IA no Customer Journey Analytics. Ele ajuda a analisar rapidamente os dados com prompts de texto. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e seus dados reais."

<!-- markdownlint-enable MD034 -->

The following parameters govern access to Data Insights Agent in Customer Journey Analytics:

* **Solution access**: Data Insights Agent is available for eligible customers for a limited time. Access to Data Insights Agent is available through February 28, 2026. It is not available in Adobe Analytics.

* **Contractual access**: If you are not able to use Data Insights Agent in the AI Assistant, please contact your organization&#39;s administrator or Adobe account team. Before your organization can use Data Insights Agent, you must agree to certain legal terms related to generative AI.

* **Permissions**: Necessary permissions must be granted in the [!UICONTROL Adobe Admin Console] before users can access Data Insights Agent.

  To grant permissions, a [product profile administrator](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) must complete the following steps in the [!UICONTROL Admin Console]:
   1. Na **[!UICONTROL Admin Console]**, selecione a guia **[!UICONTROL Produtos]** para exibir a página **[!UICONTROL Todos os produtos e serviços]**.
   1. Selecione **[!UICONTROL Customer Journey Analytics]**.
   1. Na guia **[!UICONTROL Perfis de produto]**, selecione o título do perfil de produto para o qual você deseja fornecer acesso ao [!UICONTROL Assistente de IA: Conhecimento do Produto].
   1. No perfil de produto específico, selecione a guia **[!UICONTROL Permissões]**.

      ![Guia Permissões no Admin Console](/help/agents/images/cja-agent/ai-assistant-permissions-tab.png)

   1. Na linha **[!UICONTROL Ferramentas de Relatório]** da tabela fornecida, selecione o ícone de edição ![Editar](/help/agents/images/cja-agent/Edit.svg).
   1. Role até ou pesquise por **[!UICONTROL Assistente de IA: Conhecimento do Produto]** e selecione o ícone de adição ![AddCircle](/help/agents/images/cja-agent/AddCircle.svg) ao lado dessa permissão.
   1. Role até ou pesquise por **[!UICONTROL Data Insights Agent]** e selecione o ícone de adição ![AddCircle](/help/agents/images/cja-agent/AddCircle.svg) ao lado dessa permissão.

      A permissão **[!UICONTROL Assistente de IA: Conhecimento do Produto]** e a permissão **[!UICONTROL Data Insights Agent]** são adicionadas à coluna **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicionar permissão](/help/agents/images/cja-agent/ai-assistant-permissions.png).

   1. Selecione **[!UICONTROL Salvar]** para salvar as permissões.

  Para obter informações adicionais sobre o controle de acesso, consulte [Controle de acesso](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/technotes/access-control#access-control).

* **Acesso à visualização de dados**: as visualizações de dados devem ser habilitadas para o Data Insights Agent.

  >[!IMPORTANT]
  >
  >Considere o seguinte ao ativar as visualizações de dados:
  >* É possível habilitar no máximo 50 visualizações de dados por organização IMS. Se você habilitar mais de 50 visualizações de dados em todos os perfis de produto para uma determinada organização, a Data Insights Agent usará as 50 visualizações de dados mais usadas.
  >  Você pode usar as [informações na coluna Data Insights Agent em Visualizações de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/manage-dataviews#manage-data-views) para exibir o número de visualizações de dados habilitadas para o Data Insights Agent em sua organização IMS.
  >* A Data Insights Agent pode fazer referência às visualizações de dados incluídas em algum momento durante o mesmo dia em que você as ativa.

  Para ativar visualizações de dados para o Data Insights Agent:

   1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]**.

   1. Selecione uma ou mais visualizações de dados que você deseja habilitar para o Data Insights Agent e selecione **[!UICONTROL Habilitar para o Data Insights Agent]**.

      ![Habilitar visualizações de dados para o Data Insights Agent](/help/agents/images/cja-agent/data-view-enable-dia.png)

      Para obter mais informações sobre como habilitar visualizações de dados para o Data Insights Agent, consulte as [Configurações de IA para uma visualização de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/create-dataview#ai-settings/help/data-views/create-dataview.md#ai-settings).

  Para exibir o número de visualizações de dados habilitadas para o Data Insights Agent em sua organização IMS:

   1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]**.

   1. Select the info icon at the top of the **[!UICONTROL Data Insights Agent]** column.

      ![Data Insights Agent info icon](/help/agents/images/cja-agent/data-insights-agent-tooltip.png)


## Access Data Insights Agent in the AI Assistant

1. Go to [experience.adobe.com](https://experience.adobe.com/) and log in with your Adobe ID.

2. Select **Customer Journey Analytics** from Experience Cloud Home.

3. Select **[!UICONTROL Blank project]** in the banner at the top of the projects page to open a new blank project.

4. Ensure that the selected data view for the panel is a data view that was enabled for use with Data Insights Agent, as described in [Manage access to Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Select the AI Assistant chat icon at the top-right area of the page.

   If you do not see the chat icon, contact your administrator so they can enable the following features in the Admin Console:

   * Reporting Tools: **[!UICONTROL AI Assistant: Product Knowledge]**

   * Data View Tools: **[!UICONTROL Data Insights Agent]**

   For additional details, see [Manage access to Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![AI Assistant icon](/help/agents/images/cja-agent/ai-asst-icon.png)

6. In the **[!UICONTROL Ask about Customer Journey Analytics]** dialog at the bottom of the page, ask a data visualization question using Data Insights Agent.

   For more information, see the following examples.

### Exemplo 1

For example, let&#39;s say you are interested in the orders your business received in July.

**Prompt:** Enter *&quot;Trend orders in July.&quot;*

![AI prompt](/help/agents/images/cja-agent/ai-asst-prompt1.png)

**Response:** Data Insights Agent gathers insights by looking through the data in the data view, including the metrics and components. It translates the prompt into the right dimensions and metrics within the data range.

As you can see, it automatically generated a line graph and a freeform table to show orders for July.

![Answer to prompt - line graph and freeform table](/help/agents/images/cja-agent/ai-asst-result.png)

### Exemplo 2

Next, you want to see how your revenue compares by region.

**Prompt:** In the prompt window, enter *&quot;Show revenue by region.&quot;*

**Response:** Data Insights Agent intelligently understands that by &quot;region,&quot; you mean &quot;customer region.&quot; Ele produz um gráfico de barras que melhor mostra a receita por região:

![Gráfico de barras](/help/agents/images/cja-agent/ai-asst-result2.png)

### Exemplo 3

Em seguida, além de entender a receita por região, você também deseja ver os dados para lucro por região. Em vez de repetir o prompt anterior, você pode solicitar que o Data Insights Agent atualize a visualização mais recente e a tabela de forma livre.

**Prompt:** Na janela de prompt, digite *&quot;Adicionar lucro.&quot;*

**Resposta:** O gráfico de **[!UICONTROL Barra]** ainda fornece a resposta mais concisa, mas a métrica de lucro foi adicionada como uma coluna na tabela de forma livre:

![Gráfico de barras](/help/agents/images/cja-agent/ai-asst-result4.png)

### Exemplo 4

Por fim, vamos analisar a receita por categoria de produto.

**Prompt:** Na janela do prompt, digite *&quot;Proporção da receita por categoria do produto.&quot;*

**Resposta:** Novamente, o Data Insights Agent escolhe a visualização mais apropriada, neste caso a visualização **[!UICONTROL Rosca]**, para responder à pergunta.

![Rosquinha](/help/agents/images/cja-agent/ai-asst-result3.png)

## Acessar o Data Insights Agent em aplicativos Experience Cloud

O Adobe Experience Platform Agent Orchestrator permite acessar a funcionalidade do Data Insights Agent em vários aplicativos da Adobe Experience Cloud, como o Adobe Journey Optimizer e o Real-Time CDP.

O Agent Orchestrator interpreta sua solicitação, determina quais agentes especializados são necessários e os coordena para fornecer a resposta correta. Ela rastreia o contexto em interações de várias voltas, para que você possa criar consultas anteriores naturalmente.

Para obter mais informações, consulte [Adobe Experience Platform Agent Orchestrator](https://business.adobe.com/br/products/experience-platform/agent-orchestrator.html).

## Exemplo de prompts de visualização de dados

A seguir estão alguns exemplos de prompts comuns e as visualizações usadas pelo Data Insights Agent para responder a esses prompts.

| Exemplo de prompt | Visualização esperada |
| --- | --- |
| Mostrar lucros em [Mês] | Linha<p>Por padrão, solicitar uma tendência ou métrica em um determinado intervalo de tempo retorna uma visualização de linha. |
| Pedidos de tendência em [Mês] | Linha |
| Mostrar receita por região em [Mês] | Barra |
| Parte da receita por categoria de produto | Rosquinha |
| Pedidos por dia da semana, de janeiro a maio | Barra |
| Mostrar pedidos por gênero, de março a junho | Barra |
| Qual é o lucro em SKUs de fevereiro a maio | Barra |
| Receita por nome de armazenamento em [Mês] | Barra |
| Quais foram meus 10 principais SKUs por lucro em [Mês]? | Barra |
| Proporção de compras por mês do ano | Rosquinha |
| Lucro total em [Mês] | Número do resumo<p>Solicitar o &quot;total&quot; de uma métrica em um determinado intervalo de tempo deve retornar uma visualização do Número do resumo. |


## Solicitação de práticas recomendadas

O Data Insights Agent processa o contexto fornecido por cada prompt do usuário e tenta responder de forma inteligente com a visualização e os componentes mais apropriados em uma tabela de forma livre.

As respostas podem variar com base nas palavras e frases específicas usadas no prompt, e pequenas alterações no idioma podem levar a resultados diferentes.

Para obter os melhores resultados, considere as seguintes diretrizes:

* **Seja específico:** Inclua termos exatos para restringir a resposta. Este é um exemplo de um aviso específico: &quot;Vendas do mês passado na Califórnia&quot;

* **Use métricas, dimensões e segmentos claros:** Adicionar métricas específicas (como &quot;Receita&quot;), dimensões (como &quot;nome do site&quot;), segmentos (como &quot;usuários do iPhone&quot;) e intervalos de datas (como &quot;últimos três meses&quot;) ajuda a Data Insights Agent a se concentrar nos dados corretos.

* **Fazer perguntas diretas:** a formulação direta de perguntas facilita que a Data Insights Agent forneça insights claros e relevantes. O exemplo a seguir mostra uma pergunta direta em um prompt: &quot;Qual é a receita média por categoria de produto neste ano?&quot;

Analise a tabela a seguir de termos de exemplo e frases que você pode usar em prompts com o Data Insights Agent, juntamente com os tipos de respostas que você pode esperar.

Esses exemplos são projetados para ajudar você a se familiarizar com a forma como palavras ou estruturas específicas podem influenciar a saída do Data Insights Agent, garantindo insights mais precisos e valiosos. O Data Insights Agent usa IA generativa, de modo que as visualizações ou os dados selecionados podem variar um pouco entre prompts semelhantes.

| Resultado desejado | Exemplo de termos e frases |
| --- | --- |
| Visualização do número do resumo | <ul><li>Total</li></ul> |
| Comparar componentes | <ul><li>Comparar</li><li>VS</li><li>Contraste</li><li>Semana a semana</li><li>Mês a mês</li><li>Trimestre a trimestre</li><li>Ano por ano</li></ul> |
| Visualização de rosca | <ul><li>Proporção</li><li>Compartilhamento de</li><li>Distribuição</li><li>Porcentagem</li><li>Contribuição</li><li>Parte</li><li>Partes</li></ul> |
| Visualização de linha | <ul><li>Tendência</li><li>[Métrica] em [Intervalo de tempo]</li></ul> |
| Visualização de barra | <ul><li>[Métrica] de [Dimension]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->


## Práticas recomendadas de configuração

Abaixo estão as práticas recomendadas para a configuração do Customer Journey Analytics (visualização de dados, métricas calculadas, segmentos e muito mais) para garantir que o Data Insights Agent possa localizar os componentes corretos e retornar respostas mais limpas sem precisar solicitar informações adicionais.

* **Equilibre quais componentes são necessários**. Não adicione todos os campos dos conjuntos de dados como métricas ou componentes de dimensão à visualização de dados, especialmente aqueles que você não espera usar na análise. Por outro lado, não se limite estritamente apenas aos campos que você antecipa que são necessários para a análise. Uma visualização de dados muito limitada restringe a flexibilidade da análise e da funcionalidade do Data Insights Agent.
* **Sempre usar nomes para exibição amigáveis**. Certifique-se de que todos os campos definidos na visualização de dados, como uma métrica ou componente de dimensão, tenham um nome de componente amigável. O processo de renomear campos com um nome amigável é especialmente relevante para campos de conjuntos de dados do conector de origem do Adobe Analytics. These fields often have non-friendly unidentifiable names, like `eVar41` or `prop25`.
* **Use distinctive names**. Distinctive names are especially relevant when you use the same field as both a metric and a dimension component in your data view. Or when you use a field in multiple components of the same type (such as in two different metrics), each with different component settings.
* **Use a component naming convention**. You can use a component naming convention to group components. For example, **[!UICONTROL Orders | Product]** and  **[!UICONTROL Orders | Customer]** can distinguish between different order metrics that might exist in your data.
* **Use the Data Dictionary**. Add descriptions and other relevant data for components in the Data Dictionary. The Data Insights Agent currently does not use description and tags from the Data Dictionary, but it might in the future.
* **Use approved calculated metrics**. Agree on a process to use only approved calculated metrics as components in your data view, and avoid using experimental calculated metrics.
* **Share required segments**. Ensure that you share segments and make segments visible that are required for Data Insights Agent prompts.
* **Standardize on component names across data views**. If you use the same fields as a component in multiple data views, ensure that you use a single friendly name and a single identifier for that component. A single name and identifier allows the Data Insights Agent to switch data views without losing context.


>[!MORELIKETHIS]
>
>[Component settings](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/component-settings/overview)
>[Data Dictionary](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/data-dictionary/data-dictionary-overview)
>[Approve calculated metric](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-approving)
>[Share segments](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/segments/seg-share)
