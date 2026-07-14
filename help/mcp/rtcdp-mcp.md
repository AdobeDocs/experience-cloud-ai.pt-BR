---
title: Real-Time CDP MCP (Beta)
description: Saiba como conectar o Adobe Real-Time CDP a clientes MCP usando o servidor MCP.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 3%

---

# Ferramentas Real-Time CDP no CX Co-worker Gateway {#rtcdp-mcp}

Você pode usar as ferramentas do produto Real-Time CDP MCP para inspecionar públicos, destinos, origens, namespaces de identidade e integridade da ativação de um cliente compatível com MCP. Essas ferramentas estão disponíveis por meio do [gateway unificado do CX Co-worker Gateway](overview.md), quando sua organização está habilitada e sua conta de usuário tem as permissões necessárias da Real-Time CDP.

>[!AVAILABILITY]
>
>A ferramenta do produto Real-Time CDP está no Beta. O acesso é apenas por convite e requer a habilitação da organização da Adobe. Consulte [Acessar as ferramentas do CX Co-worker Gateway](access.md).

## Principais recursos {#mcp-capabilities}

As ferramentas do Real-Time CDP fornecem uma superfície de monitoramento e triagem somente leitura. Você pode:

* Liste e inspecione públicos, incluindo estado do ciclo de vida, origem e namespace de identidade.
* Revise a avaliação do público-alvo e os trabalhos de exportação para identificar falhas recentes.
* Inspecione as contas de destino configuradas, os fluxos de destino e o histórico de execução de ativação.
* Inspecione conectores de origem, contas, fluxos e histórico de execução de assimilação.
* Listar namespaces de identidade e políticas de mesclagem.

>[!IMPORTANT]
>
>Todas as ferramentas do Real-Time CDP na Beta atual são somente leitura. Não há suporte para criar, atualizar, ativar ou excluir públicos, destinos, fontes ou fluxos de dados.

## Ferramentas disponíveis {#mcp-tools}

| Área | Ferramenta | Descrição |
| --- | --- | --- |
| Públicos-alvo | `search_audiences` | Liste e pesquise públicos-alvo por nome, tipo de entidade, estado do ciclo de vida, namespace de identidade ou origem. |
| Públicos-alvo | `preview_audience_membership` | Estime o tamanho de uma expressão de segmento do PQL ou SDD antes de salvá-la como um público. |
| Públicos-alvo | `inspect_audience_evaluation_jobs` | Recupere registros do trabalho de avaliação do segmento para diagnosticar problemas de atualização do público-alvo ou confirmar o histórico de avaliação recente. |
| Públicos-alvo | `inspect_audience_export_jobs` | Recupere registros de trabalho de exportação de público-alvo para confirmar as exportações concluídas ou exibir detalhes de falha. |
| Destinos | `search_destination_connectors` | Listar tipos de conectores de destino disponíveis na plataforma. |
| Destinos | `search_destination_accounts` | Listar contas de destino autenticadas. |
| Destinos | `search_destination_input_connections` | Recupere a entrada do lado do Experience Platform de um fluxo de destino. |
| Destinos | `search_destination_output_connections` | Recupere o ponto de extremidade externo de um fluxo de destino, incluindo o caminho de destino, o formato de arquivo e a configuração de entrega. |
| Destinos | `search_destination_flows` | Liste e inspecione os fluxos de ativação de destino configurados, incluindo estado, mapeamentos e agendamento. |
| Destinos e origens | `inspect_flow_runs` | Recupere o histórico de execução do fluxo de origem e de destino, incluindo status, tempo, contagens de registros e detalhes de falhas. |
| Fontes | `search_source_connectors` | Listar tipos de conectores de origem disponíveis na plataforma. |
| Fontes | `search_source_accounts` | Listar contas de origem autenticadas. |
| Fontes | `search_source_input_connections` | Recupere o que um fluxo de origem extrai de uma conta. |
| Fontes | `search_source_output_connections` | Recupere o destino do conjunto de dados do Experience Platform para um fluxo de origem. |
| Fontes | `search_source_flows` | Liste e inspecione os pipelines configurados de assimilação de origem, incluindo estado, mapeamentos e agendamento. |
| Identidade | `search_identity_namespaces` | Listar definições de namespace de identidade na sandbox. |
| Identidade | `search_merge_policies` | Registros da política de mesclagem de listas que controlam como os Perfis de clientes em tempo real são montados. |

