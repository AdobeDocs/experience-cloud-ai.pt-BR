---
title: Ferramentas Adobe Experience Platform no CX Co-worker Gateway
description: Saiba quais ferramentas do Adobe Experience Platform estão disponíveis por meio do CX Co-worker Gateway.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 8%

---


# Ferramentas do Adobe Experience Platform no Adobe CX Co-worker Gateway {#aep-mcp}

Você pode usar as ferramentas de produto do Adobe Experience Platform para inspecionar esquemas, conjuntos de dados, configuração de governança de dados, recursos do Serviço de consulta e eventos de auditoria de um cliente compatível com MCP. Essas ferramentas estão disponíveis por meio do [Adobe CX Co-worker Gateway](overview.md), quando sua organização está habilitada e sua conta de usuário tem as permissões necessárias do Experience Platform.

>[!AVAILABILITY]
>
>A ferramenta do produto Experience Platform está no Beta. O acesso é apenas por convite e requer a habilitação da organização da Adobe. Consulte [Acessar as ferramentas do CX Co-worker Gateway](access.md).

## Resumo

| Ferramenta | Descrição | Recurso | Recursos | Status |
| --- | --- | --- | --- | --- |
| `search_allowed_ip_ranges` | Recuperar restrições de acesso de IP do Serviço de Consulta | Autenticação do Data Distiller · Intervalos IP | list | Ativo |
| `search_audit` | Listar eventos de auditoria de atividades do usuário no Experience Platform | Consulta de auditoria · eventos de auditoria | lista, filtrar por tipo de ativo, ação, status, intervalo de tempo | Ativo |
| `search_datasets` | Consultar metadados do conjunto de dados e da assimilação em lote | API do catálogo · Conjuntos de dados, lotes | listar, obter, filtrar, listar último, listar arquivos | Ativo |
| `search_class_relations` | Pesquisar relacionamentos de classe comercial do Experience Platform | Relações de classe · índice YAML estático | pesquisa por token, correspondência parcial de vários termos | Ativo |
| `search_data_access` | Listar arquivos de lotes de assimilação com falha | API de acesso a dados · lotes com falha | listar arquivos com falha | Ativo |
| `search_data_lake` | Inspecionar metadados do conjunto de dados e integridade do lote | API Data Lake · conjuntos de dados, lotes | obter, obter tamanho, listar lotes com falha | Ativo |
| `search_dule` | Consultar rótulos, políticas e ações de governança de dados | Controle de dados · rótulos, políticas, ações de marketing | lista, obter, lista ativada, avaliar | Ativo |
| `search_query_service` | Consulta consultas SQL, modelos, agendamentos, alertas | Serviço de consulta · consultas, modelos, agendamentos, alertas | listar, obter, filtrar, obter parâmetros de conexão | Ativo |
| `search_schema_registry` | Consultar esquemas XDM, grupos de campos, classes, tipos | Registro de Esquemas · esquemas, grupos de campos, classes, data_types, descritores | listar, obter, filtrar por contêiner | Ativo |

## Referência da ferramenta

### search_allowed_ip_ranges

**Recurso:** Autenticação do Data Distiller · Intervalos IP
**Status:** Ativo

Recupere todas as restrições de acesso IP configuradas para o Serviço de consulta na sandbox atual. Retorna a ID da organização e a lista de intervalos de IP permitidos. Disponível somente para clientes com o complemento Data Distiller.

**Recursos:** listar intervalos IP permitidos para o Serviço de Consulta

Nenhum parâmetro.

### search_audit

**Recurso:** Consulta de auditoria · eventos de auditoria
**Status:** Ativo

Lista registros com carimbo de data e hora de atividades do usuário nos serviços da Experience Platform. Retorna o tipo de ação, email do usuário, informações do ativo e status do evento. Use `asset_type` e `action` para restringir os resultados. O padrão é os últimos 7 dias quando nenhum intervalo de tempo é especificado. Limitado aos últimos 1000 registros e eventos dos últimos 90 dias.

