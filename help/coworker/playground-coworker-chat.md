---
title: Introdução Ao Bate-Papo Entre Colegas No Playground
description: Saiba como usar o Bate-papo com colegas de trabalho no Playground para explorar como os prompts em linguagem natural podem ajudar você a aprender, investigar e refinar seu trabalho.
hide: true
source-git-commit: ea975ce8a0386f9d340014ab7755761815bcf8ae
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%

---

# Introdução ao Bate-papo com colegas de trabalho no Playground

Use o Bate-papo com colegas de trabalho no Playground para explorar como os prompts em linguagem natural podem ajudar você a aprender, investigar e refinar seu trabalho. O Playground fornece exemplos de maneiras de iniciar uma conversa, para que você possa entender rapidamente o que o Bate-papo do Colaborador pode fazer.

>[!IMPORTANT]
>
>Use o seguinte para concluir este exercício:
>
>- Link: [ao.adobe.io](https://ao.adobe.io/)
>- Instância: AEP GenAI - VA7
>- Sandbox: `fsi-box`

## Demonstração do colega de trabalho do AI: [!DNL weBank] Campanha de atualização de cartão de crédito

Esse exercício abrange o Real-Time CDP e o Adobe Journey Optimizer.

Você é um estrategista da CX Enterprise na **[!DNL weBank]**, uma empresa de serviços financeiros digitais. Use o Colaborador de IA para ir de dados brutos a uma campanha ao vivo — inteiramente por meio de conversas.

## Parte 1: Entenda sua empresa

### 1.1 — Obter a posição da terra

**Aviso**

> Dê-me uma visão geral da minha sandbox — quantos públicos, conjuntos de dados e destinos tenho?

**Resultado esperado**

O colaborador retorna um estoque completo de sandbox em segundos:

| Recurso | Count |
| --- | --- |
| Públicos-alvo | 21 |
| Conjuntos de dados | 30 |
| Esquemas | 28 |
| Fontes | 3 |
| Destinos | 1 (Amazon S3) |
| Jornadas | 0 |

### 1.2 — Quais públicos-alvo já existem?

**Aviso**

> Listar todos os meus públicos-alvo classificados por tamanho

**Resultado esperado**

O colaborador lista 21 públicos-alvo classificados por tamanho, de 8.012 perfis para 0:

| Categoria | Público-alvo | Perfis |
| --- | --- | --- |
| Pontuações de propensão | Atualização de Cartão de Crédito Alta | 1,195 |
| Pontuações de propensão | Médio | 4,113 |
| Pontuações de propensão | Baixo | 8,012 |
| Propensão hipotecária | Alto | 1,233 |
| Propensão hipotecária | Médio | 4,141 |
| Propensão hipotecária | Baixo | 7,946 |
| Níveis de valor da conta | +500 K | 4,377 |
| Níveis de valor da conta | 250-500 K | 4,537 |
| Níveis de valor da conta | 100-250 K | 2,666 |
| Níveis de valor da conta | 50-100 K | 894 |
| Níveis de valor da conta | &lt;50.000 | 846 |
| Demografia | Feminino | 6,719 |
| Demografia | Masculino | 6,601 |
| Geografia | Costa Leste | 2,260 |
| Geografia | Costa Oeste | 1,740 |
| Aceitação de canal | Email | 6,597 |
| Aceitação de canal | SMS | 6,675 |
| Aniversário | Aniversário deste mês | 0 |
| Aniversário | No prazo de 7 dias | 0 |
| Aniversário | Hoje | 0 |
| Aniversário | Próximos 30 dias | 0 |

Todos os públicos-alvo de aniversário atualmente mostram 0, pois dependem do tempo.

### 1.3 — Quais dados alimentam esses públicos?

**Aviso**

> Quais conjuntos de dados eu tenho que contêm dados do cliente?

**Resultado esperado**

O Colaborador identifica dois conjuntos de dados importantes de negócios e conjuntos de dados de sistema relacionados:

| Conjunto de dados | Descrição |
| --- | --- |
| **weBank: CRM** | Dados de perfil/conta do cliente (perfil + identidade ativada) |
| **weBank: Ações de Clientes** | Dados comportamentais do evento (perfil + identidade ativada) |

Os conjuntos de dados do System Journey Optimizer para sinais de engajamento incluem rastreamento de email, rastreamento de push, consentimento e feedback da mensagem.

## Parte 2: Descubra os campos certos

### 2.1 — Localizar campos de valor da conta

**Aviso**

> Quais campos estão disponíveis relacionados ao valor ou saldo da conta?

**Resultado esperado**

O colaborador exibe o campo primário e os campos relacionados no conjunto de dados **weBank: CRM**:

| Campo | Notas |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.totalAccountValue` | Campo principal; usado em todos os 5 públicos-alvo da camada Valor da conta |
| `numberOfAccounts` | Campo relacionado |
| `accountType` | Campo relacionado |
| `currentStatement` | Campo relacionado |
| `actionAmount` | Campo relacionado |

### 2.2 — Localizar campos de cartão de crédito

**Aviso**

> Localizar campos relacionados a cartão de crédito ou tipo de cartão

**Resultado esperado**

O colaborador identifica estes campos no esquema **weBank: CRM**:

| Campo | Descrição |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardType` | Tipo de cartão da loja (Visa, Mastercard, Amex) |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardHolder` | Nome do titular do cartão |

### 2.3 — Campos geográficos

**Aviso**

> Existe um campo para o estado ou região de origem?

**Resultado esperado**

O colaborador identifica campos geográficos no conjunto de dados **weBank: CRM**:

| Campo | Notas |
| --- | --- |
| `homeAddress.state` | Abreviação do estado dos EUA; usada em Vidas na Costa Leste e Vidas na Costa Oeste |
| `homeAddress.stateProvince` | Também encontrado |
| `homeAddress.region` | Também encontrado |
| `placeContext.geo.stateProvince` | Também encontrado |

## Parte 3: Encontre o público-alvo certo para uma campanha de reativação

### 3.1 — Solicite ajuda à IA para encontrar o público-alvo correto

**Aviso**

> Ajude-me a encontrar ou criar o público-alvo correto para uma campanha de reativação de cartão de crédito. Quero direcionar os clientes que tiveram alta ou média propensão para uma atualização de cartão de crédito, mas que ainda não tomaram medidas

**Resultado esperado**

O colaborador encontra dois públicos-alvo candidatos que nunca foram direcionados em uma jornada ou destino:

| Público-alvo | Perfis |
| --- | --- |
| Atualização de Cartão de Crédito Alta | 1,195 |
| Medium de atualização de cartão de crédito | 4,113 |

Opções recomendadas:

| Opção | Abordagem |
| --- | --- |
| **A** | Use ambos diretamente com ramificação de jornada — oferta agressiva para Alta qualidade e desenvolvimento do Medium |
| **B** | Criar um segmento de segmentos derivado com lógica de exclusão de atualização para um gerenciamento mais limpo |

Tamanho combinado: aproximadamente 5.308 perfis

### 3.2 — Criar o público-alvo do precision

**Aviso**

> Crie um público-alvo de clientes que estejam no público-alvo &quot;Propensões: alta atualização de cartão de crédito&quot; E tenham um valor de conta superior a US$ 250.000 E optem por enviar email

Nomeie-o **Atualização Platinum - Email de Alto Valor Qualificado** → Selecionar Lote → Aprovar Plano

**Resultado esperado**

O colaborador cria camadas de propensão de ML, valor financeiro e qualificação de canal em um segmento de precisão — trabalho que normalmente exigiria um tíquete de equipe de dados.

### 3.3 — Estimativa da dimensão e cascata

**Aviso**

> Qual é o tamanho desse público-alvo? Mostre-me o detalhamento da cascata.

**Resultado esperado**

O colaborador retorna uma estimativa de contagem de perfis em tempo real e um gráfico visual em cascata:

| Etapa de filtro | Resultado |
| --- | --- |
| Atualização de cartão de crédito Alta propensão | Aproximadamente 1.195 perfis |
| + Valor da conta acima de US$ 250 mil | Estreita ainda mais |
| + Aceitação de email | Contagem endereçável final |

Isso mostra exatamente qual condição é o maior filtro e se os critérios devem ser afrouxados.

### 3.4 — Verificar públicos semelhantes

**Aviso**

> Existem públicos-alvo semelhantes ao que acabei de criar?

**Resultado esperado**

O colega de trabalho confirma que não existe um público-alvo combinado único, mas todos os elementos já estão presentes:

| Bloco de construção | Detalhes |
| --- | --- |
| Propensões: alta atualização de cartão de crédito | Pontuação ≥ 90 |
| Valor da conta: 250-500K | Público existente |
| Valor da conta: +500K | Público existente |
| Aceitação de email | `consents.marketing.email.val = "y"` |

O parceiro confirma que não há risco de duplicação e recomenda continuar.

## Parte 4: Criar a Jornada

### 4.1 — Tenha ideias de jornada baseadas em seus dados

**Aviso**

> Com base em casos de uso populares em serviços financeiros, sugira algumas jornadas de resultados rápidos que eu possa criar com os públicos-alvo que tenho

**Resultado esperado**

O colega de trabalho sugere cinco ideias de jornada concretas baseadas em públicos reais:

| Jornada ideia | Públicos-alvo |
| --- | --- |
| Toque de fidelidade de aniversário | Aniversário em 7 dias + níveis de Valor da conta |
| Criação de atualização de cartão de crédito | Atualização do CC superior + aceitação de email |
| Mortgage Regional Outreach | Hipoteca alta + Costa Leste/Oeste |
| Atualização de Aviso de Nível Avançado | Valor da conta: +500K |
| Ativação entre canais de Opt-in | Aceitação de email menos aceitação de SMS |

### 4.2 — Criar a jornada de atualização de cartão de crédito

**Aviso**

> Crie uma jornada usando o público-alvo &quot;Atualização do Platinum - Elegível para email de alto valor&quot;. Envie uma notificação por push apresentando os benefícios do WeBank Platinum Card. Espere 3 dias. Se o cliente não tiver solicitado, envie um SMS com uma oferta por tempo limitado de 0% ABR por 12 meses em transferências de saldo. Espere mais 5 dias. Se ainda assim nenhum aplicativo, envie uma notificação por push final com um convite de banqueiro pessoal.

Revisar plano → Aprovar plano → Conceder permissões

**Resultado esperado**

O Colaborador cria uma jornada completa de 2 canais e 3 toques a partir de uma única descrição de idioma natural, incluindo temporizadores de espera, verificações de condição e ofertas de escalonamento.

### 4.3 — Bônus: Criar uma jornada a partir de uma imagem

**Aviso**

> Criar esta jornada a partir da imagem que eu carreguei

**Resultado esperado**

O colaborador lê a imagem carregada — incluindo nós, canais, tempos de espera e condições — e gera a jornada completa no Journey Optimizer. Isso transforma um artefato de planejamento diretamente em uma jornada implantável.

### 4.4 — Verificação de conflitos

**Aviso**

> Existem jornadas ativas que podem entrar em conflito com a jornada que acabei de criar?

**Resultado esperado**

O colaborador verifica automaticamente todas as jornadas ativas em busca de sobreposição de público-alvo, colisões de agendamento e saturação de canal.

## Parte 5: Transformar as quedas de Jornada em um novo público

### 5.1 — Identificação do ponto de devolução

**Aviso**

> Mostre-me a jornada que acabei de criar e identifique qual etapa tem a maior queda

**Resultado esperado**

O colaborador analisa os eventos de etapa do jornada e exibe o nó com a taxa de saída mais alta. Por exemplo:

> 68% dos perfis que receberam o primeiro email nunca o abriram e saíram antes da etapa de SMS.

### 5.2 — Criar um público-alvo suspenso

**Aviso**

> Transforme esses menus suspensos do jornada em um novo público-alvo — pessoas que entraram na jornada de atualização do Platinum, mas nunca chegaram à etapa de SMS

Nomeie-o **Atualização Platinum - Email para Não Respondentes** → Selecionar Lote → Aprovar Plano

**Resultado esperado**

O colaborador cria um novo público-alvo com base nos dados comportamentais da jornada — perfis que entraram na jornada, mas não avançaram para a etapa de SMS. Esse público-alvo é imediatamente utilizável para uma campanha de acompanhamento.

### 5.3 — Reativar as quedas

**Aviso**

> Crie uma jornada de reativação para o público-alvo &quot;Platinum Upgrade - Email Non-Responders&quot;. Tente uma abordagem diferente — comece com uma notificação por push que destaca uma oferta de 75.000 pontos de bônus por tempo limitado, aguarde 2 dias e envie um convite por correspondência direta para visitar sua filial local.

Revisar plano → Aprovar plano → Conceder permissões

**Resultado esperado**

O colaborador cria uma jornada de recuperação dedicada usando diferentes canais e mensagens para não respondentes. Agora você encerrou o ciclo em um vazamento de conversão — inteiramente por meio de conversações.

## Parte 6: Controle de qualidade e validação automatizados

### 6.1 — Verificação de integridade da frescura e da assimilação de dados

**Aviso**

> Existem problemas de qualidade de dados com os conjuntos de dados que alimentam meus públicos-alvo? Verifique a integridade da assimilação para o weBank: CRM e weBank: Ações do cliente

**Resultado esperado**

O colaborador relata a integridade da assimilação para cada conjunto de dados:

| Conjunto de dados | Status | Detalhes |
| --- | --- | --- |
| **weBank: CRM** | Integridade boa | 39 registros assimilados, 32 para perfil, zero falhas |
| **weBank: Ações de Clientes** | Sinalizador secundário | 441 registros assimilados; 35 tinham carimbos de data e hora expirados; aproximadamente 8% excluídos devido à janela TTL |

Recomendação: revise as configurações de TTL ou verifique se há registros obsoletos no sistema de origem.

### 6.2 — Validar a jornada antes de publicar

**Aviso**

> Revise a jornada de atualização do Platinum para ver se há erros ou problemas de qualidade — verifique se há temporizadores de espera ausentes, caminhos sem acesso, configurações de canal ausentes e lacunas de qualificação de público

**Resultado esperado**

O colaborador inspeciona a estrutura da jornada e sinaliza problemas como:

| Tipo de problema | Exemplo |
| --- | --- |
| Caminhos de beco sem saída | Caminhos que não terminam com um nó final |
| Configuração de canais | Ações sem configurações de superfície de canal |
| Temporizadores de espera | Temporizadores que podem causar problemas do SLA |
| Conteúdo | Nós com conteúdo ausente |

## Parte 7: Monitoramento e governança

### 7.1 — Rastrear a integridade do público ao longo do tempo

**Aviso**

> Mostre-me como o público-alvo &quot;Propensões: alta atualização de cartão de crédito&quot; mudou nos últimos 30 dias

**Resultado esperado**

O colaborador retorna uma visualização de série temporal do crescimento ou declínio do público-alvo com análise de tendência, ajudando você a identificar se a pontuação do modelo de aprendizado de máquina está deslocada ou se as alterações de dados upstream estão afetando a qualificação.

### 7.2 — Diagnosticar uma alteração

**Aviso**

> Por que o público-alvo &quot;Account Value: +500K&quot; caiu recentemente?

**Resultado esperado**

O colaborador executa a análise causal ao decompor a alteração em:

| Fator | Pergunta |
| --- | --- |
| Atualização de dados | Havia uma lacuna de assimilação? |
| Alterações na política de mesclagem | A compilação de perfil mudou? |
| Alterações na origem upstream | Os dados do CRM pararam de fluir? |
| Comportamento real do cliente | Os valores da conta realmente diminuíram? |

Substitui de 1 a 2 dias da triagem do analista.

