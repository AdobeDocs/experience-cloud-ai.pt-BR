---
title: Audience Agent
description: Saiba como usar o Audience Agent para criar públicos, exibir alterações de público, detectar públicos duplicados e exibir insights do público.
TQID: https://experienceleague.adobe.com/574QhqKI0YDoPHD9BFmB6jl-HET3zVom3eD4cJQABSE
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 1242
ht-degree: 2%

---

# Audience Agent

>[!AVAILABILITY]
>
>O Audience Agent está disponível para todos os clientes que têm acesso ao AI Assistant. No entanto, você precisará das seguintes permissões para usar totalmente os recursos do Audience Agent.
>
>**Exibir segmentos**: essa permissão permite que você use a Audience Agent para exibir insights sobre os públicos diretamente no Assistente de IA.
>
>**Gerenciar segmentos**: a permissão Para permite que você use a Audience Agent para criar novos públicos diretamente no Assistente de IA.

O Audience Agent permite exibir insights sobre públicos-alvo, incluindo a detecção de alterações significativas no tamanho do público-alvo, a detecção de públicos-alvo duplicados, a exploração do inventário do público-alvo e a recuperação do tamanho deles.

>[!SLIDE](audience-agent-overview)

## Casos de uso aceitos

O Audience Agent no Assistente de IA é compatível com os seguintes casos de uso:

- Explorar seu público de forma conversacional
   - Localizar tamanhos de público-alvo de públicos-alvo existentes
   - Procure públicos-alvo com base em atributos completos ou parciais chamados
   - Detectar públicos-alvo duplicados
   - Descobrir campos XDM que podem ser usados para definir um público
- Detectar alterações significativas no tamanho do público
   - Isso permite encontrar públicos que subitamente cresceram ou diminuíram, permitindo que você analise melhor as possíveis alterações de mercado
- Criação de público-alvo
   - Essa habilidade permite criar um público-alvo com base nos atributos e eventos fornecidos
   - Além disso, essa habilidade permite estimar o tamanho potencial de um público antes de criá-lo, permitindo que você repita rapidamente no público mais eficiente antes que ele esteja pronto para ser ativado

<!--
  - Find your audience size and detect significant changes in audience size
  - This lets you find audiences that have suddenly grown or shrunk, letting you better analyze potential market changes
- Detect duplicate audiences
  - This lets you reduce redundancies with your created audiences
- Find audiences based on full or partial attributes named
  - This lets you more easily navigate through your audience inventory
- Discover XDM fields you can use to define an audience
  - This skill lets you more easily identify the right fields to use in your audience based on context and relevance 
-->

A Audience Agent não **oferece suporte ao seguinte recurso no momento**:

- Exploração de público-alvo com base em metas
   - A exploração de público-alvo com base em metas permite descobrir conjuntos de dados e perfis relevantes alinhados a uma meta comercial aplicando modelos de aprendizado de máquina, como propensão para comprar ou converter.

Além disso, ao usar o Audience Agent, você deve ter as seguintes restrições em mente:

- O Audience Agent precisa de pelo menos 24 horas para processar seus dados
   - Por exemplo, você **não pode** ter uma consulta que procura dados nas últimas 24 horas. Você terá que olhar dentro das últimas 48 horas, no mínimo.
- O Audience Agent é compatível apenas com os seguintes tipos de público-alvo:
   - **Públicos-alvo** com base em pessoas que são avaliados usando a segmentação em lote
   - **Públicos-alvo** baseados em conta para os seguintes casos de uso:
      - Exploração de público-alvo de conversa
      - Detecção de público-alvo duplicado

## Exemplos de prompts

Os exemplos a seguir demonstram exemplos de prompts e respostas para a Audience Agent.

### Exploração de público-alvo de conversa

Mostre-me campos para compradores ricos.

+++ Resposta

![O Assistente de IA mostra uma tabela exibindo campos relevantes para compradores ricos.](./images/audience/affluent-buyers.png)

+++

Quais públicos-alvo não foram ativados ou usados em nenhuma campanha nos últimos 30 dias?

+++ Resposta

![O Assistente de IA mostra uma tabela que exibe públicos que não foram ativados ou usados em campanhas nos últimos 30 dias.](./images/audience/not-activated.png)

+++

Liste todos os públicos que foram mapeados para novos destinos nos últimos três meses.

+++ Resposta

![O Assistente de IA lista o público-alvo que foi mapeado para um novo destino nos últimos 3 meses.](./images/audience/new-destination.png)

+++

Qual público-alvo de conta tem o maior tamanho de público-alvo e qual é esse tamanho?

+++ Resposta

![O Assistente de IA mostra uma tabela que exibe os maiores públicos-alvo da conta.](./images/audience/largest-account-audience.png)

+++

### Detectar públicos-alvo duplicados

Tenho públicos-alvo com descrições idênticas ou semelhantes?

+++ Resposta

![O Assistente de IA exibe uma tabela que contém a definição do segmento e os nomes dos públicos-alvo com as mesmas definições de segmento.](./images/audience/similar-descriptions.png)

+++

Identifique públicos que tenham as mesmas regras, mas nomes diferentes.

+++ Resposta