**Recursos:** liste eventos de auditoria, filtre por tipo de ativo, ação, status, intervalo de tempo, paginar

**Parâmetros:**

| Parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| `action` | Não | Filtrar por tipo de ação. Valores comuns (separados por vírgula para OR): `Create`, `Delete`, `Update`, `Enable`, `Disable` |
| `asset_type` | Não | Filtrar por tipo de ativo. Deve ser um dos seguintes: `Dataset`, `Schema`, `Segment`, `Destination`, `Source Data Flow`, `Merge Policy`, `Identity Namespace`, `Identity Graph`, `Sandbox`, `Role`, `Query`, `Scheduled Query`, `Datastream`, `Computed Attribute`, `Field Group`, `Class`, `Data Types`, `Account`, `Product Profile`, `Query Template`, `Work Order`, `Audit Logs`, `Access Control Policy` |
| `status` | Não | Filtrar por status do evento. Valores: `Success`, `Failure`, `Allow`, `Deny`. Separado por vírgulas para OR |
| `start_time` | Não | Carimbo de data e hora mais antigo. ISO 8601 UTC com ms, ex.: `2024-01-15T00:00:00.000Z` |
| `end_time` | Não | Carimbo de data/hora mais recente. ISO 8601 UTC com ms |
| `property_filter` | Não | Expressão de filtro bruta, ex.: `action==create`. Preferir os parâmetros dedicados acima |
| `orderby` | Não | Ordem de classificação: `timestamp` (asc) ou `-timestamp` (desc) |
| `limit` | Não | Número máximo de resultados (3-1000, padrão 50) |
| `start` | Não | Deslocamento de paginação. Incrementar por valor de limite para cada página |
| `query_id` | Não | ID da consulta de uma resposta anterior para repetir a mesma consulta |

### search_datasets

**Recurso:** API de catálogo · dataSets, lotes
**Status:** Ativo

Ferramenta de expedição unificada para o serviço de catálogo da Experience Platform. Consultar metadados do conjunto de dados (referências de esquema, tags, informações de criação) ou registros de assimilação em lote (status, métricas, listagens de arquivos). Use `dataset/list` para descobrir conjuntos de dados, `batch/list` para verificar a integridade da assimilação e `batch/list_files` ou `batch/get_meta_files` para inspecionar conteúdo de lote específico. Todas as operações são somente leitura.

**Recursos:** listar conjuntos de dados, obter conjunto de dados, listar lotes, obter lote, listar o último lote por conjunto de dados, listar arquivos em lotes, obter metarquivos em lotes (erros de linha, arquivos de entrada)

**Parâmetros:**

| Parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| `entity_type` | Sim | `dataset` ou `batch` |
| `operation` | Sim | `list`, `get`, `list_last`, `list_files`, `get_meta_files`. Combinações válidas: conjunto de dados → lista, get; lote → todos os cinco |
| `resource_id` | Não | Conjunto de dados ou ID do lote. Necessário para `dataset/get`, `batch/get`, `batch/list_files`, `batch/get_meta_files` |
| `query_params.limit` | Não | Máximo de resultados por página (máx. 100). Aplica-se a todas as operações de lista |
| `query_params.start` | Não | Deslocamento de paginação. Aplica-se a todas as operações de lista |
| `query_params.order_by` | Não | Direção de classificação, por exemplo, `asc:created,updated`. Aplica-se a todas as operações de lista |
| `query_params.properties` | Não | Incluo na lista de permissões de propriedades separado por vírgulas. Aplica-se a dataset/list, dataset/get, batch/list, batch/list_last |
| `query_params.name` | Não | Filtrar conjuntos de dados por nome (somente conjunto de dados/lista) |
| `query_params.tags` | Não | Filtrar conjuntos de dados por marcas, por exemplo `unifiedProfile:enabled:true` (somente conjunto de dados/lista) |
| `query_params.property_filter` | Não | Filtro Regex em objetos de resposta (conjunto de dados/lista e lote/lista) |
| `query_params.status` | Não | Filtrar lotes por status: `success`, `failed`, `loading`, `active` (somente lote/lista) |
| `query_params.dataset_id` | Não | Escopo lotes para um conjunto de dados específico (batch/list e batch/list_last) |
| `query_params.created_after` | Não | Filtrar lotes criados após o carimbo de data e hora Unix em ms (somente lote/lista) |
| `query_params.created_before` | Não | Filtrar lotes criados antes do carimbo de data e hora Unix em ms (somente lote/lista) |
| `query_params.last_batch_status` | Não | Filtrar por status do último lote (somente batch/list_last) |
| `query_params.aggregate` | Não | Retornar métricas agregadas no nível raiz (somente batch/get) |
| `query_params.path` | Não | Arquivo Meta a ser baixado: `row_errors`, `input_files`, `row_errors_sample.json` (batch/get_meta_files somente) |

