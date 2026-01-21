---
title: Visão geral e guia do usuário do Journey Agent
description: Guia abrangente para o Journey Agent, permitindo que os usuários criem, analisem e otimizem jornadas de marketing usando uma interface de linguagem natural no Journey Optimizer.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer,Leader
source-git-commit: 0e3839f829efc5670c235435d49ed5e49da2ed13
workflow-type: tm+mt
source-wordcount: '2147'
ht-degree: 18%

---


# Journey Agent: visão geral e guia do usuário

## Introdução ao Journey Agent no Adobe Journey Optimizer

O Journey Agent permite que os usuários do Journey Optimizer criem, analisem e otimizem jornadas de marketing usando uma interface de linguagem natural. Com o Journey Agent, profissionais de marketing podem criar jornadas rapidamente, detectar e resolver conflitos de cronograma ou público-alvo, analisar o desempenho e os pontos de desistência e identificar as jornadas de melhor desempenho para replicá-lo em campanhas futuras. Ele capacita os profissionais a tomar decisões orientadas por dados, melhorar o envolvimento do cliente e simplificar a orquestração de jornadas.

O Journey Agent consiste em duas habilidades principais:
- **Criar Agente do Jornada**: criar e configurar jornadas de marketing por meio de prompts de linguagem natural
- **Jornada Analyze Agent**: analise jornadas, detecte problemas, descubra insights e otimize o engajamento do cliente

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

---

# Jornada Analyze Agent: visão geral e guia do usuário da habilidade

## Visão geral

O Journey Agent permitirá que os usuários do Journey Optimizer analisem e otimizem jornadas usando uma interface de linguagem natural. Com o Journey Agent, os profissionais podem identificar e resolver rapidamente conflitos de agendamento e/ou público-alvo, detectar pontos de abandono de usuários em uma jornada e fornecer insights ou recomendações. Ele capacita profissionais de marketing a tomar decisões baseadas em dados, melhorar o engajamento do cliente e simplificar a orquestração da jornada.

