---
title: sp_replmonitorhelpmergesession (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_replmonitorhelpmergesession_TSQL
- sp_replmonitorhelpmergesession
helpviewer_keywords:
- sp_replmonitorhelpmergesession
ms.assetid: a0400ba8-9609-4901-917e-925e119103a1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 305b7a0e2c9d83fe33a6d571198b205f7452ba44
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85725691"
---
# <a name="sp_replmonitorhelpmergesession-transact-sql"></a>sp_replmonitorhelpmergesession (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Retorna informações de sessões anteriores para um determinado Merge Agent de replicação, com uma linha retornada para cada sessão correspondente aos critérios de filtragem. Esse procedimento armazenado, usado para monitorar replicação de mesclagem, é executado no Distribuidor, no banco de dados de distribuição, e no Assinante, no banco de dados de assinatura.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_replmonitorhelpmergesession [ [ @agent_name = ] 'agent_name' ]  
    [ , [ @hours = ] hours ]  
    [ , [ @session_type = ] session_type ]  
    [ , [ @publisher = ] 'publisher' ]  
    [ , [ @publisher_db = ] 'publisher_db' ]  
    [ , [ @publication = ] 'publication' ]   
```  
  
## <a name="arguments"></a>Argumentos  
`[ @agent_name = ] 'agent_name'`É o nome do agente. *agent_name* é **nvarchar (100)** sem padrão.  
  
`[ @hours = ] hours`É o intervalo de tempo, em horas, para o qual as informações de sessão histórica do agente são retornadas. *horas* é **int**, que pode ser um dos intervalos a seguir.  
  
|Valor|Description|  
|-----------|-----------------|  
|< **0**|Retorna informações sobre execuções de agente anteriores, até um máximo de 100 execuções.|  
|**0** (padrão)|Retorna informações sobre todas as execuções de agente anteriores.|  
|> **0**|Retorna informações sobre execuções do agente que ocorreram nas últimas *horas* do número de horas.|  
  
`[ @session_type = ] session_type`Filtra o conjunto de resultados com base no resultado final da sessão. *session_type* é **int**e pode ser um desses valores.  
  
|Valor|Description|  
|-----------|-----------------|  
|**1** (padrão)|Sessões de agente com um resultado de repetição ou êxito.|  
|**0**|Sessões de agente com um resultado de falha.|  
  
`[ @publisher = ] 'publisher'`É o nome do Publicador. o *Publicador* é **sysname**, com um padrão de NULL. Esse parâmetro é usado ao executar **sp_replmonitorhelpmergesession** no Assinante.  
  
`[ @publisher_db = ] 'publisher_db'`É o nome do banco de dados de publicação. *publisher_db* é **sysname**, com um padrão de NULL. Esse parâmetro é usado ao executar **sp_replmonitorhelpmergesession** no Assinante.  
  
`[ @publication = ] 'publication'`É o nome da publicação. a *publicação* é **sysname**, com um padrão de NULL. Esse parâmetro é usado ao executar **sp_replmonitorhelpmergesession** no Assinante.  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**Session_id**|**int**|ID da sessão de trabalho do agente.|  
|**Status**|**int**|Status de execução do agente:<br /><br /> **1** = iniciar<br /><br /> **2** = com sucesso<br /><br /> **3** = em andamento<br /><br /> **4** = ocioso<br /><br /> **5** = repetir<br /><br /> **6** = falha|  
|**StartTime**|**datetime**|Iniciada sessão de trabalho do agente de tempo.|  
|**EndTime**|**datetime**|A sessão de trabalho do agente de tempo foi concluída.|  
|**Duration**|**int**|Duração acumulada, em segundos, dessa sessão de trabalho.|  
|**UploadedCommands**|**int**|Número de comandos carrgeado durante a sessão do agente.|  
|**DownloadedCommands**|**int**|Número de comandos baixados durante a sessão do agente.|  
|**ErrorMessages**|**int**|Número de mensagens de erro geradas durante a sessão do agente.|  
|**ErrorID**|**int**|ID do erro ocorrido.|  
|**PercentageDone**|**decimal**|Porcentagem estimada do total de alterações que já foi entregue em uma sessão ativa.|  
|**TimeRemaining**|**int**|Número estimado de segundos restantes em uma sessão ativa.|  
|**CurrentPhase**|**int**|É a fase atual da sessão de uma sessão ativa, que pode ser uma das seguintes:<br /><br /> **1** = carregar<br /><br /> **2** = baixar|  
|**LastMessage**|**nvarchar (500)**|É a última mensagem registrada pelo Merge Agent durante a sessão.|  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Comentários  
 **sp_replmonitorhelpmergesession** é usado para monitorar a replicação de mesclagem.  
  
 Quando executado no Assinante, **sp_replmonitorhelpmergesession** retorna apenas informações nas últimas cinco sessões de agente de mesclagem.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros da função de banco de dados fixa **db_owner** ou **replmonitor** no banco de dados de distribuição no distribuidor ou no banco de dados de assinatura no assinante podem executar **sp_replmonitorhelpmergesession**.  
  
## <a name="see-also"></a>Consulte Também  
 [Monitorar a replicação de forma programática](../../relational-databases/replication/monitor/programmatically-monitor-replication.md)  
  
  
