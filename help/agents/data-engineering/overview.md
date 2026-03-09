---
title: Data Engineering Agent
description: Saiba como usar o Data Engineering Agent.
hide: true
hidefromtoc: true
source-git-commit: 12c61f88b358fc8c357ec4fa373493d6b70d5a06
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Data Engineering Agent

&lt;!— ESTE É UM RASCUNHO —>

O Data Engineering Agent é um copiloto baseado em IA e com recursos da Agent Orchestrator para equipes de dados na Adobe Experience Platform. O agente foi projetado para lidar com o trabalho pesado no ciclo de vida completo dos dados: modelagem de dados, integração, preparação de dados SQL, governança e gerenciamento do ciclo de vida. Com a Data Engineering Agent, engenheiros e arquitetos podem se mover mais rápido com maior qualidade de dados e menos trabalho manual.

O Data Engineering Agent está organizado em habilidades que você pode aproveitar para otimizar seus fluxos de trabalho.

| Habilidade do Data Engineering Agent | Descrição |
| --- | --- |
| Integração de dados | <strong>A integração de dados</strong> oferece suporte a fontes em lote, como S3, Marketo e DLZ (Data Landing Zone). Seus recursos incluem: <ul><li>Conexão com várias fontes de dados, incluindo S3, Data Landing Zone, Marketo e muito mais.</li><li>Definindo o perfil dos dados de origem (por exemplo, valores distintos, nulos, duplicados e métricas de qualidade básicas).</li><li>Alinhamento de campos de origem a grupos de campos XDM padrão e campos personalizados.</li><li>Propor e criar fluxos de dados de assimilação de dados (por exemplo, mover dados do S3 ou do Marketo para conjuntos de dados do RTCDP/CJA).</li></ul> |
| Qualidade automatizada dos dados e enriquecimento semântico | <ul><li>Executa avaliações abrangentes da qualidade dos dados, incluindo a identificação de anomalias e a geração de relatórios de contagens de registros válidas/inválidas.</li><li>Recomenda melhorias na qualidade dos dados, como normalização de tipo, formatação de moeda e desduplicação de ID.</li><li>Aplica enriquecimento semântico a esquemas com base na amostragem de dados e no reconhecimento inteligente do padrão de nomenclatura.</li><li>Envolve os usuários para confirmação sobre os enriquecimentos sugeridos, garantindo alterações finalizadas e aprovadas nos dados.</li></ul> |
| Destilador de dados | |
| Coleta de dados | |
| Validação de dados | |

Com o Data Engineering Agent, você pode garantir:

- **Integração mais rápida**: reduza o tempo de semanas de mapeamento manual de esquemas e configuração de pipeline para horas de configuração guiada e conversacional.
- **Qualidade de dados mais alta**: menos registros inválidos e incidentes de produção devido à análise de qualidade de dados interna e verificações semânticas.
- **Governança e conformidade aprimoradas**: as políticas de governança são anexadas em tempo de design (rótulos, TTL, manipulação de identidade) em vez de como um pensamento posterior.
- **Equipes de dados mais produtivas**: o trabalho de SQL/fluxo de dados repetitivo é automatizado para que os engenheiros se concentrem em projetos e otimização de maior valor.
- **Autoatendimento mais amplo**: as partes interessadas não especializadas podem realizar com segurança o autoatendimento de tarefas comuns de preparação de dados com medidas de proteção.