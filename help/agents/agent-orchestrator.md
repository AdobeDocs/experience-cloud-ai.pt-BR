---
title: Adobe Experience Platform Agent Orchestrator
description: Saiba mais sobre o Adobe Experience Platform Agent Orchestrator.
source-git-commit: 352ba791195eca7f68e6d317e0f2449d6ededeb2
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 2%

---

# Adobe Experience Platform Agent Orchestrator

O Adobe Experience Platform Agent Orchestrator é a nova camada de agente no Adobe Experience Platform. Projetada para aproveitar os valiosos dados e conhecimentos de clientes da Experience Platform, a Experience Platform Agent Orchestrator alimenta a inteligência e o raciocínio por trás dos agentes especializados Adobe Experience Platform criados com propósitos específicos, permitindo que eles executem tarefas complexas de tomada de decisões e solução de problemas em velocidade e escala — tudo com supervisão humana. Quando você faz perguntas ou solicita ajuda por meio da linguagem natural em uma interface conversacional como o AI Assistant, o Agent Orchestrator chama automaticamente agentes especializados para obter as respostas certas. O Agent Orchestrator lembra seu histórico de conversas, permitindo que você se baseie em perguntas anteriores naturalmente sem repetir o contexto e combina insights de vários agentes para apresentar respostas claras e unificadas.

Você pode concluir fluxos de trabalho completos e complexos por meio de uma interface conversacional intuitiva sem precisar saber quais agentes estão trabalhando em segundo plano. O sistema entende seus objetivos, cria planos passo a passo e ajusta sua abordagem conforme necessário com base em seus comentários. Em sua conversa no Assistente de IA, você pode explorar o painel de raciocínio do Agent Orchestrator para ver o processo de pensamento passo a passo e entender melhor como suas solicitações estão sendo tratadas.

Leia este documento para saber mais sobre o Agent Orchestrator.

## Componentes do Agent Orchestrator {#components}

O Agent Orchestrator é composto por vários componentes principais, incluindo a interface conversacional do Assistente de IA, um mecanismo de raciocínio para tomada de decisões e planejamento, agentes especializados da Adobe Experience Platform e uma base de conhecimento que fornece acesso a informações relevantes.

![A arquitetura de marketing do Agent Orchestrator.](./images/agent-orchestrator/agentic-architecture.png)

### Interface de conversação do Assistente de IA {#ai-assistant}