### search_class_Relations

**Recurso:** Relações de Classe · índice YAML estático
**Status:** Ativo

Procure relações de classe comercial da Experience Platform por nome usando o índice estático `class_relations_v1.yaml`. Não são feitas chamadas à API da Experience Platform. Aceita um único termo ou termos separados por vírgulas; cada termo é comparado a nomes de classe usando a correspondência de token parcial. Retorna classes correspondentes com relações de encaminhamento (para o que cada classe aponta) e relações de reversão (para as quais as classes apontam de volta). Use-a para entender os relacionamentos de entidade antes de criar consultas, fluxos de dados ou composições de esquema.

**Recursos:** pesquisa por token, pesquisa separada por vírgulas multitermo, correspondência de token parcial, expansão de sinônimo bidirecional

**Parâmetros:**

| Parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| `query` | Sim | Nome da classe comercial ou tipo de objeto a ser pesquisado. Suporta correspondências parciais de token (`dat` correspondências `dataset`, `data_type`, etc.). Passe vários termos separados por vírgula para procurar várias classes de uma só vez (por exemplo, `dataset, schema`) |
| `n` | Não | Número máximo de resultados correspondentes a serem retornados (padrão: 5, min 1) |

### search_data_access

**Recurso:** API de acesso a dados · lotes com falha
**Status:** Ativo

Acesse arquivos de lotes de assimilação de dados com falha da Experience Platform. Use `failed_batch/list_failed` para listar os arquivos pertencentes a um lote com falha para diagnóstico de falha. Requer uma ID de lote para todas as operações. Observação: `file/get` e `dataset/preview` estão desabilitados porque expõem os dados reais do registro. Todas as operações são somente leitura.

**Recursos:** listam arquivos de um lote de assimilação com falha

**Parâmetros:**

| Parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| `entity_type` | Sim | `failed_batch` — listar arquivos de um lote de assimilação com falha |
| `operation` | Sim | `list_failed` — a única operação suportada |
| `resource_id` | Sim | ID do lote com falha |
| `query_params.start` | Não | Índice de início de paginação, ex.: `1` |
| `query_params.limit` | Não | Número de resultados por página, por exemplo: `10` |
| `query_params.path` | Não | Filtro de nome de arquivo completo, ex.: `profiles.csv` |


### search_data_lake

**Recurso:** API Data Lake · conjuntos de dados, lotes
**Status:** Ativo

Inspecione o conjunto de dados e os metadados em lote da camada do Data Lake. Use `get` para metadados completos, `get_size` para métricas de tamanho de armazenamento e assimilação e `list_failed` para monitorar falhas de assimilação em uma janela de tempo. O padrão é os últimos 7 dias quando nenhum intervalo de tempo é fornecido para `list_failed`. Todas as operações são somente leitura e exigem uma ID de recurso.

