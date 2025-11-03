---
title: IA em aplicativos da Experience Cloud
description: Saiba como os aplicativos da Experience Cloud usam a IA generativa (GenAI), o Assistente de IA e a IA agêntica.
source-git-commit: 8c05562121071874002afd6d248f16186616da55
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 3%

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
- Identificação de públicos-alvo duplicados.
- Explorar o inventário de público-alvo.
- Recuperação de tamanhos de público-alvo.

Leia a [documentação do Audience Agent](./agents/audience.md) para obter mais informações.

#### Data Insights Agent

Disponível na Customer Journey Analytics, a Data Insights Agent:

- Responde perguntas sobre seus dados usando a linguagem natural.
- Cria visualizações relevantes no Analysis Workspace.
- Usa componentes da sua visualização de dados e dados reais.

#### Agente de análise de Jornada

O Jornada Analyze Agent permite que os usuários do Adobe Journey Optimizer:

- Analise e otimize jornadas usando a linguagem natural.
- Detectar e resolver conflitos de agendamento ou público-alvo.
- Analise o desempenho e os pontos de devolução.

Leia a [documentação do Jornada Analyze Agent](./agents/ajo-agent-analyze.md) para obter mais informações.

#### Agente de suporte ao produto

Use o Agente de Suporte do Produto para depuração e solução de problemas de autoatendimento:

- Solucionar problemas de recursos do Adobe Experience Platform sem sair dos fluxos de trabalho.
- Criar tíquetes de suporte com contexto de interações do Assistente de IA.
- Verifique as atualizações de tíquete por meio do Assistente de IA.

Leia a [documentação do Agente de Suporte do Produto](./agents/product-support.md) para obter mais informações.

## Introdução

### Requisitos de acesso

Para usar o AI Assistant e os Experience Platform Agents, o administrador do Adobe precisa configurar as permissões apropriadas:

- Para usar o Assistente de IA no Real-Time CDP e no Adobe Journey Optimizer, você precisa da permissão &quot;Habilitar o Assistente de IA&quot;, bem como da permissão &quot;Exibir Insights Operacionais&quot; para acessar perguntas operacionais.
- O acesso ao Assistente de IA no Customer Journey Analytics é gerenciado por meio do Controle de acesso da Customer Journey Analytics, que permite fazer perguntas sobre conhecimento do produto e insights de dados.
- No Adobe Experience Manager, você pode acessar o Assistente de IA por meio de permissões definidas no Adobe Admin Console.

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
