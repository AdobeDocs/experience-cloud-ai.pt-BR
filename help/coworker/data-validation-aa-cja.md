---
title: Validar dados com o Colaborador ao atualizar do Adobe Analytics para o Customer Journey Analytics
description: Saiba como os administradores do Analytics usam o recurso de validação de dados do CX Enterprise Co-worker para comparar os dados do Adobe Analytics e do Customer Journey Analytics durante a migração.
hold: true
source-git-commit: 850bfef76e3c3e081f9860b9757e5e5128383f76
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Validar dados com o Colaborador ao atualizar do Adobe Analytics para o Customer Journey Analytics

O CX Enterprise Co-worker inclui uma habilidade de validação que permite validar os dados ao atualizar do Adobe Analytics para o Customer Journey Analytics. A validação de dados é concluída em uma única conversa.

Essa habilidade compara automaticamente:

* Cada dimensão, métrica e tendência individualmente em implementações.

* Todos os conjuntos de relatórios do Adobe Analytics em relação a todas as visualizações de dados do Customer Journey Analytics.

Depois de fazer essas comparações, a habilidade gera insights e recomendações orientados por IA que você pode implementar para facilitar a atualização para o Customer Journey Analytics.

## Antes de começar

Para validar dados como parte da atualização, é necessário:

* O conjunto de relatórios do Adobe Analytics que você deseja validar.

* A visualização de dados do Customer Journey Analytics que contém os mesmos dados.

Você não precisa saber com antecedência como sua implementação foi projetada. A habilidade detecta automaticamente se os dados são mapeados por meio de um conector de origem do Analytics ou por meio de duas implementações lado a lado, de modo que você não precisa fornecer esse contexto sozinho.

## Iniciar uma sessão de validação

1. Faça logon no CX Enterprise Co-worker.

1. Selecione [!UICONTROL **Novo Chat**].

1. No campo de texto, solicite que o agente valide a migração do Adobe Analytics para o Customer Journey Analytics:

   **Aviso**

   > Ajude-me a validar a atualização de minha empresa do Adobe Analytics para o Customer Journey Analytics.

   Sua solicitação é roteada para a habilidade de validação de dados, que inicia um processo de configuração interativo.

1. O processo de configuração inclui as perguntas da tabela abaixo. Para cada pergunta, selecione uma resposta e, em seguida, [!UICONTROL **Enviar**].

   | Pergunta | Contexto adicional |
   |---------|----------|
   | [!UICONTROL **Selecione sua empresa do Analytics**] | Esta é a sua empresa de logon na Adobe Analytics. |
   | [!UICONTROL **Selecione seu conjunto de relatórios**] <!--In the UI, recommend change to "Select your Adobe Analytics report suite"--> | Esse é o conjunto de relatórios no Adobe Analytics que contém os dados que você deseja validar em relação aos dados do Customer Journey Analytics. |
   | [!UICONTROL **Selecione sua visualização de dados do Customer Journey Analytics**] | Essa é a visualização de dados no Customer Journey Analytics que contém os mesmos dados que o conjunto de relatórios do Adobe Analytics selecionado. |

1. Revise o resumo da configuração para confirmar se você está validando os dados corretos antes de continuar. O resumo inclui a empresa, o conjunto de relatórios e a visualização de dados selecionados, juntamente com uma visualização das métricas e dimensões principais de cada sistema.

1. Continue com a seguinte seção, [Escolha os dados a serem validados](#choose-the-data-to-validate).

## Escolher os dados para validar

É possível validar métricas ou dimensões individuais, ou validar todas as métricas e dimensões incluídas no conjunto de relatórios e na visualização de dados.

1. Selecione entre as seguintes opções:

   | Opção de validação | Descrição |
   |---------|----------|
   | [!UICONTROL **Comparação de métrica única**] | Comparar a tendência de uma métrica entre o Adobe Analytics e o Customer Journey Analytics. Use-a quando quiser verificar rapidamente uma métrica específica, como exibições de página ou visitas. |
   | [!UICONTROL **Comparação de dimensões únicas**] | Compare o detalhamento de uma única dimensão entre o Adobe Analytics e o Customer Journey Analytics. Use isso quando suspeitar de uma diferença de mapeamento ou classificação para uma dimensão específica. |
   | [!UICONTROL **Auditoria completa do conjunto de relatórios e da visualização de dados**] | Comparar até 20 métricas e dimensões em uma única execução. Use-a quando quiser ter uma visão abrangente da integridade geral da migração. |

1. Continue com a seguinte seção, [Revise a análise](#review-the-analysis).

## Revisar a análise

1. Selecione cada uma das guias a seguir para revisar a análise:

   | Guia Revisão de análise | Descrição |
   |---------|----------|
   | [!UICONTROL **Taxa de correspondência geral**] | Uma porcentagem que indica com que proximidade os dados do conjunto de relatórios do Adobe Analytics correspondem aos da visualização de dados do Customer Journey Analytics. |
   | [!UICONTROL **Principais insights**] | Principais insights descobertos durante a análise. |
   | [!UICONTROL **Resumo**] | Totais de Adobe Analytics, totais de Customer Journey Analytics, variação total, dias de aprovação e dias críticos. <!--what are these?--> |
   | [!UICONTROL **Tendência diária**] | Gráfico que mostra uma comparação lado a lado dos dados do Adobe Analytics e do Customer Journey Analytics. |
   | [!UICONTROL **Detalhes diários**] | <!--what goes here?--> |

1. Role para baixo na análise para visualizar padrões adicionais que foram descobertos durante a análise, causas prováveis para esses padrões e ações sugeridas que você pode tomar para resolver qualquer discrepância de dados.

1. Verifique se as ações sugeridas são válidas e resolva-as no Adobe Experience Platform ou no Adobe Analytics.

1. (Opcional) Continue sua análise analisando outra métrica, analisando outra dimensão ou executando outro relatório com até 20 métricas e dimensões, conforme descrito em [Escolha os dados que serão validados](#choose-the-data-to-validate).