**Recursos:** obtenha metadados de conjunto de dados/lote, obtenha métricas de tamanho de armazenamento, liste lotes com falha em uma janela de tempo

**Parâmetros:**

| Parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| `entity_type` | Sim | `dataset` ou `batch` |
| `operation` | Sim | `get`, `get_size`, `list_failed`. `list_failed` dá suporte apenas ao tipo de entidade `batch` |
| `resource_id` | Sim | ID do conjunto de dados ou ID do lote. Para `list_failed`: a ID do conjunto de dados para analisar falhas para |
| `query_params.created_after` | Não | Janela de início de hora. Carimbo de data e hora Unix em ms |
| `query_params.created_before` | Não | Fim da janela de tempo. Carimbo de data e hora Unix em ms |
| `query_params.limit` | Não | Máximo de resultados por página (máx. 100) |
| `query_params.order_by` | Não | Direção de classificação, ex.: `desc:created` |

### search_dule

**Recurso:** Governança de dados · rótulos, políticas, ações_de_marketing
**Status:** Ativo

Consulte a API de serviço de política para obter os rótulos de uso de dados, as políticas e as ações de marketing. Use `marketing_action/evaluate` para testar se uma ação de marketing em dados com rótulos específicos violaria quaisquer políticas de governança. Todas as operações são somente leitura.

**Recursos:** listar/obter rótulos de uso de dados, listar/obter políticas, listar políticas habilitadas, listar/obter ações de marketing, avaliar a ação de marketing em relação aos rótulos

**Parâmetros:**

| Parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| `entity_type` | Sim | `label`, `policy` ou `marketing_action` |
| `operation` | Sim | `list`, `get`, `list_enabled` (somente política), `evaluate` (somente marketing_action). `list_enabled` não requer escopo |
| `scope` | Não | `core` (definido pela Adobe) ou `custom` (definido pela organização). Necessário para `list`, `get`, `evaluate`; não usado para `list_enabled` |
| `resource_id` | Não | Nome do rótulo, ID da política ou nome da ação de marketing. Necessário para `get` e `evaluate` |
| `query_params.dule_labels` | Não | Rótulos separados por vírgulas (ex.: `C1,C3`). Necessário para `marketing_action/evaluate`; filtro opcional para `policy/list` |
| `query_params.limit` | Não | Máximo de resultados |
| `query_params.start` | Não | Cursor de paginação do valor `_page.next` de uma resposta anterior |
| `query_params.orderby` | Não | Campos de classificação separados por vírgulas |
| `query_params.property_filter` | Não | Expressão de filtro, ex.: `name==C1` |
| `query_params.marketing_action` | Não | Restringir a lista de políticas a políticas que fazem referência a esta ação de marketing (somente política/lista) |
| `query_params.include_draft` | Não | Incluir políticas RASCUNHO em `marketing_action/evaluate` (padrão: somente políticas HABILITADAS) |

### search_query_service

**Recurso:** Serviço de Consulta · consultas, modelos, agendamentos, execuções de agendamento, conexões, assinaturas de alerta
**Status:** Ativo

Ferramenta unificada para recursos do Serviço de consulta. Liste e recupere consultas ad-hoc, modelos SQL salvos, consultas programadas e suas execuções, parâmetros de conexão interativa (para clientes psql/JDBC) e assinaturas de alerta. Para listas de consulta, o padrão é `isService==false,isParentLevel==true` para filtrar o tráfego interno. Todas as operações são somente leitura.

**Recursos:** consultas list/get, modelos list/get, agendamentos list/get, execuções de agendamento list/get, obter parâmetros de conexão, listar assinaturas de alerta

**Parâmetros:**

| Parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| `entity_type` | Sim | `query`, `query_template`, `schedule`, `schedule_run`, `connection`, `alert_subscription` |
| `operation` | Sim | `list`, `get`, `get_connection_params`, `list_by_u...` |