O Assistente de IA é uma experiência de conversação inteligente em linguagem natural que permite que os profissionais que usam aplicativos habilitados do Experience Cloud aproveitem os recursos de IA de geração e de agente, cuja amplitude depende dos aplicativos da Experience Cloud licenciados pelos clientes. Para desbloquear o acesso, leia [o manual sobre como acessar o Assistente de IA](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

Para obter mais informações, leia o [Guia da interface do usuário do Assistente de IA](../ai-assistant/ai-assistant-ui.md).

### Mecanismo de raciocínio {#reasoning-engine}

O mecanismo de raciocínio interpreta suas metas com base em seus prompts de linguagem natural, verifica quaisquer limites ou requisitos e cria planos passo a passo para ajudar você a alcançar seus objetivos. Ao contrário de sistemas simples de perguntas e respostas, ele pode ajustar seus planos à medida que as coisas mudam, e pode voltar e tentar abordagens diferentes, se necessário. Os planos criados são mostrados na interface conversacional do Assistente de IA, para que você possa ver e seguir o processo, bem como intervir, se necessário.

### Agentes da Adobe Experience Platform {#agents}

Os agentes da Adobe Experience Platform são um agrupamento criado com propósitos específicos de agentes de IA qualificados para fornecer trabalhos comuns em domínios de experiência do cliente. Abaixo está a lista de Agentes do Adobe Experience Platform que estão disponíveis atualmente nos aplicativos da Experience Cloud:

| Agente | Detalhes | Aplicativos compatíveis |
| --- | --- | --- |
| [Audience Agent](audience.md) | O Audience Agent permite exibir insights sobre públicos-alvo, incluindo a detecção de alterações significativas no tamanho do público-alvo, a detecção de públicos-alvo duplicados, a exploração do inventário do público-alvo e a recuperação do tamanho dele. | <ul><li>Real-Time CDP</li><li>Adobe Journey Optimizer</li></ul> |
| [Data Insights Agent](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) | O Data Insights Agent, acessível pelo Assistente de IA na Customer Journey Analytics, é um agente de conversação de IA generativo que responde de forma rápida e eficiente a perguntas sobre seus dados. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e usando seus dados reais. | Customer Journey Analytics |
| [Agente de experimentação](./agent-experiment.md) | O agente de experimentação ajuda as equipes a aprenderem mais rápido, analisando os resultados dos experimentos, prevendo o impacto e propondo novos experimentos. Ele centraliza experimentos passados e ativos para que você possa aproveitar o que já aprendeu, detectar lacunas e priorizar o que testar a seguir. | Adobe Journey Optimizer Experimentation Accelerator |
| [Journey Agent](./ajo-agent-analyze.md) | O Journey Agent permite que os usuários do Adobe Journey Optimizer criem, analisem e otimizem jornadas usando uma interface de linguagem natural. Com o Journey Agent, você pode criar jornadas rapidamente, detectar e resolver conflitos de agendamento ou público-alvo, analisar pontos de desempenho e queda e identificar jornadas de melhor desempenho a serem replicadas para campanhas futuras. Ele ajuda você a tomar decisões orientadas por dados, melhorar o envolvimento do cliente e simplificar a orquestração de jornadas. | Adobe Journey Optimizer |
| [Agente de Suporte ao Produto](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/new-features/customer-support) | O Agente de suporte ao produto é um recurso de depuração e solução de problemas de autoatendimento que ajuda a solucionar problemas de recursos e aplicativos do Adobe Experience Platform sem sair dos fluxos de trabalho. Os administradores de suporte podem criar tíquetes de suporte ao cliente com contexto das interações do Assistente de IA e você pode verificar as atualizações de tíquetes por meio do Assistente de IA. | <ul><li>Adobe Experience Platform</li><li>Real-Time CDP</li><li>Adobe Journey Optimizer</li><li>Adobe Journey Optimizer B2B edition</li><li>Customer Journey Analytics</li><li>Adobe Experience Manager</li></ul> |

Para obter mais informações sobre a disponibilidade de Agentes nos aplicativos da Experience Cloud, consulte a [documentação sobre IA de agente na Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/features/agentic-ai).

### Knowledge base {#knowledge-base}

A base de conhecimento fornece aos agentes acesso seguro à inteligência de negócios do cliente por meio de fontes de dados estruturadas e não estruturadas, incluindo documentação de produtos da Adobe, metadados de clientes sobre objetos de negócios e dados de análise.

## Acesso {#access}

As solicitações do Assistente de IA são autenticadas usando os Adobe Identity Management Services. As autorizações são aplicadas pelo Adobe Experience Platform Access Control e pelo Customer Journey Analytics Access Control.

Para obter acesso à interface conversacional do Assistente de IA e usar um ou mais Agentes do Experience Platform, o administrador do Adobe deve conceder a você as permissões relevantes na interface do usuário de permissões ou na Adobe Admin Console:

* **Real-Time CDP** e **Adobe Journey Optimizer**: o administrador deve conceder a você a permissão **Habilitar Assistente de IA** para permitir que você acesse o Assistente de IA. O administrador também deve conceder a você as permissões **Exibir Insights Operacionais** para permitir que você faça perguntas sobre insights operacionais no Assistente de IA. Ambas as permissões são definidas pelo administrador na interface do usuário de Permissões.

* **Customer Journey Analytics**: o administrador deve conceder a você permissão para acessar o Assistente de IA por meio do [Controle de Acesso do Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/access-control). Isso permite fazer perguntas sobre conhecimento do produto e insights de dados.

>[!NOTE]
>
>As perguntas de insights operacionais não estão disponíveis para o Customer Journey Analytics; portanto, nenhuma permissão adicional se aplica.

* **Adobe Experience Manager**: o administrador deve conceder a você permissão para acessar o Assistente de IA por meio da [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html).

