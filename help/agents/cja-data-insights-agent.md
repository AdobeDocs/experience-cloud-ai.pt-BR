---
description: Saiba como visualizar dados com o Data Insights Agent no Customer Journey Analytics
title: Visualizar dados com a Data Insights Agent no Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
source-git-commit: 0e366e182cfccf2c081f6e5689c02b650148a7b9
workflow-type: tm+mt
source-wordcount: '2497'
ht-degree: 5%

---

# Visualizar dados com o Data Insights Agent

>[!AVAILABILITY]
>
>O Data Insights Agent está disponível para clientes qualificados por um período limitado. O acesso ao Data Insights Agent terminará em 28 de fevereiro de 2026. Para continuar usando o Data Insights Agent sem interrupção, entre em contato com o representante de conta da Adobe para saber mais sobre como licenciar o Data Insights Agent.

O Data Insights Agent, acessível pelo [Assistente de IA](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/ai-assistant) no Customer Journey Analytics, é um agente de conversação de IA generativo que responde de forma rápida e eficiente a perguntas sobre seus dados. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e seus dados reais.

Usar o Data Insights Agent para responder perguntas centradas em dados no Analysis Workspace pode economizar inúmeras horas que, de outra forma, você poderia gastar criando visualizações manualmente no Analysis Workspace e se familiarizando com seus componentes de visualização de dados.

