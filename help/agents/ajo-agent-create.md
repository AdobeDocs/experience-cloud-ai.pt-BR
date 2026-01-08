---
title: Visão geral da criação de habilidades de agente do Jornada
description: Saiba como usar a habilidade Criar do Journey Agent para criar jornadas de marketing por meio de prompts de linguagem naturais no Journey Optimizer.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer
feature: AI Assistant
topic: Administration
level: Beginner
source-git-commit: 864002185f3745ca76180af192f616d1e5da0791
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 1%

---


# Jornada Criar agente: visão geral e guia do usuário da habilidade

## Visão geral

O Agente de criação de Jornada permite que os usuários do Journey Optimizer criem e configurem jornadas de marketing usando uma interface de linguagem natural. Com o Jornada Create Agent, os profissionais podem criar jornadas rapidamente descrevendo seus requisitos em prompts de conversa. O agente simplifica a criação de jornadas, permitindo que os profissionais de marketing se concentrem na estratégia em vez da configuração técnica.

>[!AVAILABILITY]
>
>O Agente de criação de Jornada está disponível para todos os clientes que têm acesso ao Assistente de IA. No entanto, você precisará das seguintes permissões para usar totalmente os recursos Criar agente do Jornada:
>
>**Gerenciar Jornadas**: essa permissão permite que você crie novas jornadas diretamente no Assistente do AI.
>
>**Exibir eventos de Jornada, fontes de dados e ações**: essa permissão garante que o Assistente de IA possa realizar pesquisas em eventos de Jornada e ações personalizadas.
>
>**Exibir segmentos**: essa permissão garante que o Assistente de IA possa pesquisar segmentos de público-alvo ao criar uma Jornada.
>
>**Gerenciar segmentos**: essa permissão permite criar novos públicos-alvo diretamente no Assistente de IA.

## Casos de uso

### Principais casos de uso para o Agente de criação do Jornada

A habilidade Criar agente da Jornada oferece recursos que podem ser aproveitados para acelerar a execução de marketing:

1. **Criação de jornada acionada por evento**

   - Crie jornadas que são ativadas com base em eventos específicos do cliente.
   - Projetar respostas automatizadas para ações do cliente em tempo real.
   - Crie fluxos de comunicação personalizados com base no comportamento do cliente.

1. **Criação de jornada direcionada ao público-alvo**

   - Crie jornadas direcionadas a segmentos específicos do público-alvo.
   - Projete sequências de comunicação em várias etapas com tempo estratégico.

1. **Criação de jornada acionada por evento comercial**

   - Crie jornadas que são ativadas com base em um evento comercial específico e direcionem um público especificado (por exemplo, produto de volta ao estoque ou alteração de pontuação do jogo)
   - Crie fluxos de comunicação personalizados com base no comportamento do cliente.

1. **Criação de jornada de qualificação de público-alvo**

   - Crie jornadas que são ativadas quando os perfis entram ou saem de uma definição de segmento de público-alvo.
   - Crie fluxos de comunicação personalizados com base no comportamento do cliente.

1. **Fluxos de jornada condicionais**

   - Crie ramificações de decisão com base nos atributos do cliente.
   - Criar caminhos divididos que se adaptam às preferências do cliente.

Para cada um desses casos de uso, o agente traduz os requisitos de linguagem natural em configurações de jornada estruturadas.

## Habilidades dentro e fora do escopo

### **No escopo**

Os seguintes recursos são compatíveis com o Jornada Create Agent:

- **Criação de jornada de linguagem natural**: permite que os usuários descrevam o fluxo de jornada em linguagem de conversação.
- **jornadas baseadas em eventos e em público-alvo**: oferece suporte aos tipos de jornada baseados em acionadores e agendados, bem como à qualificação de eventos comerciais e públicos-alvo.
- **Lógica condicional**: lida com divisões de decisão e ramificações com base nos atributos do cliente.
- **Mensagens multicanais**: oferece suporte a notificações por push, email e canais SMS.
- **Agendamento de Jornada**: configura datas de início e tempo para jornadas agendadas.

### **Fora de escopo**

As seguintes funcionalidades não são compatíveis no momento:

- **Análise de jornada avançada**
- **Modificações de jornada em tempo real**
- **Orquestração entre jornadas**
- **Configuração de teste A/B**
- **Transformações de dados complexas**
- **Criação da mensagem de conteúdo**

## Exemplos de prompts

### Prompts comuns para a criação de jornadas

Estes são exemplos de prompts valiosos que os usuários podem utilizar para criar jornadas.

