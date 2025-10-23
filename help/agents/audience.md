---
title: Audience Agent
description: Saiba como usar o Audience Agent para criar públicos, exibir alterações de público, detectar públicos duplicados e exibir insights do público.
source-git-commit: f2b5bd1a59055a8ca6785abfc2d0a336eea7fd98
workflow-type: tm+mt
source-wordcount: '859'
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

<!-- - Find your audience size and detect significant changes in audience size
  - This lets you find audiences that have suddenly grown or shrunk, letting you better analyze potential market changes
- Detect duplicate audiences
  - This lets you reduce redundancies with your created audiences
- Find audiences based on full or partial attributes named
  - This lets you more easily navigate through your audience inventory
- Discover XDM fields you can use to define an audience
  - This skill lets you more easily identify the right fields to use in your audience based on context and relevance -->

A Audience Agent não **oferece suporte atualmente** aos seguintes recursos:

- Criação de público-alvo com base no conhecimento
   - A criação de público-alvo com base no conhecimento é criar um público-alvo com base nos atributos e eventos fornecidos
   - Além disso, é possível estimar o tamanho potencial do público-alvo antes da criação. Isso permite iterar rapidamente no público-alvo mais eficiente antes que esteja pronto para ativação
   - O suporte para esse recurso será lançado em breve
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

![O Assistente de IA exibe uma tabela que contém os nomes e as IDs dos públicos-alvo da conta que compartilham as mesmas regras de público-alvo.](./images/audience/duplicate-account-audience.png)

+++

### Recuperar tamanho do público

Qual é o tamanho atual do meu público-alvo &quot;Membros Gold-star na Califórnia_f153e1&quot;?

+++ Resposta

![O Assistente de IA informa o tamanho atual do público-alvo que foi perguntado.](./images/audience/current-size.png)

+++

Qual é o meu maior público-alvo?

+++ Resposta

![O Assistente de IA fornece informações sobre o público-alvo com mais perfis, incluindo nome e ID de público-alvo.](./images/audience/largest-audience.png)

+++

### Detectar alterações significativas no tamanho do público

Quais públicos-alvo aumentaram de tamanho em mais de 20% na última semana?

+++ Resposta

![O Assistente de IA exibe uma tabela que lista os nomes de todos os públicos-alvo que correspondem à consulta. Ele também mostra o aumento percentual, o tamanho do público-alvo atual, bem como o tamanho do público-alvo anterior.](./images/audience/increase-past-week.png)

+++

Quais públicos-alvo diminuíram em tamanho em mais de 10% no último mês?

+++ Resposta

![O Assistente de IA exibe uma tabela que lista os nomes de todos os públicos-alvo que correspondem à consulta. Ele também mostra o tamanho atual do público, o tamanho anterior do público, bem como a data do tamanho antigo do público.](./images/audience/decrease-month.png)

+++

Qual é o meu público que cresce mais rápido?

+++ Resposta

![O Assistente de IA informa o nome do público-alvo que cresce mais rápido, bem como o tamanho atual e a porcentagem de crescimento.](./images/audience/fastest-growing.png)

+++

## Próximas etapas

Depois de ler este guia, você terá uma melhor compreensão do Audience Agent e de quais recursos ele oferece suporte. Para obter mais informações sobre agentes no Adobe Experience Platform, leia a [visão geral do Agent Orchestrator](./agent-orchestrator.md).

