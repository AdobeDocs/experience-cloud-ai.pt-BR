---
title: IA em aplicativos da Experience Cloud
description: Saiba como os aplicativos da Experience Cloud usam a IA generativa (GenAI), o Assistente de IA e a IA agêntica.
TQID: https://experienceleague.adobe.com/heALjEZbowNaygG24oOM2HSlHa9oYVI5ViUNZDr19Ds
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: e1e0219c-f879-479f-8427-888ed2a6e9c2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 846
ht-degree: 4%

---

# IA na Experience Cloud

Bem-vindo ao guia abrangente para recursos de IA em aplicativos da Adobe Experience Cloud. Esta documentação aborda como a IA gerativa, o AI Assistant e os agentes do Adobe são integrados aos fluxos de trabalho do Experience Cloud para acelerar a produtividade e aprimorar a tomada de decisões.

## O que está incluído neste guia

### Assistente de IA

O [Assistente de IA](./ai-assistant/ai-assistant-ui.md) é uma ferramenta de IA conversacional e gerativa inteligente que impulsionará a produtividade e redefinirá o trabalho em aplicativos baseados em Adobe Experience Platform. Os usuários podem obter conhecimento sobre o produto, solucionar problemas e encontrar insights operacionais por meio de prompts de linguagem natural. Você também pode usar o Assistente de IA para acessar os Agentes do Adobe Experience Platform e outros recursos de IA.

**Principais recursos:**

- **Interface de conversa**: você pode escolher entre uma interface de exibição em tela inteira e uma interface de exibição em painel para atender às suas preferências de fluxo de trabalho.
- **Solicitações de Descoberta**: o Assistente de IA fornece solicitações pré-configuradas que são organizadas por categorias, como Aprender, Analisar e Otimizar.
- **Configuração de Contexto**: você pode definir as configurações de aplicativo, sandbox e exibição de dados para receber respostas adequadas às suas necessidades.
- **Visualização de dados**: a ferramenta fornece gráficos interativos, permitindo que você obtenha insights sobre seus dados.
- **Verificação de resposta**: todas as respostas incluem citações de origem, explicações sobre o raciocínio de IA e mecanismos para fornecer feedback.


### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md) é a nova camada de agente no Adobe Experience Platform. Projetada para aproveitar os valiosos dados e conhecimentos de clientes da plataforma, a Experience Platform Agent Orchestrator capacita a inteligência e o raciocínio por trás dos agentes especializados Adobe Experience Platform criados com propósitos específicos, permitindo que eles executem tarefas complexas de tomada de decisões e solução de problemas em velocidade e escala — tudo com supervisão humana. Quando você faz perguntas ou solicita ajuda por meio da linguagem natural em uma interface conversacional como o AI Assistant, o Agent Orchestrator chama automaticamente agentes especializados para obter as respostas certas. O Agent Orchestrator lembra seu histórico de conversas, permitindo que você se baseie em perguntas anteriores naturalmente sem repetir o contexto e combina insights de vários agentes para apresentar respostas claras e unificadas.

**Componentes principais:**

- **Mecanismo de raciocínio**: cria planos passo a passo e ajusta abordagens conforme necessário
- **Agentes especializados**: agentes criados com propósitos específicos para tarefas e domínios específicos
- **Knowledge Base**: Acesso seguro à business intelligence e documentação

### Agentes especializados

#### Audience Agent

A Audience Agent fornece insights sobre públicos-alvo, incluindo:

- Detecção de alterações significativas no tamanho do público.
- Identifying duplicate audiences.
- Exploring audience inventory.
- Retrieving audience sizes.

Read the [Audience Agent documentation](./agents/audience.md) for more information.

#### Data Insights Agent

Available in Customer Journey Analytics, the Data Insights Agent:

- Answers questions about your data using natural language.
- Builds relevant visualizations in Analysis Workspace.
- Uses components from your dataview and actual data.

#### Journey Analyze Agent

The Journey Analyze Agent enables the Adobe Journey Optimizer users to:

- Analyze, and optimize journeys using natural language.
- Detect and resolve schedule or audience conflicts.
- Analyze performance and drop-off points.

Read the [Journey Agent documentation](./agents/ajo-agent.md) for more information.

#### Agente de suporte ao produto

Use the Product Support Agent for self-serve debugging and troubleshooting:

- Troubleshoot Adobe Experience Platform features without leaving workflows.
- Create support tickets with context from AI Assistant interactions.
- Check ticket updates through AI Assistant.

Read the [Product Support Agent documentation](./agents/product-support.md) for more information.

<!--
#### Adobe Marketing Agent for [!DNL Microsoft 365 Copilot]

Use the Adobe Marketing Agent for [!DNL Microsoft 365 Copilot] to retrieve marketing insights from Experience Platform in [!DNL Microsoft 365] apps like [!DNL Teams], [!DNL Word], [!DNL Powerpoint], and [!DNL Excel]. With this agent, you can:

- Make faster, data-driven marketing decisions.
- Reduce time spent switching between tools.
- Simplify access to audience and journey insights across teams.

Read the [Adobe Marketing Agent documentation](./agents/ama-ms.md) for more information.
-->

## Introdução

### Access requirements

To use AI Assistant and Experience Platform Agents, your Adobe Admin needs to set up the appropriate permissions:

- To use AI Assistant within Real-Time CDP and Adobe Journey Optimizer, you need the &quot;Enable AI Assistant&quot; permission, as well as the &quot;View Operational Insights&quot; permission to access operational questions.
- Access to AI Assistant in Customer Journey Analytics is managed through Customer Journey Analytics Access Control, which allows you to ask both product knowledge and data insights questions.
- For Adobe Experience Manager, you can access AI Assistant through permissions set in the Adobe Admin Console.

### Privacidade e segurança

O Assistente de IA é criado com privacidade, segurança e governança na vanguarda:

- Nenhum dado pessoal é usado para treinamento.
- Todas as políticas de controle de acesso existentes são respeitadas.
- Pronto para HIPAA quando usado com o Adobe Experience Platform Healthcare Shield.
- Política de retenção de 30 dias para logs de interação.
- Isolamento de dados específico de sandbox.

## Práticas recomendadas

Para obter o máximo valor de sua experiência com o Assistente de IA, siga estas práticas recomendadas:

- **Seja específico** em suas solicitações para obter insights relevantes e direcionados do Assistente de IA.
- **Verifique as respostas** examinando as citações de origem e as explicações de raciocínio fornecidas pelo Assistente de IA.
- **Use a configuração de contexto** para garantir que as fontes de dados mais relevantes sejam usadas para suas perguntas.
- **Forneça feedback** para ajudar a melhorar o desempenho e a precisão do Assistente de IA ao longo do tempo.
- **Combine insights** de vários agentes para obter uma análise mais abrangente e bem arredondada.

## Considerações legais

Ao usar o Assistente de IA, é importante estar ciente das principais considerações legais e práticas. Atualmente, o Assistente de IA é compatível com respostas somente em inglês. Tenha sempre o cuidado de verificar as informações fornecidas, uma vez que os modelos de idioma podem, ocasionalmente, cometer erros. Use as etapas de raciocínio e as explicações incluídas nas respostas para entender melhor as respostas que você recebe. Se você encontrar problemas ou imprecisões, envie feedback para ajudar a melhorar o Assistente de IA ao longo do tempo.
