---
title: Privacidade, segurança e governança no Assistente de IA
description: Saiba mais sobre as práticas de privacidade, segurança e governança do Assistente de IA.
source-git-commit: c9909616697ef319a307b5c8a1ee135204347844
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Privacidade, segurança e governança no Assistente de IA

O Assistente de IA no Adobe Experience Platform é criado com privacidade, segurança e governança na vanguarda.

Leia este documento para saber mais sobre os recursos focados na confiança do cliente que você pode esperar do Assistente de IA:

* Nenhum dado pessoal está sendo usado pelo Assistente de IA hoje, mesmo para fins de treinamento.
* O Assistente de IA não tem conhecimento dos dados do consumidor.
* Todas as políticas existentes de [controle de acesso](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home) serão atendidas pelo Assistente de IA.

   * Quaisquer novas políticas de controle de acesso baseadas em atributos serão refletidas no Assistente de IA após um máximo de 24 horas&amp;ast;

* Você deve receber permissão explícita para interagir com o Assistente de IA.

   * Você pode definir permissões de forma diferente para o Experience Platform e o Journey Optimizer usando a [Interface do usuário de permissões](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/browse) e pode usar o [Admin Console](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/browse) para atribuir permissões para o Customer Journey Analytics.
   * As permissões são granulares e o administrador da sandbox pode configurar quais dos seus usuários podem fazer diferentes categorias de perguntas (perguntas baseadas em conhecimento do produto com o Assistente de IA ou perguntas sobre insights operacionais).

* O AI Assistant é um recurso pronto para HIPAA quando usado em combinação com o Adobe Experience Platform Healthcare Shield.
* Você pode exibir um log de suas interações anteriores com o AI Assistant com uma política de retenção de 30 dias.
* O Assistente de IA é baseado em dados específicos da sandbox e na documentação pública do Adobe ao responder aos prompts do usuário. Os dados não são compartilhados em sandboxes.
* Os prompts fornecidos ao Assistente de IA não são compartilhados com outros clientes.

&amp;ast; *Isso implica que se quaisquer novos rótulos forem adicionados aos campos e objetos ou qualquer nova política for criada, o AI Assistant levará até 24 horas para honrá-los. Durante essas 24 horas, os usuários com acesso recém-restrito ainda poderão acessar esses campos e objetos.*