## Exemplo de prompts {#mcp-use-cases}

| Meta | Exemplo de prompt |
| --- | --- |
| Listar públicos | &quot;Listar meus públicos-alvo na sandbox do `prod`.&quot; |
| Inspecionar um público | &quot;Mostre-me os detalhes e o estado do ciclo de vida da ID de público-alvo `abc123`.&quot; |
| Diagnosticar problemas de avaliação | &quot;Mostre-me os trabalhos de avaliação de público-alvo mais recentes e sinalize falhas.&quot; |
| Verificar trabalhos de exportação | &quot;Liste os trabalhos de exportação de público-alvo recentes e mostre-me o status de cada um.&quot; |
| Estimar tamanho do público | &quot;Estime o tamanho desta expressão PQL antes de salvá-la: `homeAddress.country = 'US'`.&quot; |
| Revisar configuração de destino | &quot;Listar meus fluxos de ativação de destino e mostrar quais estão habilitados ou desabilitados.&quot; |
| Investigar uma execução de ativação com falha | &quot;Mostrar o histórico de execuções da ID de fluxo `xyz789` e resumir os erros.&quot; |
| Revisar assimilação da origem | &quot;Mostrar histórico de execuções recentes para a ID do fluxo de origem `src456` e sinalizar falhas.&quot; |
| Inspecionar configuração de identidade | &quot;Quais namespaces de identidade são configurados na minha sandbox?&quot; |

## Permissões {#mcp-context}

Sua organização da Adobe e o contexto de sandbox são estabelecidos uma vez no nível de conexão de gateway e se aplicam a todas as famílias de ferramentas, de modo que você não alterne organizações ou sandboxes das ferramentas do Real-Time CDP. Para definir esse contexto para uma sessão, consulte [Contexto do produto para chamadas de ferramenta](install.md#mcp-connect-params).

Sua conta de usuário deve ter permissão para exibir os recursos do Real-Time CDP que você consulta. O gateway não ignora as permissões do produto.

## Limitações conhecidas {#mcp-limitations}

| Limitação | Descrição | Solução alternativa |
| --- | --- | --- |
| Superfície somente leitura | As ferramentas do Real-Time CDP só expõem as APIs de recuperação. Não é possível criar, atualizar, ativar ou excluir públicos, destinos, fontes ou fluxos de dados. | Use a interface do usuário do Real-Time CDP ou as APIs do Experience Platform para operações de gravação. |
| Sem métricas de envolvimento ou entrega | As ferramentas não retornam estatísticas de entrega downstream, envolvimento ou métricas de conversão das plataformas de destino. | Use os relatórios, as ferramentas do Customer Journey Analytics ou as ferramentas do Adobe Analytics da plataforma de destino para os dados de envolvimento e conversão. |
| A consulta de segmento deve ser criada externamente | `preview_audience_membership` requer uma expressão válida de PQL ou SDD. A ferramenta não compõe a consulta para você. | Crie a expressão no Construtor de segmentos ou na API do Serviço de segmentação e cole-a no prompt. |
| Paginação por meio de tokens de continuação | As ferramentas de lista retornam resultados paginados. A enumeração completa em sandboxes muito grandes requer a encadeamento de tokens de continuação. | Restrinja consultas usando filtros como nome, estado, especificação de conexão ou intervalo de tempo. |
| A filtragem de execução de ativação é baseada apenas no tempo | A inspeção de execução de ativação suporta a filtragem por status e carimbo de data e hora de conclusão, mas não diretamente por tipo de erro ou plataforma de destino. | O filtro por `flowId` primeiro no escopo é executado para um fluxo de destino específico. |

