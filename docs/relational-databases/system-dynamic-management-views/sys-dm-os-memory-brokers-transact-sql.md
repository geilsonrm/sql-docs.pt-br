---
title: sys. dm_os_memory_brokers (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 08/18/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_os_memory_brokers
- dm_os_memory_brokers_TSQL
- sys.dm_os_memory_brokers_TSQL
- dm_os_memory_brokers
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_memory_brokers dynamic management view
ms.assetid: 48dd6ad9-0d36-4370-8a12-4921d0df4b86
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f6d59886a480f38ce9e734e8dae7baa7604922c8
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85898752"
---
# <a name="sysdm_os_memory_brokers-transact-sql"></a>sys.dm_os_memory_brokers (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  As alocações internas ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usam o gerenciador de memória do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Acompanhar a diferença entre contadores de memória de processo de **Sys. dm_os_process_memory** e contadores internos pode indicar o uso de memória de componentes externos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espaço de memória.  
  
 Os agentes de memória distribuem alocações de memória razoavelmente entre vários componentes no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], com base no uso projetado e atual. Eles não executam alocações. Só controlam alocações para computar a distribuição.  
  
 A tabela a seguir fornece informações sobre agentes de memória.  
  
> [!NOTE]  
>  Para chamá-lo de [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] , use o nome **Sys. dm_pdw_nodes_os_memory_brokers**.  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**pool_id**|**int**|ID do pool de recursos caso seja associado a um pool do Administrador de recursos.|  
|**memory_broker_type**|**nvarchar(60)**|Tipo de agente de memória. Atualmente, há três tipos de agentes de memória no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , listados abaixo com suas descrições.<br /><br /> **MEMORYBROKER_FOR_CACHE** : memória que é alocada para uso por objetos armazenados em cache (não cache do pool de buffers).<br /><br /> **MEMORYBROKER_FOR_STEAL** : memória roubada do pool de buffers. Essa memória não estará disponível para reutilização por outros componentes até ser liberada pelo proprietário atual.<br /><br /> **MEMORYBROKER_FOR_RESERVE** : memória reservada para uso futuro por solicitações atualmente em execução.|  
|**allocations_kb**|**bigint**|Quantidade de memória, em quilobytes (KB), alocada a este tipo de agente.|  
|**allocations_kb_per_sec**|**bigint**|Taxa de alocações de memória em quilobytes (KB) por segundo. Esse valor pode ser negativo para desalocações de memória.|  
|**predicted_allocations_kb**|**bigint**|Quantidade prevista de memória alocada pelo agente. Tem como base o padrão de uso da memória.|  
|**target_allocations_kb**|**bigint**|Quantidade recomendada de memória alocada, em quilobytes (KB), com base nas configurações atuais e no padrão de uso da memória. Esse agente deve aumentar ou diminuir em relação a esse número.|  
|**future_allocations_kb**|**bigint**|Número projetado de alocações, em quilobytes (KB), que serão feitas nos próximos segundos.|  
|**overall_limit_kb**|**bigint**|Quantidade máxima de memória, em kilobytes (KB), que o agente pode alocar.|  
|**last_notification**|**nvarchar(60)**|Recomendação de uso de memória com base nas configurações atuais e no padrão de uso. Estes são os valores válidos:<br /><br /> grow<br /><br /> shrink<br /><br /> estável|  
|**pdw_node_id**|**int**|**Aplica-se a**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ,[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> O identificador do nó em que essa distribuição está.|  
  
## <a name="permissions"></a>Permissões  

Ativado [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] , requer `VIEW SERVER STATE` permissão.   
Nas [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] camadas Premium, o requer a `VIEW DATABASE STATE` permissão no banco de dados. Nas [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] camadas Standard e Basic, o requer o **administrador do servidor** ou uma conta de **administrador do Azure Active Directory** .   
  
## <a name="see-also"></a>Consulte Também  

  [SQL Server exibições de gerenciamento dinâmico relacionadas ao sistema operacional &#40;&#41;Transact-SQL](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  


