---
title: Agente de descoberta de campo
description: Localize, avalie e selecione campos XDM no Adobe Experience Platform usando a linguagem natural no Assistente de IA, com resultados classificados, valores de amostra e contexto de uso para segmentação, consulta e fluxos de trabalho de dados.
keywords: descoberta de campo, XDM, Assistente de IA, agentes do Experience Platform, vinculação de entidades, recomendações de campo, criação de público-alvo, segmentação
solution: Experience Platform
role: User, Admin, Developer
source-git-commit: b4d8c83cca73a19e1fe229c8cec03caee16bcd8c
workflow-type: tm+mt
source-wordcount: '3525'
ht-degree: 0%

---

# Agente de descoberta de campo

Ao criar públicos-alvo ou integrar dados no Adobe Experience Platform, a identificação do campo XDM correto para um conceito de negócios geralmente requer a navegação manual em esquemas ou o conhecimento prévio de exatamente como um campo é nomeado. Campos diferentes podem representar o mesmo conceito com nomes diferentes, por exemplo, estado, região e local, e escolher o errado introduz erros em workflows downstream.

O Agente de descoberta de campo é um agente habilitado por IA na Adobe Experience Platform que ajuda a localizar, avaliar e selecionar campos XDM usando consultas de linguagem natural no Assistente de IA. Você descreve o que está procurando em linguagem simples (um conceito comercial, uma meta de fluxo de trabalho ou um nome de campo específico), e o agente retorna sugestões de campos classificados com contexto de suporte.

O Field Discovery Agent é chamado automaticamente em segundo plano no Assistente do AI quando outros agentes do Experience Platform precisam resolver referências de campo ou de entidade. Nesses casos, ele opera em segundo plano para melhorar a precisão do agente com o qual você está trabalhando. Quando precisar de uma descoberta de campo para seu próprio trabalho, escreva um prompt de descoberta de campo explícito no Assistente do AI. O Agente de Descoberta de Campo só exibe informações de campo. Ele não modifica esquemas, conjuntos de dados ou públicos-alvo e respeita os controles de acesso e o contexto da sandbox existentes.

## Quando usar isto {#when-to-use-this}

Use o Agente de descoberta de campo explicitamente no Assistente de IA quando precisar de sugestões de campos classificados, valores de exemplo e contexto de uso para um mapeamento, segmentação ou consulta. Ele é usado implicitamente quando outro agente do Experience Platform o chama em segundo plano para resolver referências de campo ou de entidade. Nesses casos, você permanece no fluxo de trabalho desse agente e não emite um prompt de descoberta de campo separado.

## Pré-requisitos {#prerequisites}

Para usar o Field Discovery Agent, verifique se você tem o seguinte:

- Acesso ao Adobe Experience Platform e ao Assistente de IA
- A organização e a sandbox corretas
- Acesso aos esquemas e conjuntos de dados que você pretende consultar

A familiaridade básica com esquemas XDM e como os campos são usados na segmentação ou em workflows de dados pode ajudar você a interpretar resultados com mais eficiência. Para obter mais informações, consulte a [visão geral do XDM](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home) e a [documentação do Editor de esquemas](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/create-schema-ui).