![Data Insights Agent no Assistente de IA](images/cja-agent//cja-ai-asst-da.gif)

## Recursos dentro e fora do escopo

| Recurso | No escopo | Fora do escopo |
| --- | --- | --- |
| **Tipos de visualização** | <ul><li>Linha</li><li>Várias linhas</li><li>Tabela de forma livre</li><li>Barra</li><li>Rosquinha</li><li>Número do resumo</li></ul> | <ul><li>Fluxo</li><li>Fallout</li><li>Tabela de coorte</li><li>Área, Área empilhada</li><li>Barra empilhada</li><li>Marcador</li><li>Combo</li><li>Histograma</li><li>Barra horizontal, Barra horizontal empilhada</li><li>Resumo da métrica principal</li><li>Dispersão</li><li>Alteração de resumo</li><li>Texto</li><li>Mapas de árvore</li><li>Venn</li><li>Análise guiada: Crescimento ativo, Tendências de conversão, Envolvimento, Impacto na primeira utilização, Frequência, Funnel, Crescimento líquido, Impacto na versão, Retenção, Linha do tempo, Tendências</li></ul> |
| **Ações do Workspace e recursos do agente** | <ul><li>Criar e atualizar visualizações<p>Gera uma tabela de forma livre e uma visualização associada (como uma linha, barra, rosca e assim por diante).<p>Por exemplo, *Qual é o lucro entre SKUs de fevereiro a maio?*</p></li><li>Fazer perguntas de acompanhamento<p>Responder a um prompt no contexto de qualquer prompt anterior. Por exemplo:</p> <ul><li>Prompt 1: *Eventos de tendência de março.*</li><li>Prompt 2: *Mostrar os dados de março a abril*</li></ul> </li><li>Detecção de prompt fora do escopo<p>Se você enviar um prompt que está fora do escopo, como *Exportar este projeto*, a Data Insights Agent responderá informando que a pergunta está fora do escopo.</p></li></ul> | <ul><li>Compartilhar</li><li>Exportar</li><li>Baixar</li><li>Gerenciar preferências do usuário</li><li>Gerenciar visualização de dados</li><li>aplicativo Painéis do Analytics</li><li>Atribuição</li><li>Resumo ou resposta em linha<p>O Data Insights Agent não pode responder embutido no painel de chat com uma resposta resumida de um prompt do usuário. Exemplos de prompts fora do escopo são: *Dê-me um resumo dos insights do meu último prompt* e *Resumir os destaques da visualização de linha.*</p></li></ul> |
| **Esclarecimento de questões** | Se você fizer uma pergunta que não tenha contexto suficiente para o Data Insights Agent responder, ou que seja muito genérica, o Data Insights Agent responderá com uma pergunta esclarecedora ou com opções sugeridas. <p>As seguintes perguntas de esclarecimento são exemplos de perguntas relacionadas a componentes:</p><ul><li>Métrica: *Qual métrica de &quot;receita&quot; você quis dizer?*</li><li>Dimension: *Em qual das &quot;regiões&quot; abaixo você deseja se concentrar?*</li><li>Segmento: *Que segmento de &quot;Conta&quot; você deseja aplicar?*</li><li>Intervalo de datas: *Por &quot;último mês&quot;, você quis dizer o último mês completo ou os últimos 30 dias?*</li></ul><p>A pergunta esclarecedora a seguir é um exemplo de uma pergunta relacionada a itens de dimensão:</p> <ul><li>Que &quot;nome da loja&quot; você quis dizer? (Por exemplo, Armazenar #5274, Armazenar #2949 e assim por diante.)</li></ul> | As perguntas de esclarecimento estão limitadas a componentes e itens de dimensão. O Data Insights Agent não pode esclarecer aspectos como visualizações de dados, visualizações, granularidade de dados, comparação e escopo. Quando o esclarecimento de dúvidas não puder ser usado, o agente assumirá como padrão o que você provavelmente está solicitando. Se retornar uma visualização ou granularidade de dados inesperada, você poderá fazer uma pergunta complementar ou ajustar a visualização e os dados. |
| **Verificabilidade e correção de dados** | A verificabilidade e a correção dos dados podem ser confirmadas visualizando-se a tabela de forma livre gerada e a visualização de dados. <p>Por exemplo, se você pedir à Data Insights Agent para *Fazer tendência de pedidos no mês passado*, será possível confirmar se a métrica (&quot;pedidos&quot;) e o intervalo de datas (&quot;mês passado&quot;) corretos foram selecionados no painel recém-gerado, na visualização de dados e na tabela de forma livre. | O Data Insights Agent não responde informando quais componentes ou visualizações foram adicionados.</p> |
| **Mecanismos de feedback** | <ul><li>Polegar para cima</li><li>Polegar para baixo</li><li>Sinalizar</li></ul> |  |


## Gerenciar acesso ao Data Insights Agent {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="Habilitar para o Data Insights Agent"
>abstract="Essa opção habilita essa visualização de dados para uso com o Data Insights Agent. O Data Insights Agent é um agente de conversação de IA generativa acessível pelo Assistente de IA no Customer Journey Analytics. Ele ajuda a analisar rapidamente os dados com prompts de texto. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e seus dados reais."

<!-- markdownlint-enable MD034 -->

Os seguintes parâmetros regulam o acesso ao Data Insights Agent no Customer Journey Analytics:

* **Acesso à solução**: o Data Insights Agent estará disponível para todos os clientes da Customer Journey Analytics como parte de um programa de acesso limitado até 30 de novembro de 2025. Não está disponível no Adobe Analytics.

* **Acesso contratual**: se você não conseguir usar o Data Insights Agent no Assistente de IA, entre em contato com o administrador da organização ou com a equipe de conta da Adobe. Antes de sua organização poder usar o Data Insights Agent, você deve concordar com determinados termos legais relacionados à IA gerativa.

* **Permissões**: as permissões necessárias devem ser concedidas no [!UICONTROL Adobe Admin Console] para que os usuários possam acessar o Data Insights Agent.

  Para conceder permissões, um [administrador do perfil de produto](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) deve concluir as seguintes etapas no [!UICONTROL Admin Console]:

   1. Na **[!UICONTROL Admin Console]**, selecione a guia **[!UICONTROL Produtos]** para exibir a página **[!UICONTROL Todos os produtos e serviços]**.
   1. Selecione **[!UICONTROL Customer Journey Analytics]**.
   1. Na guia **[!UICONTROL Perfis de produto]**, selecione o título do perfil de produto para o qual você deseja fornecer acesso ao [!UICONTROL Assistente de IA: Conhecimento do Produto].
   1. No perfil de produto específico, selecione a guia **[!UICONTROL Permissões]**.

      ![Guia Permissões no Admin Console](images/cja-agent/ai-assistant-permissions-tab.png)

   1. Na linha **[!UICONTROL Ferramentas de Relatório]** da tabela fornecida, selecione o ícone de edição ![Editar](images/cja-agent/Edit.svg).
   1. Role até ou pesquise por **[!UICONTROL Assistente de IA: Conhecimento do Produto]** e selecione o ícone de adição ![AddCircle](images/cja-agent/AddCircle.svg) ao lado dessa permissão.
   1. Role até ou pesquise por **[!UICONTROL Data Insights Agent]** e selecione o ícone de adição ![AddCircle](images/cja-agent/AddCircle.svg) ao lado dessa permissão.

      A permissão **[!UICONTROL Assistente de IA: Conhecimento do Produto]** e a permissão **[!UICONTROL Data Insights Agent]** são adicionadas à coluna **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicionar permissão](images/cja-agent/ai-assistant-permissions.png).

   1. Selecione **[!UICONTROL Salvar]** para salvar as permissões.

  Para obter informações adicionais sobre o controle de acesso, consulte [Controle de acesso](https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/access-control#access-control).

* **Acesso à visualização de dados**: as visualizações de dados devem ser habilitadas para o Data Insights Agent.

  >[!IMPORTANT]
  >
  >Considere o seguinte ao ativar as visualizações de dados:
  >* É possível habilitar no máximo 50 visualizações de dados por organização IMS. Se você habilitar mais de 50 visualizações de dados em todos os perfis de produto para uma determinada organização, a Data Insights Agent usará as 50 visualizações de dados mais usadas.
  >* A Data Insights Agent pode fazer referência às visualizações de dados incluídas em algum momento durante o mesmo dia em que você as ativa.

  Para ativar visualizações de dados para o Data Insights Agent:

   1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]**.
   1. Selecione uma ou mais visualizações de dados que você deseja habilitar para o Data Insights Agent e selecione **[!UICONTROL Habilitar para o Data Insights Agent]**.

      ![Habilitar visualizações de dados para o Data Insights Agent](images/cja-agent/data-view-enable-dia.png)

  Para exibir o número de visualizações de dados habilitadas para o Data Insights Agent em sua organização IMS:

   1. No Customer Journey Analytics, selecione **[!UICONTROL Gerenciamento de dados]** > **[!UICONTROL Visualizações de dados]**.
   1. Selecione o ícone de informações na parte superior da coluna **[!UICONTROL Data Insights Agent]**.

      ![ícone de informações do Data Insights Agent](images/cja-agent/data-insights-agent-tooltip.png)

## Acessar o Data Insights Agent no Assistente de IA

1. Acesse [experience.adobe.com](https://experience.adobe.com/) e faça logon com sua Adobe ID.
1. Selecione **Customer Journey Analytics** na página inicial da Experience Cloud.
1. Selecione **[!UICONTROL Projeto em branco]** no banner na parte superior da página de projetos para abrir um novo projeto em branco.
1. Verifique se o modo de exibição de dados selecionado para o painel é um modo de exibição de dados habilitado para uso com o Data Insights Agent, conforme descrito em [Gerenciar acesso ao Data Insights Agent no Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).
1. Selecione o ícone de chat do Assistente do AI na área superior direita da página.

   Se você não vir o ícone de bate-papo, entre em contato com o administrador para que ele possa habilitar os seguintes recursos no Admin Console:

   * Ferramentas de Relatório: **[!UICONTROL Assistente de IA: Conhecimento do Produto]**
   * Ferramentas de Visualização de Dados: **[!UICONTROL Data Insights Agent]**

   Para obter detalhes adicionais, consulte [Gerenciar acesso ao Data Insights Agent no Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![Ícone do Assistente de IA](images/cja-agent/ai-asst-icon.png)

1. Na caixa de diálogo **[!UICONTROL Perguntar sobre o Customer Journey Analytics]**, na parte inferior da página, faça uma pergunta sobre visualização de dados usando o Data Insights Agent.

   Para obter mais informações, consulte os exemplos a seguir.

### Exemplo 1

Por exemplo, digamos que você esteja interessado nos pedidos que sua empresa recebeu em julho.

**Aviso:** Insira *&quot;Pedidos de tendência em julho.&quot;*

![Solicitação de IA](images/cja-agent/ai-asst-prompt1.png)

**Resposta:** o Data Insights Agent coleta informações verificando os dados na exibição de dados, incluindo as métricas e os componentes. Ele traduz o prompt para as dimensões e métricas certas no intervalo de dados.

Como você pode ver, ele gerou automaticamente um gráfico de linhas e uma tabela de forma livre para mostrar os pedidos de julho.

![Responder ao prompt - gráfico de linhas e tabela de forma livre](images/cja-agent/ai-asst-result.png)

### Exemplo 2

Em seguida, você deseja ver a comparação de receita por região.

**Prompt:** Na janela de prompt, digite *&quot;Mostrar receita por região.&quot;*

**Resposta:** a Data Insights Agent entende de forma inteligente que, por &quot;região&quot;, você quer dizer &quot;região do cliente&quot;. Ele produz um gráfico de barras que melhor mostra a receita por região:

![Gráfico de barras](images/cja-agent/ai-asst-result2.png)

### Exemplo 3

Em seguida, além de entender a receita por região, você também deseja ver os dados para lucro por região. Em vez de repetir o prompt anterior, você pode solicitar que o Data Insights Agent atualize a visualização mais recente e a tabela de forma livre.

**Prompt:** Na janela de prompt, digite *&quot;Adicionar lucro.&quot;*

**Resposta:** O gráfico de **[!UICONTROL Barra]** ainda fornece a resposta mais concisa, mas a métrica de lucro foi adicionada como uma coluna na tabela de forma livre:

![Gráfico de barras](images/cja-agent/ai-asst-result4.png)

### Exemplo 4

Por fim, vamos analisar a receita por categoria de produto.

**Prompt:** Na janela do prompt, digite *&quot;Proporção da receita por categoria do produto.&quot;*

**Resposta:** Novamente, o Data Insights Agent escolhe a visualização mais apropriada, neste caso a visualização **[!UICONTROL Rosca]**, para responder à pergunta.

![Rosquinha](images/cja-agent/ai-asst-result3.png)

## Acessar o Data Insights Agent em aplicativos Experience Cloud

O Adobe Experience Platform Agent Orchestrator permite acessar a funcionalidade do Data Insights Agent em vários aplicativos da Adobe Experience Cloud, como o Adobe Journey Optimizer e o Real-Time CDP.

O Agent Orchestrator interpreta sua solicitação, determina quais agentes especializados são necessários e os coordena para fornecer a resposta correta. Ela rastreia o contexto em interações de várias voltas, para que você possa criar consultas anteriores naturalmente.

Para obter mais informações, consulte [Adobe Experience Platform Agent Orchestrator](/help/agents/agent-orchestrator.md).

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

Esses exemplos foram projetados para ajudá-lo a se familiarizar com a forma como palavras ou estruturas específicas podem influenciar a saída do Agente do Data Insight, garantindo insights mais precisos e valiosos. O Data Insights Agent usa IA generativa, de modo que as visualizações ou os dados selecionados podem variar um pouco entre prompts semelhantes.

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

* **Equilibre quais componentes são necessários**. Não adicione todos os campos dos conjuntos de dados como métricas ou componentes de dimensão à visualização de dados. Especialmente, aqueles que você certamente não usará em sua análise. Por outro lado, não se limite estritamente apenas aos campos que você antecipa que são necessários para a análise. Uma visualização de dados muito limitada restringe a flexibilidade da análise e da funcionalidade do Data Insights Agent.
* **Sempre usar nomes para exibição amigáveis**. Certifique-se de que todos os campos definidos na visualização de dados, como uma métrica ou componente de dimensão, tenham um nome de componente amigável. O processo de renomear campos com um nome amigável é especialmente relevante para campos de conjuntos de dados do conector de origem do Adobe Analytics. Esses campos geralmente têm nomes não amigáveis não identificáveis, como `eVar41` ou `prop25`.
* **Usar nomes distintos**. Nomes distintos são especialmente relevantes quando você usa o mesmo campo como uma métrica e um componente de dimensão em sua visualização de dados. Ou quando você usa um campo em vários componentes do mesmo tipo (como em duas métricas diferentes), cada um com configurações de componente diferentes.
* **Usar uma convenção de nomenclatura de componente**. Você pode usar uma convenção de nomenclatura de componente para agrupar componentes. Por exemplo, **[!UICONTROL Pedidos | Produto]** e **[!UICONTROL Pedidos | O cliente]** pode distinguir entre métricas de ordem diferentes que podem existir em seus dados.
* **Usar o Dicionário de Dados**. Adicione a descrição e outros dados relevantes para os componentes no Dicionário de dados. Atualmente, o Agente de Insight de dados não usa a descrição e as tags do Dicionário de dados, mas pode ser que use no futuro.
* **Usar métricas calculadas aprovadas**. Concorde com um processo para usar somente métricas calculadas aprovadas como componentes em sua visualização de dados e evite usar métricas calculadas experimentais.
* **Compartilhar segmentos necessários**. Compartilhe segmentos e torne visíveis os segmentos necessários aos prompts do Data Insights Agent.
* **Padronizar nomes de componentes em visualizações de dados**. Se você usar os mesmos campos que um componente em várias visualizações de dados, certifique-se de usar um único nome simples e um único identificador para esse componente. Um único nome e identificador permite que o Data Insights Agent alterne as visualizações de dados sem perder o contexto.

>[!MORELIKETHIS]
>
>[Configurações de componente](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview)
>[Dicionário de Dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/data-dictionary/data-dictionary-overview)
>[Aprovar métrica calculada](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-approving)
>[Compartilhar segmentos](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/segments/seg-share)
