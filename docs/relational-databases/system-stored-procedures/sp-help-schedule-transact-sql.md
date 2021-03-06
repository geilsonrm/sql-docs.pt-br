---
title: sp_help_schedule (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_help_schedule
- sp_help_schedule_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_schedule
ms.assetid: b2fc4ce1-0a8e-44d2-b206-7dc7b258d8c9
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5f0539e4281d58744b18a4f9ca522c52952032c0
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85893594"
---
# <a name="sp_help_schedule-transact-sql"></a>sp_help_schedule (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Lista informações sobre agendas.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_help_schedule   
     [ @schedule_id = ] id ,  
     [ @schedule_name = ] 'schedule_name'   
     [ , [ @attached_schedules_only = ] attached_schedules_only ]  
     [ , [ @include_description = ] include_description ]  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @schedule_id = ] id`O identificador da agenda a ser listada. *schedule_name* é **int**, sem padrão. *Schedule_id* ou *schedule_name* pode ser especificado.  
  
`[ @schedule_name = ] 'schedule_name'`O nome da agenda a ser listada. *schedule_name* é **sysname**, sem padrão. *Schedule_id* ou *schedule_name* pode ser especificado.  
  
`[ @attached_schedules_only = ] attached_schedules_only ]`Especifica se é para mostrar apenas os agendamentos aos quais um trabalho está anexado. *attached_schedules_only* é **bit**, com um padrão de **0**. Quando *attached_schedules_only* é **0**, todas as agendas são mostradas. Quando *attached_schedules_only* é **1**, o conjunto de resultados contém apenas os agendamentos anexados a um trabalho.  
  
`[ @include_description = ] include_description`Especifica se as descrições devem ser incluídas no conjunto de resultados. *include_description* é **bit**, com um padrão de **0**. Quando *include_description* é **0**, a coluna *schedule_description* do conjunto de resultados contém um espaço reservado. Quando *include_description* é **1**, a descrição da agenda é incluída no conjunto de resultados.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Este procedimento retorna o seguinte conjunto de resultados:  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**schedule_id**|**int**|Número do identificador de agenda.|  
|**schedule_uid**|**uniqueidentifier**|Identificador da agenda.|  
|**schedule_name**|**sysname**|Nome da agenda.|  
|**habilitado**|**int**|Se a agenda está habilitada (**1**) ou não habilitada (**0**).|  
|**freq_type**|**int**|Valor que indica quando o trabalho deve ser executado.<br /><br /> **1** = uma vez<br /><br /> **4** = diariamente<br /><br /> **8** = semanalmente<br /><br /> **16** = mensalmente<br /><br /> **32** = mensalmente, em relação ao **freq_interval**<br /><br /> **64** = executar quando o serviço SQLServerAgent for iniciado.|  
|**freq_interval**|**int**|Dias em que o trabalho é executado. O valor depende do valor de **freq_type**. Para obter mais informações, consulte [sp_add_schedule &#40;&#41;Transact-SQL ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_subday_type**|**int**|Unidades para **freq_subday_interval**. Para obter mais informações, consulte [sp_add_schedule &#40;&#41;Transact-SQL ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_subday_interval**|**int**|Número de períodos de **freq_subday_type** a ocorrer entre cada execução do trabalho. Para obter mais informações, consulte [sp_add_schedule &#40;&#41;Transact-SQL ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_relative_interval**|**int**|A ocorrência do trabalho agendado do **freq_interval** em cada mês. Para obter mais informações, consulte [sp_add_schedule &#40;&#41;Transact-SQL ](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md).|  
|**freq_recurrence_factor**|**int**|Número de meses entre a execução agendada do trabalho.|  
|**active_start_date**|**int**|Data em que a agenda foi ativada.|  
|**active_end_date**|**int**|Data de término da agenda.|  
|**active_start_time**|**int**|Hora do dia em que a agenda é iniciada.|  
|**active_end_time**|**int**|Hora do dia em que a agenda é encerrada.|  
|**date_created**|**datetime**|Data em que a agenda foi criada.|  
|**schedule_description**|**nvarchar(4000)**|Uma descrição em inglês da agenda (se solicitado).|  
|**job_count**|**int**|Retorna o número de trabalhos que referenciam essa agenda.|  
  
## <a name="remarks"></a>Comentários  
 Quando nenhum parâmetro é fornecido, **sp_help_schedule** lista informações para todos os agendamentos na instância.  
  
## <a name="permissions"></a>Permissões  
 Por padrão, os membros da função de servidor fixa **sysadmin** podem executar este procedimento armazenado. Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 Para obter detalhes sobre as permissões dessas funções, consulte [Funções de banco de dados fixas do SQL Server Agent](../../ssms/agent/sql-server-agent-fixed-database-roles.md).  
  
 Os membros de **SQLAgentUserRole** só podem exibir as agendas que possuem.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-listing-information-for-all-schedules-in-the-instance"></a>a. Listando informações para todas as agendas da instância  
 O exemplo a seguir lista as informações para todas as agendas na instância.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_schedule ;  
GO  
```  
  
### <a name="b-listing-information-for-a-specific-schedule"></a>B. Listando informações de uma agenda específica  
 O exemplo a seguir lista as informações para a agenda chamada `NightlyJobs`.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_schedule  
    @schedule_name = N'NightlyJobs' ;  
GO  
```  
  
## <a name="see-also"></a>Consulte Também  
 [&#41;&#40;Transact-SQL de sp_add_schedule](../../relational-databases/system-stored-procedures/sp-add-schedule-transact-sql.md)   
 [&#41;&#40;Transact-SQL de sp_attach_schedule](../../relational-databases/system-stored-procedures/sp-attach-schedule-transact-sql.md)   
 [&#41;&#40;Transact-SQL de sp_delete_schedule](../../relational-databases/system-stored-procedures/sp-delete-schedule-transact-sql.md)   
 [&#41;&#40;Transact-SQL de sp_detach_schedule](../../relational-databases/system-stored-procedures/sp-detach-schedule-transact-sql.md)  
  
  