### Prompts de jornada acionados por evento

**jornada de visita da loja:**

&quot;Crie uma jornada que começa quando um usuário entra no local da loja. Envie uma notificação por push para dar as boas-vindas aos usuários do armazenamento. Aguarde 2 dias e verifique se o usuário tem um endereço de email válido. Se o usuário tiver um endereço de email válido, envie uma pesquisa por email para perguntar sobre a experiência da loja. Se o usuário não tiver um endereço de email válido, envie uma notificação por push para solicitar o registro.&quot;

**jornada pós-compra:**

&quot;Crie uma jornada que começa quando um cliente faz uma compra online. Envie uma notificação por push para agradecer a compra. Em seguida, verifique se eles são membros do programa de fidelidade. Se o usuário for um membro do programa de fidelidade, envie uma segunda notificação por push com um código de desconto de 10%. Se o usuário não for um membro do programa de fidelidade, envie um push convidando-o a se inscrever no programa de fidelidade. Aguarde 2 dias e envie um push de acompanhamento com uma pesquisa sobre a experiência de compra deles.&quot;

**Promoção baseada em eventos:**

&quot;Criar uma jornada acionada quando a pontuação do jogo atingir 50. Envie uma mensagem SMS aos membros do programa de fidelidade dizendo que estão qualificados para receber uma fatia gratuita de pizza do patrocinador do parceiro.&quot;

### Prompts de jornada direcionados ao público

**Campanha sazonal:**

&quot;Eu quero criar uma jornada direcionada a um público de visitantes do dia. Quero enviar um email alertando esse público-alvo para minha próxima venda de fim de ano que inclui uma variedade de recursos básicos para caminhadas. Aguarde 3 dias após o envio do primeiro e-mail e envie um segundo e-mail que tenha um cupom de 15% com frete grátis. Aguarde 1 semana e envie uma 3ª mensagem de email para mostrar nosso novo saco de dormir e coleção de tendas. Programe a jornada para iniciar em 20/12.&quot;

**Apreciação de fidelidade:**

&quot;Crie uma jornada de apreciação de fidelidade para proprietários de SUVs, incluindo uma notificação por push de agradecimento com uma oferta gratuita de lavagem de carro e um lembrete de notificação por push de acompanhamento se a primeira notificação não tiver interação em até 1 dia.&quot;

### Prompts abertos

Para usuários que começam sem uma jornada específica em mente:

- &quot;Gostaria de criar uma jornada&quot;
- &quot;Ajude-me a criar uma jornada&quot;
- &quot;Crie uma jornada para mim&quot;

O agente fornecerá orientação e exemplos para ajudar você a definir seus requisitos de jornada.

## Práticas recomendadas

### Solicitação de práticas recomendadas

Para maximizar a eficácia do Agente de criação do Jornada, siga estas práticas recomendadas:

1. **Seja específico**: forneça detalhes claros sobre suas metas do jornada, público-alvo e ações desejadas. Inclua informações sobre canais, tempo e condições.
1. **Especificar Tempo**: indique claramente os períodos de espera entre as ações e quando a jornada deve começar.
1. **Definir condições**: ao usar a lógica condicional, explique os critérios para cada caminho de ramificação.
1. **Incluir Canais**: especifique quais canais de comunicação você deseja usar (push, email, SMS).
1. **Agendamento de menção**: para jornadas agendadas, forneça a data e a hora de início desejadas.
1. **Ações personalizadas**: se você estiver usando ações personalizadas em seu fluxo de trabalho, será necessário especificar que você está usando uma ação personalizada, juntamente com o nome exato da ação personalizada. Exemplo:
Quando um usuário entrar no meu local de armazenamento, envie uma mensagem de boas-vindas usando a ação personalizada ExternalPush. Aguarde 2 dias e envie uma mensagem de acompanhamento usando a ação personalizada ExternalEmail com uma pesquisa em sua visita.
1. **Validar expressões**: verifique e valide todas as expressões criadas pelo Journey Agent para garantir que os campos e valores corretos sejam usados.

### Configurar práticas recomendadas

- **Definir objetivos claros**: antes de criar jornadas, estabeleça metas claras (melhorar a retenção, gerar conversões, aumentar o engajamento).
- **Preparar públicos-alvo**: verifique se os públicos-alvo já foram criados e segmentados corretamente.
- **Conteúdo da Mensagem do Plano**: Defina sua estratégia de mensagens antes da criação da jornada.
- **Considere a Experiência do Cliente**: crie fluxos de jornada que respeitem as preferências do cliente e evitem a comunicação excessiva.

