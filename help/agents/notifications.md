---
title: Agente de notificações
description: Saiba como usar o Agente de notificações no Assistente de IA para resumir, interpretar e agir em suas notificações do Adobe CX Enterprise usando a linguagem natural.
source-git-commit: d4254ada196055b869e6392b6d8cc2d4a037c4ad
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# Agente de notificações

O Agente de Notificações adiciona uma camada de IA conversacional no [Assistente de IA](../ai-assistant/ai-assistant-ui.md), que você pode usar para resumir, interpretar e agir em suas notificações usando linguagem natural, transformando assim um feed passivo em um assistente ativo. Em vez de digitalizar uma lista longa, você pode alternar de &quot;Tenho 47 notificações&quot; para &quot;2 Preciso de minha aprovação até sexta-feira, 3 conjuntos de dados têm conflitos, o restante é informações&quot; em uma única troca.

## O que o Agente de Notificações pode fazer

O Agente de Notificações é compatível com os seguintes recursos:

| Recursos | Descrição |
| --- | --- |
| **Resumos e insights de notificação** | Obtenha visões gerais concisas de suas notificações, faça uma distinção clara entre as que exigem ação e as que são apenas informativas e entenda a finalidade de uma notificação e o motivo pelo qual você a recebeu. |
| **Ações operacionais** | Executar ações em notificações diretamente por meio de conversas — marcá-las como lidas, adiá-las ou definir lembretes para notificações individuais ou agrupadas. |
| **Preferências e configurações** | Ative ou desative os canais de notificação (email, Slack, no aplicativo) por solução e categoria, sem navegar pelas Configurações. |
| **Navegação e deep linking** | Mudar de uma notificação diretamente para a área de produto relevante por meio de deep links. |
| **Collaboration e compartilhamento** | Compartilhe notificações ou envie anúncios para destinatários na mesma organização. |

## Agente de Notificações de Acesso

Você pode acessar o Agente de notificações das seguintes maneiras:

- **No Assistente de IA**: abra o Assistente de IA e insira qualquer prompt relacionado à notificação.
- **Na biblioteca de prompts**: selecione um prompt sugerido que atenda ao seu requisito.

## Exemplos de prompts

Leia as seções a seguir para ver exemplos de prompts que podem ser usados com o Agente de Notificações.

### Resumos e insights

- &quot;Resumir minhas notificações recentes.&quot;
- &quot;Quais das minhas notificações precisam da minha ação em relação ao que é apenas informação?&quot;

### Ações

- &quot;Marcar todas as notificações não acionáveis como lidas.&quot;
- &quot;Lembre-me sobre a notificação {NOTIFICATION_OF_INTEREST} em uma hora.&quot;

### Preferências

- &quot;Ativar notificações do Slack para o Journey Optimizer.&quot;
- &quot;Mudar meu resumo diário para semanal.&quot;

### Colaboração

- &quot;Compartilhar esta notificação com {EMAIL_ADDRESS_OF_USER_IN_YOUR_ORG}.&quot;

## Práticas recomendadas

Lembre-se das seguintes dicas ao usar o Agente de notificações:

- **Seja específico** — Nomeie claramente o aplicativo, a notificação, a categoria de notificação e o canal para que o agente possa agir no destino pretendido.
- **Pedidos de encadeamento** — Você pode solicitar um resumo, fazer o acompanhamento com foco em uma notificação específica e, em seguida, realizar uma ação, tudo em uma única conversa.
- **Responda perguntas esclarecedoras** — quando o agente solicitar confirmação sobre o aplicativo, canal ou notificação, certifique-se de responder para que as alterações sejam aplicadas corretamente.