Saiba mais e descubra o agente rapidamente nesta [visão geral](https://experienceleague.adobe.com/en/slides/journey-agent-overview).

>[!AVAILABILITY]
>
>O Journey Agent está disponível para todos os clientes que têm acesso ao AI Assistant. No entanto, você precisará das seguintes permissões para usar totalmente os recursos do Journey Agent:
>
>**Exibir Jornadas**: essa permissão permite exibir insights sobre a jornada diretamente no Assistente de IA.
>
>**Gerenciar Jornadas**: a permissão Para permite que você crie novas jornadas diretamente no Assistente de IA.
>
>**Exibir segmentos**: essa permissão permite que você visualize insights sobre os públicos-alvo diretamente no Assistente de IA.
>
>**Gerenciar segmentos**: a permissão Para permite que você crie novos públicos diretamente no Assistente de IA.

![Amostra para o AJO Agent](./images/ajo-agent/ajo-agent-sample.png)

## Casos de uso

### Principais casos de uso da análise do Journey Agent

A habilidade de análise do Journey Agent oferece uma variedade de funcionalidades que podem ser aproveitadas para otimizar os esforços de marketing:

1. **Análise de fallout da jornada**

   - Identifique onde e por que os clientes desistem durante uma jornada.
   - Detecte padrões no comportamento do cliente que levam ao desengajamento.
   - Use insights para refinar o design da jornada e melhorar a retenção.

1. **Análise de sobreposição de público-alvo da jornada**

   - Analise a sobreposição de público-alvo em diversas jornadas.
   - Evite a fadiga de público-alvo causada pelo excesso de direcionamento.
   - Otimize a segmentação para garantir um engajamento equilibrado.

1. **Análise de sobreposição de cronograma da jornada**

   - Detecte conflitos de data entre jornadas programadas que direcionam o mesmo público-alvo.
   - Evite o excesso de comunicação e melhore a eficiência do agendamento.
   - Maximize o impacto no público-alvo garantindo que as jornadas ocorram nos momentos ideais.

1. **Insights operacionais**

   - Insights do Jornada com base em prompts - Surja insights operacionais sobre o jornada, ou seja, &quot;mostrar todas as jornadas ativas para mim&quot;.

Para cada uma dessas análises, o agente não apenas detecta problemas, mas também fornece **recomendações acionáveis para resolvê-los**.

## Habilidades dentro e fora do escopo

### **Dentro do escopo**

Os seguintes recursos são compatíveis com a análise do Journey Agent:

- **Consultas reativas**: permite que usuários façam perguntas específicas sobre o desempenho da jornada, a utilização do público-alvo e conflitos de agendamento.
- **Integração com outros agentes**: colabora com o Audience Agent e o Data Insights Agent para realizar análises mais aprofundadas.
- **Estrutura de resposta do agente**: raciocínio (explique a lógica), resumo da análise (destaque os pontos principais), detalhes do problema (descreva o problema) e recomendação (proponha as próximas etapas).

### **Fora do escopo**

As seguintes funcionalidades não são compatíveis no momento:

- **Criação automatizada de jornadas**
- **Detecção de anomalias em tempo real**
- **Sobreposição de canais**
- **Análise de entrada da jornada**
- **Análise de problemas técnicos**
- **Análise de fadiga**

## Prompts de amostra e prompts de exemplo

### Prompts comuns para a análise da jornada

Estes são alguns exemplos de prompts valiosos que os usuários podem aproveitar para explorar, monitorar e solucionar problemas em suas jornadas.

### Perguntas sobre o ciclo de vida da jornada

- &quot;Quando o [Nome da Jornada] foi publicado?&quot;
- &quot;Quando o [Nome da Jornada] foi interrompido?&quot;
- &quot;Listar todas as jornadas atualmente no modo de teste&quot;

### Perguntas sobre os recursos da jornada

- &quot;Quantas jornadas ao vivo eu tenho?&quot;
- &quot;Forneça uma lista de todas as jornadas recorrentes agendadas e seus tempos de execução esperados.&quot;

### Insights de público-alvo e de jornada

- &quot;Quais públicos-alvo são usados em mais de X jornadas?&quot;
- &quot;Liste todas as jornadas usando o [nome do público-alvo].&quot;

### Análise de fallout

- &quot;Quero analisar o fallout por nó para a Campanha do jornada de 4 de julho.&quot;
- &quot;Execute uma análise de fallout para a Campanha do jornada de 4 de julho.&quot;
- &quot;O que é perda de perfil ao longo da Campanha de 4 de julho do jornada?&quot;
- &quot;Mostrar onde os usuários estão saindo na Campanha do jornada de 4 de julho.&quot;

### Prompts de análise de conflitos

Use estes prompts para analisar potenciais conflitos entre jornadas, incluindo sobreposições de agendamento e de público-alvo:

- &quot;Você pode fazer uma análise abrangente dos conflitos da sua jornada [Nome da Jornada] com informações de tipo de conflito (agendamento/público) com jornadas ativas/em execução?&quot;
- &quot;Faça uma análise de conflito de agendamento para a jornada [Nome da Jornada] com informações de tipo de conflito.&quot;
- &quot;Faça uma análise de sobreposição de público-alvo para a jornada [Nome da Jornada] com informações de tipo de conflito.&quot;
- &quot;Há algum conflito de agendamento para a jornada [Nome da Jornada]?&quot;
- &quot;Mostrar conflitos de sobreposição de público-alvo para a jornada [Nome da Jornada].&quot;
- &quot;Analisar todos os conflitos da jornada [Nome da Jornada] com outras jornadas ativas.&quot;
- &quot;Quais são os conflitos atuais para a jornada [Nome da Jornada]?&quot;
- &quot;Verifique se o [Nome da Jornada] da jornada tem conflitos de público com outras jornadas.&quot;
- &quot;Verifique se há conflitos de agendamento envolvendo o [Nome da Jornada] da jornada.&quot;
- &quot;Quero saber sobre todos os conflitos de jornada para [Nome da Jornada].&quot;
- &quot;Há algum conflito de jornadas ao vivo com [Nome da Jornada] por agenda ou público-alvo?&quot;
- &quot;Identifique tipos de conflito para a jornada [Nome da Jornada] em comparação à execução de jornadas.&quot;
- &quot;Mostrar públicos sobrepostos para a jornada [Nome da Jornada] e outras jornadas.&quot;
- &quot;Destaque as sobreposições de agendamento entre a jornada [Nome da Jornada] e jornadas ativas.&quot;
- &quot;A jornada [Nome da Jornada] está em conflito com alguma outra jornada?&quot;
- &quot;Detecte e liste conflitos para [Nome da Jornada].&quot;
- &quot;Relate todos os tipos de conflitos da jornada [Nome da Jornada].&quot;
- &quot;Detalhamento de conflitos (agendamento e público-alvo) para [Nome da Jornada].&quot;
- &quot;O [Nome da Jornada] possui conflitos que podem afetar o desempenho?&quot;
- &quot;Há algum conflito ativo afetando [Nome da Jornada]?&quot;
- &quot;Listar jornadas em conflito com [Nome da Jornada] por agenda ou público-alvo.&quot;
- &quot;A jornada [Nome da Jornada] acionou alertas de conflito?&quot;
- &quot;Localize possíveis conflitos de público-alvo para a jornada [Nome da Jornada].&quot;
- &quot;Analisar o risco de conflito da jornada [Nome da Jornada].&quot;
- &quot;Forneça diagnósticos de conflito para [Nome da Jornada].&quot;

## Práticas recomendadas

### Práticas recomendadas de criação de prompts

Para maximizar a eficácia da análise do Journey Agent, siga estas práticas recomendadas:

1. **Seja específico(a)**: use prompts claros e concisos para obter insights direcionados. Por exemplo, em vez de perguntar &quot;Quais são minhas jornadas?&quot;, especifique &quot;Listar todas as jornadas criadas no último mês&quot;.
1. **Combine insights**: integre insights do Audience Agent e do Data Insights Agent para obter uma visão integral do desempenho da jornada.
1. **Refinamento iterativo**: use as análises de fallout e de sobreposição para refinar continuamente o design e o agendamento da jornada.

### Práticas recomendadas de configuração

- **Defina objetivos claros**: antes de analisar as jornadas, estabeleça metas claras (por exemplo: melhorar a retenção, aumentar as conversões).
- **Monitore regularmente**: agende revisões regulares do desempenho da jornada para identificar tendências e anomalias.
- **Otimize a segmentação**: mantenha uma segmentação de público-alvo equilibrada para evitar fadiga e maximizar o engajamento.

---

## Slides e apresentações

>[!NOTE]
>
>Os slides e o material de apresentação do Journey Agent estarão disponíveis aqui. Verifique novamente em breve se há atualizações.