Para obter instruções sobre como habilitar o acesso ao Assistente de IA e conceder as permissões necessárias, consulte o [guia de acesso do Agent Orchestrator](./agent-orchestrator.md#access).

## Funções do agente de detecção de campo {#field-discovery-agent-functions}

O Field Discovery Agent processa sua consulta e retorna um dos três tipos de saída, dependendo de sua intenção. Essas funções refletem como o agente interpreta sua consulta; você não as seleciona. O agente determina automaticamente o tipo de resposta apropriado com base no que você descreve.

| Função | Descrição | Saída esperada |
| --- | --- | --- |
| **Identificação** | Identifica campos XDM que correspondem semanticamente a um conceito ou atributo de negócios descrito na linguagem natural. | Uma lista classificada de campos candidatos com rótulos de relevância, caminhos de campo e links de Contextos de uso. |
| **Recomendação** | Recomenda campos XDM com base em uma meta de fluxo de trabalho ou caso de uso descrito, como criar um segmento de público-alvo ou modelar um atributo comportamental. | Uma lista priorizada de campos relevantes para a meta declarada, com contexto de relevância para cada um. |
| **Enriquecimento** | Retorna o contexto detalhado de um campo específico, incluindo valores de amostra, localização do esquema e onde o campo é usado em conjuntos de dados, públicos-alvo e destinos. | Detalhes do campo, incluindo valores de amostra, caminho do esquema, conjuntos de dados associados e uso de público-alvo ou destino. |

## Como o Field Discovery Agent funciona {#how-field-discovery-agent-works}

Em um alto nível, o agente interpreta sua intenção, pesquisa seus dados disponíveis e classifica os resultados por relevância. A forma como o query é formulado afeta diretamente cada estágio, o que, por sua vez, afeta a qualidade dos resultados.

Quando você envia uma consulta no Assistente de IA, o Agente de descoberta de campo processa sua solicitação em três estágios:

| Preparo | Descrição |
|------|-------------|
| **Interpretação de intenção** | O agente lê sua entrada de linguagem natural e identifica o conceito ou objetivo subjacente. Por exemplo, uma consulta sobre &quot;pessoas na Califórnia&quot; é interpretada como uma solicitação de atributo geográfico, não como uma correspondência de sequência literal. O agente mapeia sua frase para conceitos semanticamente equivalentes que podem aparecer sob nomes diferentes em seus esquemas. |
| **Escopo da pesquisa** | O agente pesquisa os esquemas XDM, conjuntos de dados e metadados de campo disponíveis em sua organização IMS atual e sandbox. Ele considera nomes de campo, nomes de exibição, descrições e associações de uso para encontrar candidatos que se alinhem à sua intenção. |
| **Classificação** | O agente classifica os resultados por relevância semântica — a proximidade com que um campo corresponde à sua intenção declarada — complementada por sinais como integridade de metadados e uso de campo em todo o ecossistema de dados. Os campos com nomes descritivos, metadados preenchidos e uso confirmado em conjuntos de dados ativos são classificados acima dos campos que existem somente em uma definição de esquema. O agente não expõe os pesos específicos atribuídos a sinais individuais. |

## Entender os resultados {#understand-your-results}

O Field Discovery Agent retorna um conjunto de resultados estruturado para cada consulta. Compreender os componentes de um resultado ajuda a avaliar campos candidatos e agir com eles com confiança, sem tentativa e erro adicionais.

Trate um campo como pronto para uso quando seu rótulo **[!UICONTROL Relevância]** for **[!UICONTROL Altamente Relevante]**, seus valores de exemplo corresponderem aos dados esperados (quando disponíveis), e seus **[!UICONTROL Contextos de Uso]** estiverem alinhados com a maneira como você planeja usá-lo. Se os resultados forem apenas **[!UICONTROL Moderadamente Relevantes]** ou **[!UICONTROL Relevantes]**, os valores de exemplo não corresponderão às suas expectativas ou o contexto de uso será limitado, refine sua consulta e revise um novo conjunto de resultados antes de continuar.

### Rótulos de relevância

O Agente de Descoberta de Campos atribui um rótulo de relevância na coluna **[!UICONTROL Relevância]** do painel **[!UICONTROL Campos Identificados]** para cada resultado de campo, indicando a proximidade com que o campo corresponde à sua consulta.

- **[!UICONTROL Altamente Relevante]** — O campo corresponde fortemente ao conceito declarado com base no nome, metadados e sinais de uso. Confirme o caminho do campo e revise seus valores de amostra para verificar se ele contém os dados esperados.
- **[!UICONTROL Moderadamente Relevante]** — O campo tem sobreposição semântica parcial com sua consulta, mas pode diferir em escopo, tipo de dados ou especificidade. Revise os valores de amostra e o contexto de uso para determinar se ele atende às suas necessidades antes de selecioná-lo.
- **[!UICONTROL Relevante]** — O campo corresponde parcialmente à sua consulta. Ela pode compartilhar sobreposição semântica, mas difere em escopo, especificidade ou tipo de dados. Revise os valores de amostra e o contexto de uso antes de decidir se deseja usá-los.

Se todos os resultados forem rotulados como **[!UICONTROL Moderadamente Relevante]** ou **[!UICONTROL Relevante]** em vez de **[!UICONTROL Altamente Relevante]**, sua consulta poderá ser muito ampla ou usar terminologia que não corresponda aos seus metadados de esquema. Refine seu prompt com termos mais específicos de idioma ou domínio que refletem como os campos são nomeados.

### Valores de amostra

Juntamente com cada sugestão de campo, o Field Discovery Agent supera valores de amostra obtidos dos dados do campo na sandbox. Os valores de amostra ajudam a verificar se um campo contém o tipo de dados esperado antes de selecioná-lo.

>[!IMPORTANT]
>
>Os exemplos de valores podem conter PII. Não os compartilhe fora de workflows internos seguros.

Os valores de amostra são visíveis somente para campos nas permissões de acesso do conjunto de dados. Para obter informações sobre governança de dados e restrições de uso no Experience Platform, consulte a [visão geral sobre governança de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/home).

Se nenhum valor de amostra for exibido para um campo, ele poderá estar vazio na sandbox atual ou as permissões talvez não incluam acesso ao conjunto de dados subjacente. Campos com alta cardinalidade (como campos de identificador ou UUID) também podem não retornar valores de amostra representativos. Os valores de amostra são agregados e baseados em frequência e não são rastreáveis a perfis individuais.

### Contexto de uso

Cada resultado de campo inclui um contexto de uso que mostra onde o campo aparece em seu ecossistema de dados:

**Público-Alvo → Conjunto De Dados → Destino → Esquema**

Um campo usado em um público publicado, exibido em um conjunto de dados ativo, mapeado para um destino em tempo real e definido em um esquema demonstrou o uso real em seu ambiente. Isso distingue campos que são ativamente dependentes de campos que existem apenas em uma definição de esquema, mas que não foram usados na prática. Use esse sinal junto com o rótulo de relevância e valores de amostra para fazer uma seleção de campo mais informada.

### Resultados no Assistente de IA

O Agente de Descoberta de Campo retorna resultados em um painel **[!UICONTROL Campos Identificados]** na resposta do Assistente de IA. O painel exibe uma tabela com três colunas:

- **[!UICONTROL Nome do Campo]** — O caminho XDM do campo candidato.
- **[!UICONTROL Relevância]** — O rótulo de relevância atribuído ao campo (**[!UICONTROL Altamente Relevante]**, **[!UICONTROL Moderadamente Relevante]** ou **[!UICONTROL Relevante]**)
- **[!UICONTROL Contextos de Uso]** — Links que mostram onde o campo aparece em seu ecossistema de dados. Selecione **[!UICONTROL público-alvo]**, **[!UICONTROL conjunto de dados]**, **[!UICONTROL destino]** ou **[!UICONTROL esquema]** para abrir um painel lateral mostrando onde o campo é usado.

![O painel Campos Identificados no Assistente de IA que mostra linhas de campo candidatas com rótulos de Relevância e links de Contextos de Uso.](./images/field-discovery/fields-identified-panel-in-chat.png)

Uma seção **[!UICONTROL Resultados Explicados]** aparece abaixo da tabela **[!UICONTROL Campos Identificados]** e fornece contexto de campo adicional, incluindo explicações e detalhes de suporte para cada resultado. Para obter orientação sobre como navegar na interface do Assistente de IA, consulte o [Guia da interface do Assistente de IA](../ai-assistant/ai-assistant-ui.md).

## Usar agente de descoberta de campo {#use-field-discovery-agent}

Você interage com o Field Discovery Agent por meio do Assistente de IA usando linguagem natural. O agente requer uma declaração clara de intenção — uma consulta vaga ou muito breve produz resultados de qualidade inferior ou não pode invocar o Field Discovery Agent.

Para a descoberta de campo explícito, siga este fluxo de trabalho: identifique o problema de atributo ou mapeamento, envie uma consulta de descoberta de campo, revise os resultados classificados e o contexto de uso no painel **[!UICONTROL Campos Identificados]**, selecione o caminho **[!UICONTROL Nome do Campo]** que se ajuste à sua intenção e aplique esse caminho XDM no Construtor de Segmentos, no Serviço de Consulta ou em outro fluxo de trabalho.

Para usar o Field Discovery Agent:

1. Navegue até o **[!UICONTROL Assistente de IA]** de qualquer aplicativo habilitado do Experience Platform. O espaço de trabalho **[!UICONTROL Assistente de IA]** é exibido.
2. Informe a intenção explicitamente no campo de entrada. Descreva o conceito, a meta ou a característica de campo que você está procurando. Por exemplo: *&quot;Localizar campos relacionados ao status de recusa de email do cliente.&quot;*
3. Revise os resultados classificados no painel **[!UICONTROL Campos Identificados]**. Cada linha inclui um rótulo de relevância e um caminho de campo XDM na coluna **[!UICONTROL Nome do Campo]**.
4. Selecione **[!UICONTROL público-alvo]**, **[!UICONTROL conjunto de dados]**, **[!UICONTROL destino]** ou **[!UICONTROL esquema]** na coluna **[!UICONTROL Contextos de Uso]** para abrir um painel lateral mostrando onde o campo é usado. Para contexto adicional em nível de campo, consulte a seção **[!UICONTROL Resultados Explicados]** abaixo da tabela de resultados.

   ![O painel lateral no Assistente de IA mostra os Contextos de Uso de um campo selecionado, incluindo as associações de público-alvo, conjunto de dados, destino e esquema.](./images/field-discovery/fields-identified-panel-expanded.png)

5. Use o caminho **[!UICONTROL Nome do campo]** em ferramentas de downstream, como o Construtor de segmentos, o Serviço de consulta ou os fluxos de trabalho de assimilação de dados, dependendo do seu caso de uso. O Field Discovery Agent fornece a referência de campo, mas não a insere em outras ferramentas.

Se necessário, selecione a lista suspensa **[!UICONTROL Raciocínio concluído]** acima da resposta para confirmar se o Agente de Descoberta de Campo tratou sua solicitação. A lista suspensa exibe detalhes de raciocínio que indicam qual agente foi chamado.

>[!NOTE]
>
>Se o painel de raciocínio não indicar o Agente de descoberta de campo, a consulta pode não ter contido uma intenção clara de descoberta de campo. Repita sua consulta com linguagem de localização de campo explícita e envie novamente. Consulte [Solução de problemas](#troubleshooting) para obter informações sobre problemas comuns de invocação.

Para obter orientação sobre a interface do Assistente de IA, consulte o [Guia da interface do Assistente de IA](../ai-assistant/ai-assistant-ui.md).

## Casos de uso aceitos {#supported-use-cases}

As seções a seguir descrevem cada uma das três funções do Field Discovery Agent com cenários representativos e prompts de exemplo. Os resultados incluem rótulos de relevância e contexto de uso para ajudar a avaliar campos. Para interpretação dos resultados, consulte [Entender seus resultados](#understand-your-results). O Field Discovery Agent retorna somente informações de campo — não cria públicos-alvo, executa consultas ou envia dados para outras ferramentas. Após identificar um campo, leia seu caminho XDM na coluna **[!UICONTROL Nome do Campo]** e use-o no fluxo de trabalho downstream.

### Identificar campos para um conceito de negócios

Quando você descreve um conceito ou atributo de dados específico, o Field Discovery Agent retorna uma lista classificada de campos que semanticamente correspondem à sua descrição.

> &quot;Quais campos representam o estado ou província residencial de um cliente?&quot;
> &quot;Localizar campos relacionados à data da transação de compra.&quot;
> &quot;Quais campos contêm informações sobre consentimento de marketing por email?&quot;

A resposta lista os campos candidatos com seu rótulo de relevância e caminho XDM no painel **[!UICONTROL Campos Identificados]**. Os campos rotulados como **[!UICONTROL Altamente Relevantes]** correspondem mais ao conceito declarado. Se os principais resultados estiverem rotulados como **[!UICONTROL Moderadamente Relevante]** ou **[!UICONTROL Relevante]** em vez de **[!UICONTROL Altamente Relevante]**, refine sua consulta usando a terminologia mais específica ou o contexto de nível de campo.

### Obter recomendações de campo para um caso de uso

Ao descrever uma meta de fluxo de trabalho ou caso de uso (como criar um segmento, integrar um conjunto de dados ou preparar um query), o Field Discovery Agent recomenda campos alinhados a esse objetivo, priorizados por relevância.

> &quot;Quero construir um público-alvo de clientes de alto valor. Quais campos devo usar?&quot;
> &quot;Campos recomendados para modelar a propensão para compras.&quot;
> &quot;Quais campos devo incluir ao integrar um conjunto de dados de transações de varejo?&quot;

A resposta retorna uma lista priorizada de campos com contexto de relevância. Revise o contexto de uso de cada campo recomendado para confirmar se ele é usado ativamente em seu ambiente.

### Enriquecer contexto de campo

Quando você pergunta sobre um campo específico por nome ou caminho, o Agente de descoberta de campo retorna o contexto detalhado desse campo, incluindo valores de amostra, localização do esquema e uso em conjuntos de dados, públicos e destinos.

> &quot;Conte-me mais sobre o campo `person.name.lastName`.&quot;
> &quot;Quais valores de exemplo existem para `homeAddress.stateProvince`?&quot;
> &quot;Onde o campo `commerce.purchases.value` é usado em meus conjuntos de dados e públicos?&quot;

A resposta retorna os valores de amostra do campo, o local do esquema, os conjuntos de dados associados e quaisquer públicos ou destinos em que o campo aparece. Revise este contexto para confirmar se o campo contém os dados esperados.

## Dentro e fora do escopo {#in-scope-and-out-of-scope}

Esta seção resume o que o Field Discovery Agent pode ou não fazer. Para obter orientações detalhadas sobre tarefas, consulte [Casos de uso com suporte](#supported-use-cases). Para restrições de plataforma, consulte [Medidas de proteção e limitações](#guardrails-and-limitations).

### No escopo

A lista a seguir descreve as tarefas que o Agente de descoberta de campo pode executar; use-a para confirmar se o agente pode atender à sua solicitação antes de confiar nela no fluxo de trabalho.

- Identificação de campos XDM que correspondem a um conceito comercial ou descrição em linguagem natural.
- Recomendar campos para uma meta de fluxo de trabalho ou caso de uso declarado.
- Enriquecimento de um campo específico com valores de amostra, localização do esquema e contexto de uso.
- Retornando resultados classificados por relevância semântica, rotulados como Altamente relevante, Moderadamente relevante ou Relevante.
- Exibição de valores de amostra nas permissões autorizadas do conjunto de dados.

### Fora do escopo

A lista a seguir descreve as ações que o Field Discovery Agent não executa; use-as para evitar depender do agente para trabalhar fora de seu escopo.

- Modifique esquemas, conjuntos de dados, campos ou públicos.
- Crie ou publique públicos ou segmentos.
- Execute queries ou ative dados para destinos.
- Acesse campos ou conjuntos de dados fora das permissões autorizadas.
- Exponha a lógica de incorporação interna, a arquitetura de banco de dados vetorial ou os detalhes de implementação de vinculação de entidade.
- Garanta uma janela de tempo específica para atualizações da base de dados de conhecimento após alterações no esquema ou no conjunto de dados.

## Medidas de proteção e limitações {#guardrails-and-limitations}

Essas medidas de proteção são importantes porque o Field Discovery Agent opera dentro de restrições no nível da plataforma que afetam a disponibilidade e a qualidade do resultado. Use-os para interpretar resultados ausentes, atrasados ou incompletos e para solucionar falhas inesperadas com expectativas realistas.

### Knowledge base

O Field Discovery Agent depende de uma base de conhecimento atualizada periodicamente com esquema e metadados de seu ambiente Experience Platform. Os resultados refletem o estado da base de conhecimento no momento da consulta, não o estado em tempo real dos esquemas, e pode haver um atraso entre a assimilação de dados e quando ela é exibida no agente.

Novos esquemas, campos ou conjuntos de dados adicionados ao seu ambiente podem não aparecer nos resultados do Agente de descoberta de campo imediatamente. Os resultados podem levar tempo para refletir as alterações recentes.

>[!NOTE]
>
>O intervalo de atualização da base de dados de conhecimento está sujeito a alterações. Se um campo adicionado recentemente não aparecer nos resultados, aguarde um tempo para que a knowledge base atualize e reenvie sua consulta.

### Qualidade e cobertura dos metadados

A qualidade do resultado depende da qualidade e da integridade dos metadados de campo no ambiente do Experience Platform. O agente usa nomes de campo, nomes de exibição, descrições e associações de uso para classificar os resultados. Campos com metadados insuficientes ou ausentes podem não aparecer nos resultados ou podem ser classificados abaixo do esperado.

Se você tiver acesso para edição de esquemas, poderá melhorar a qualidade dos resultados ao:

- Usando nomes de exibição claros e descritivos para campos em seus esquemas.
- Adicionar descrições de campo sempre que possível.
- Associar campos a conjuntos de dados ativos em vez de deixá-los como definições somente de esquema.

Para obter orientação sobre como editar nomes para exibição de campo e descrições no Editor de Esquemas, consulte [Criar e editar esquemas na interface](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/resources/schemas).

Se você não tiver acesso para edição de esquemas e os resultados forem consistentemente ruins, entre em contato com o administrador do Experience Platform ou com a equipe de engenharia de dados para revisar os metadados de campo dos esquemas com os quais você trabalha.

### Restrições de acesso e PII

O Field Discovery Agent respeita todos os controles de acesso existentes do Experience Platform e opera em seu contexto atual de sandbox. Você recebe resultados apenas para campos em esquemas e conjuntos de dados aos quais você está autorizado a acessar.

Os valores de amostra são regidos pelas mesmas permissões no nível do conjunto de dados. Os campos em conjuntos de dados habilitados para perfil com restrições de PII retornam valores de amostra somente se você tiver o acesso necessário. Consulte [Valores de exemplo](#sample-values) para obter orientação sobre como manusear. O Agente de descoberta de campo não ignora a segurança em nível de campo nem as restrições de acesso ativadas por perfil.

## Práticas recomendadas {#best-practices}

Use as orientações a seguir para obter resultados precisos e acionáveis do Field Discovery Agent.

- **Seja específico sobre o conceito, não apenas sobre o tipo de campo.** Um prompt como &quot;localizar um campo de estado&quot; produz resultados de qualidade inferior a &quot;localizar o campo que contém o estado de um cliente nos EUA para segmentação geográfica&quot;. A especificidade dá ao agente mais sinal para corresponder aos seus metadados. Consulte [Como o Field Discovery Agent funciona](#how-field-discovery-agent-works) para saber por que isso é importante.
- **Use a terminologia que corresponde aos seus metadados de esquema.** Se seus esquemas usarem o termo &quot;transação&quot; em vez de &quot;compra&quot;, use &quot;transação&quot; em seus prompts. O agente corresponde aos nomes e às descrições dos campos reais, não apenas aos conceitos gerais.
- **Verifique os campos antes de confirmar.** Depois de encontrar campos candidatos, pergunte sobre um campo específico por nome ou caminho para revisar seus valores de amostra e contexto de uso antes de usá-lo em um segmento ou consulta. Isso reduz o risco de selecionar o campo errado.
- **Repita quando os resultados forem Moderadamente Relevantes ou Relevantes em vez de Altamente Relevantes.** Reescreva sua consulta com terminologia diferente ou adicione mais contexto sobre seu caso de uso. Uma segunda consulta, mais específica, geralmente apresenta melhores candidatos.
- **Incluir contexto de escopo em seus prompts.** Para a segmentação com base geográfica, inclua a região do target. Para consultas baseadas em tempo, inclua o atributo tempo. Quanto mais contexto você fornecer, mais direcionada será a classificação do resultado.

## Exemplo de prompts {#example-prompts}

Use esta seção como uma biblioteca de prompts de referência rápida. Se você nunca usou o Field Discovery Agent, leia [Práticas recomendadas](#best-practices) e [Casos de uso com suporte](#supported-use-cases) primeiro para entender quando e por que cada função se aplica.

### Prompts de identificação

Use esses prompts quando você souber o conceito de dados necessário, mas não saber qual campo o contém.

> &quot;Qual campo contém o estado ou a região de um cliente?&quot;
> &quot;Localizar campos relacionados ao status da assinatura de email.&quot;
> &quot;Qual campo contém a data da primeira compra de um cliente?&quot;
> &quot;Identifique campos que representam o valor vitalício do cliente.&quot;
> &quot;Quais campos no meu esquema de perfil estão relacionados à associação ao programa de fidelidade?&quot;

### Prompts de recomendação

Use esses prompts quando estiver iniciando um workflow e precisar de orientação sobre quais campos incluir para uma meta específica.

> &quot;Quais campos devo usar para criar um público-alvo de reengajamento?&quot;
> &quot;Campos recomendados para um público-alvo direcionado a clientes que não compraram em 90 dias.&quot;
> &quot;Quais campos são mais úteis para modelar o risco de churn?&quot;
> &quot;Sugerir campos que devo incluir ao criar uma segmentação geográfica.&quot;
> &quot;Estou construindo um modelo de propensão à compra. Com quais campos devo começar?&quot;

### Prompts de enriquecimento

Use esses prompts quando tiver um campo candidato e quiser verificá-lo antes de usá-lo em um segmento, consulta ou mapeamento.

> &quot;Conte-me mais sobre `homeAddress.stateProvince`.&quot;
> &quot;Mostrar valores de exemplo para `commerce.purchases.value`.&quot;
> &quot;Onde o `person.name.lastName` é usado em meus conjuntos de dados e públicos-alvo?&quot;
> &quot;Quais conjuntos de dados contêm o campo `web.webPageDetails.URL`?&quot;
> &quot;`segmentMembership` está mapeado para algum destino ativo?&quot;

## Solução de problemas {#troubleshooting}

Use esta seção quando os resultados estiverem ausentes, inesperados ou quando você não tiver certeza se o Agente de Descoberta de Campo tratou sua solicitação.

- **Um campo adicionado recentemente não aparece nos resultados.** A base de dados de conhecimento pode ainda não refletir o novo esquema ou campo. Permita que a base de conhecimento atualize depois de adicionar esquemas ou campos ao seu ambiente e, em seguida, reenvie sua consulta. Consulte [Knowledge base](#knowledge-base).

- **Todos os resultados são rotulados como Moderadamente Relevantes ou Relevantes em vez de Altamente Relevantes.** Sua consulta pode ser muito ampla ou a terminologia usada pode não corresponder aos metadados do campo. Refine seu prompt com idioma ou termos mais específicos que se alinham com a maneira como seus campos são nomeados em seus esquemas. Consulte [Práticas recomendadas](#best-practices).

- **O Field Discovery Agent não foi invocado.** Você enviou uma consulta no Assistente de IA, mas o painel **[!UICONTROL Raciocínio concluído]** não indica o Agente de Descoberta de Campo. Sua consulta pode não ter contido uma intenção de descoberta de campo não criptografado. Repita o query explicitamente, por exemplo, &quot;Encontrar o campo com o status de não participação de email do cliente&quot;, e envie novamente. Consulte [Usar Agente de Descoberta de Campo](#use-field-discovery-agent).

- **Os valores de exemplo não aparecem para um campo.** O campo pode estar vazio na sandbox atual, suas permissões podem não incluir acesso ao conjunto de dados subjacente ou o campo pode ter alta cardinalidade (como um campo de ID) para o qual os valores de amostra não são mostrados. Confirme suas permissões de acesso ao conjunto de dados e verifique se o campo está preenchido com dados. Consulte [Restrições de acesso e PII](#access-and-pii-constraints).

- **Os resultados incluem campos de esquemas que você não esperava.** O Field Discovery Agent pesquisa todos os esquemas e conjuntos de dados na sandbox atual que estejam acessíveis sob suas permissões. Se resultados inesperados forem exibidos, confirme seu contexto de sandbox ativo no Assistente de IA e verifique quais esquemas e conjuntos de dados estão acessíveis para sua função.

Para verificar qual agente manipulou sua solicitação, consulte a etapa 6 em [Usar o Agente de Descoberta de Campo](#use-field-discovery-agent).