![O Assistente de IA exibe uma tabela que contém os nomes dos públicos-alvo que compartilham as mesmas regras de público-alvo.](./images/audience/same-rules-different-names.png)

+++

Mostre-me todos os públicos-alvo que têm as mesmas regras, mas destinos de ativação diferentes.

+++ Resposta

![O Assistente de IA mostra que não há definições de segmento duplicadas para destinos diferentes.](./images/audience/same-rules-different-destinations.png)

+++

Identifique públicos-alvo de conta que tenham as mesmas regras, mas nomes diferentes.

+++ Resposta

![The AI Assistant displays a table that contains the names and IDs of account audiences that share the same audience rules.](./images/audience/duplicate-account-audience.png)

+++

### Recuperar tamanho do público

What is the current size of my audience &quot;Gold-star Members in California_f153e1&quot;?

+++ Resposta

![The AI Assistant states the current size of the audience that was asked about.](./images/audience/current-size.png)

+++

What is my biggest audience?

+++ Resposta

![The AI Assistant gives information about the audience with the most profiles, including name and audience ID.](./images/audience/largest-audience.png)

+++

### Detectar alterações significativas no tamanho do público

Which audiences have increased in size by more than 20% in the last week?

+++ Resposta

![The AI Assistant displays a table that lists the names of all the audiences that match the query. It also shows the percentage increase, the current audience size, as well as the former audience size.](./images/audience/increase-past-week.png)

+++

Which audiences have decreased in size by more than 10% in the last month?

+++ Resposta

![The AI Assistant displays a table that lists the names of all the audiences that match the query. It also shows the current audience size, the former audience size, as well as the date of the old audience size.](./images/audience/decrease-month.png)

+++

What is my fastest growing audience?

+++ Resposta

![The AI Assistant states the name of the fastest growing audience, as well as the current size and the percentage of growth.](./images/audience/fastest-growing.png)

+++

### Criar um público-alvo

>[!AVAILABILITY]
>
>You can only use the create audience skill if you are part of the Agent Orchestrator Explorer program. For more information, contact Adobe Customer Care.

When you create an audience with Audience Agent, AI Assistant will guide you through a plan. For example, you can ask to &quot;Create an audience made up of people who live in California&quot;. AI Assistant then lists the plan that it will undertake to create the audience.

+++ Resposta

![The AI Assistant shows the plan to create an audience.](./images/audience/audience-create-plan.png)

+++

This plan is made up of three steps:

1. [Identify audience characteristics](#identify)
2. [Estimate audience size](#estimate)
3. [Create and persist a new audience](#create)

#### Identificar características do público {#identify}

![Etapa 1 do plano, que é identificar as características do público-alvo.](./images/audience/plan-step-1.png){align="center" width="80%"}

Depois de aceitar o plano, o Assistente de IA capturará as características do público-alvo com base na consulta inicial.

+++ Resposta

![A definição de público-alvo com base na consulta de usuário.](./images/audience/audience-create-definition.png)

Para esta consulta, o Assistente de IA gera a Profile Query Language (PQL) relevante que procuraria pessoas que vivem na Califórnia. Nesse caso de uso, a consulta do PQL seria semelhante ao seguinte:

```sql
homeAddress.state.equals("California", false)
```

Para obter mais informações sobre o PQL, leia a [visão geral do PQL](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/pql/overview).

+++

Se a definição de público-alvo do Assistente de IA estiver correta, você poderá aprovar e seguir para a próxima etapa.

#### Estimar tamanho do público {#estimate}

![Etapa 2 do plano, que é estimar o tamanho do público potencial.](./images/audience/plan-step-2.png){align="center" width="80%"}

Depois de aprovar as características identificadas do público-alvo, o Assistente de IA estimará o tamanho do público-alvo potencial e os detalhes de definição do público-alvo.

+++ Resposta

![A amostra de estimativa para o público-alvo potencial é exibida. O tamanho estimado e a definição do segmento são mostrados.](./images/audience/audience-create-estimate.png)

+++

Se o tamanho estimado estiver correto, você poderá aprovar e seguir para a próxima etapa.

#### Criar e manter um novo público-alvo {#create}

![Etapa 3 do plano, que é concluir a criação do público-alvo.](./images/audience/plan-step-3.png){align="center" width="80%"}

Por fim, se as características e o tamanho do público estiverem corretos, você poderá aprovar ou rejeitar a criação do público.

+++ Resposta

Primeiro, você pode revisar o público-alvo proposto por meio da grade de dados fornecida.

![A tela de revisão é exibida.](./images/audience/audience-create-review.png)

Se o público estiver correto, você pode aceitar a proposta selecionando **[!UICONTROL Criar]** para concluir a criação do público.

![A proposta completa para o público-alvo é exibida.](./images/audience/audience-create-proposal.png)

+++

O público-alvo foi criado.

![A proposta de público-alvo foi aceita e o público-alvo foi criado.](./images/audience/audience-finish-create.png){align="center" width="80%"}

## Próximas etapas

Depois de ler este guia, você terá uma melhor compreensão do Audience Agent e de quais recursos ele oferece suporte. Para obter mais informações sobre agentes no Adobe Experience Platform, leia a [visão geral do Agent Orchestrator](./agent-orchestrator.md).

