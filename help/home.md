---
title: IA em aplicativos Experience Cloud
description: Saiba como os aplicativos do Experience Cloud usam IA gerativa (GenAI), AI Assistant e IA agêntica.
source-git-commit: 4bb6da3fe1abee98446df62c94730274e0931493
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# IA no Experience Cloud

Bem-vindo ao guia abrangente para recursos de IA em aplicativos da Adobe Experience Cloud. Esta documentação aborda como a IA gerativa, o AI Assistant e os agentes do Adobe são integrados aos fluxos de trabalho do Experience Cloud para acelerar a produtividade e aprimorar a tomada de decisões.

## O que está incluído neste guia

### Assistente de IA

O [Assistente de IA](./ai-assistant/ai-assistant-ui.md) é uma ferramenta de IA conversacional e gerativa inteligente que impulsionará a produtividade e redefinirá o trabalho em aplicativos baseados em Adobe Experience Platform. Os usuários podem obter conhecimento sobre o produto, solucionar problemas e encontrar insights operacionais por meio de prompts de linguagem natural. Você também pode usar o Assistente de IA para acessar os Agentes do Adobe Experience Platform e outros recursos de IA.

**Principais recursos:**

- **Interface de conversa**: opções de exibição de tela inteira e painel para diferentes preferências de fluxo de trabalho
- **Solicitações de Descoberta**: solicitações pré-configuradas organizadas por categoria (Aprender, Analisar, Otimizar)
- **Configuração de Contexto**: definir configurações de aplicativo, sandbox e exibição de dados para respostas direcionadas
- **Visualização de dados**: gráficos interativos para insights de dados
- **Verificação de Resposta**: citações do Source, explicações de raciocínio e mecanismos de feedback

### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md) é a nova camada de agente no Adobe Experience Platform. Projetada para aproveitar os valiosos dados e conhecimentos de clientes da plataforma, a Experience Platform Agent Orchestrator capacita a inteligência e o raciocínio por trás dos agentes especializados Adobe Experience Platform criados com propósitos específicos, permitindo que eles executem tarefas complexas de tomada de decisões e solução de problemas em velocidade e escala — tudo com supervisão humana. Quando você faz perguntas ou solicita ajuda por meio da linguagem natural em uma interface conversacional como o AI Assistant, o Agent Orchestrator chama automaticamente agentes especializados para obter as respostas certas. O Agent Orchestrator lembra seu histórico de conversas, permitindo que você se baseie em perguntas anteriores naturalmente sem repetir o contexto e combina insights de vários agentes para apresentar respostas claras e unificadas.

**Componentes principais:**

- **Mecanismo de raciocínio**: cria planos passo a passo e ajusta abordagens conforme necessário
- **Agentes especializados**: agentes criados com propósitos específicos para tarefas e domínios específicos
- **Knowledge Base**: Acesso seguro à business intelligence e documentação

### Agentes especializados

#### Audience Agent

Fornece insights sobre públicos-alvo, incluindo:

- Detecção de alterações significativas no tamanho do público
- Identificação de públicos-alvo duplicados
- Explorar o inventário de público
- Recuperação de tamanhos de público

#### Data Insights Agent

Disponível no Customer Journey Analytics, este agente:

- Responde perguntas sobre seus dados usando a linguagem natural
- Cria visualizações relevantes no Analysis Workspace
- Usa componentes da sua visualização de dados e dados reais

#### Journey Agent

Permite que os usuários do Journey Optimizer:

- Analisar e otimizar jornadas usando linguagem natural
- Detectar e resolver conflitos de agendamento ou público
- Analisar desempenho e pontos de devolução

#### Agente de suporte ao produto

Oferece depuração e solução de problemas de autoatendimento:

- Solução de problemas de recursos do Adobe Experience Platform sem sair dos fluxos de trabalho
- Criar tíquetes de suporte com contexto de interações do Assistente de IA
- Verificar atualizações de tíquete por meio do Assistente de IA

## Introdução

### Requisitos de acesso

Para usar o AI Assistant e os Experience Platform Agents, o administrador do Adobe precisa configurar as permissões apropriadas:

- **Real-Time CDP e Adobe Journey Optimizer**: exige a permissão &quot;Habilitar o Assistente de IA&quot; e a permissão &quot;Exibir Insights Operacionais&quot; para perguntas operacionais
- **Customer Journey Analytics**: acesso através do Controle de Acesso Customer Journey Analytics para perguntas sobre conhecimento do produto e insights de dados
- **Adobe Experience Manager**: acesso através da Adobe Admin Console

### Privacidade e segurança

O Assistente de IA é criado com privacidade, segurança e governança na vanguarda:

- Nenhum dado pessoal é usado para treinamento
- Todas as políticas de controle de acesso existentes são respeitadas
- Pronto para HIPAA quando usado com o Adobe Experience Platform Healthcare Shield
- Política de retenção de 30 dias para logs de interação
- Isolamento de dados específico de sandbox

## Práticas recomendadas

- **Seja específico** em suas solicitações para obter insights direcionados
- **Verificar respostas** usando citações de origem e explicações de raciocínio
- **Usar configuração de contexto** para garantir fontes de dados relevantes
- **Forneça feedback** para ajudar a melhorar o desempenho do Assistente de IA
- **Combine insights** de vários agentes para uma análise abrangente

## Considerações legais

- O Assistente de IA atualmente suporta somente inglês
- Sempre verifique as respostas, pois os modelos de idioma podem cometer erros
- Revisar etapas de raciocínio e explicações fornecidas
- Envie feedback sobre problemas ou imprecisões

Este guia fornece tudo o que você precisa para usar com eficiência os recursos de IA em seus aplicativos da Experience Cloud, desde interações básicas até a orquestração avançada de agentes e fluxos de trabalho especializados.
