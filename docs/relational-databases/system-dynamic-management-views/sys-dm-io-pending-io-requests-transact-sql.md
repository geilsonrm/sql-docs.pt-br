---
title: sys. dm_io_pending_io_requests (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_io_pending_io_requests
- dm_io_pending_io_requests
- dm_io_pending_io_requests_TSQL
- sys.dm_io_pending_io_requests_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_io_pending_io_requests dynamic management view
ms.assetid: d1fb46dd-5c74-4c04-9ecf-8934b1bedb5b
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 4d189ba90bb8597f2c23b143528cba1c8b225709
ms.sourcegitcommit: df1f0f2dfb9452f16471e740273cd1478ff3100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87396318"
---
# <a name="sysdm_io_pending_io_requests-transact-sql"></a>sys.dm_io_pending_io_requests (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Retorna uma linha para cada solicitação de E/S pendente no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!NOTE]  
>  Para chamá-lo de [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)] , use o nome **Sys. dm_pdw_nodes_io_pending_io_requests**.  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**io_completion_request_address**|**varbinary (8)**|Endereço de memória da solicitação de E/S. Não permite valor nulo.|  
|**io_type**|**nvarchar(60)**|Tipo de solicitação de E/S pendente. Não permite valor nulo.|  
|**io_pending_ms_ticks**|**bigint**|Apenas para uso interno. Não permite valor nulo.| 
|**io_pending**|**int**|Indica se a solicitação de E/S está pendente ou foi concluída pelo Windows. Uma solicitação de E/S ainda pode ficar pendente mesmo que o Windows a conclua, caso o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não execute uma opção de contexto que processe a solicitação de E/S e a remova da lista. Não permite valor nulo.|  
|**io_completion_routine_address**|**varbinary (8)**|Função interna a ser chamada quando a solicitação de E/S é concluída. Permite valor nulo.|  
|**io_user_data_address**|**varbinary (8)**|Apenas para uso interno. Permite valor nulo.|  
|**scheduler_address**|**varbinary (8)**|Agendador no qual esta solicitação de E/S foi emitida. A solicitação de E/S será exibida na lista de E/S pendente do agendador. Para obter mais informações, consulte [Sys. dm_os_schedulers &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-schedulers-transact-sql.md). Não permite valor nulo.|  
|**io_handle**|**varbinary (8)**|Identificador de arquivo do arquivo usado na solicitação de E/S. Permite valor nulo.|  
|**io_offset**|**bigint**|Deslocamento da solicitação de E/S. Não permite valor nulo.|  
|**io_handle_path**|**nvarchar(256)**| Caminho do arquivo usado na solicitação de e/s. Permite valor nulo.|
|**pdw_node_id**|**int**|**Aplica-se a**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ,[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> O identificador do nó em que essa distribuição está.|  
  
## <a name="permissions"></a>Permissões  

Ativado [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] , requer `VIEW SERVER STATE` permissão.   
Nas [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] camadas Premium, o requer a `VIEW DATABASE STATE` permissão no banco de dados. Nas [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] camadas Standard e Basic, o requer o **administrador do servidor** ou uma conta de **administrador do Azure Active Directory** .   
  
## <a name="see-also"></a>Consulte Também  
 [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [E/s relacionadas a exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/i-o-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  


