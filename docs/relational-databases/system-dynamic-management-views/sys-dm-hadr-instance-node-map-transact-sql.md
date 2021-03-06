---
title: sys. dm_hadr_instance_node_map (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.sys.dm_hadr_instance_node_map_TSQL
- sys.sys.dm_hadr_instance_node_map
- sys.dm_hadr_instance_node_map_TSQL
- sys.dm_hadr_instance_node_map
dev_langs:
- TSQL
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- Availability Groups [SQL Server], WSFC
- sys.sys.dm_hadr_instance_node_map dynamic management view
ms.assetid: ccfaf62c-9f87-43cf-a5e7-8942e91dd041
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 32001d88c17358406b5b855cbb698c9d2686e40f
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85760251"
---
# <a name="sysdm_hadr_instance_node_map-transact-sql"></a>sys.dm_hadr_instance_node_map (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Para cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda uma réplica de disponibilidade que é unida ao seu grupo de disponibilidade Always on, retorna o nome do nó do WSFC (cluster de failover do Windows Server) que hospeda a instância do servidor. Esta exibição de gerenciamento dinâmico tem os seguintes usos:  
  
-   Esta exibição de gerenciamento dinâmico será útil para detectar um grupo de disponibilidade com várias réplicas de disponibilidade que são hospedadas no mesmo nó do WSFC, que é uma configuração sem suporte que poderá ocorrer depois de um failover de FCI se o grupo de disponibilidade estiver configurado incorretamente. Para obter mais informações, veja [Clustering de failover e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/failover-clustering-and-always-on-availability-groups-sql-server.md).  
  
-   Quando várias instâncias do SQL Server são hospedadas no mesmo nó do WSFC, a DLL de Recurso usa esta exibição de gerenciamento dinâmico para determinar a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à qual se conectar.  
   
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**ag_resource_id**|**nvarchar(256)**|ID exclusiva do grupo de disponibilidade como um recurso no WSFC.|  
|**instance_name**|**nvarchar(256)**|Nome-*server* / *instância*do servidor-de uma instância de servidor que hospeda uma réplica para o grupo de disponibilidade.|  
|**node_name**|**nvarchar(256)**|Nome do nó WSFC.|  
  
## <a name="permissions"></a>Permissões  
 , é necessário ter permissão VIEW SERVER STATE no servidor.  
  
## <a name="see-also"></a>Consulte Também  
 [Always On funções e exibições de gerenciamento dinâmico de grupos de disponibilidade &#40;&#41;de Transact-SQL](../../relational-databases/system-dynamic-management-views/always-on-availability-groups-dynamic-management-views-functions.md)   
 [Always On exibições de catálogo de grupos de disponibilidade &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/always-on-availability-groups-catalog-views-transact-sql.md)   
 [Monitorar grupos de disponibilidade &#40;&#41;Transact-SQL](../../database-engine/availability-groups/windows/monitor-availability-groups-transact-sql.md)   
 [Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
