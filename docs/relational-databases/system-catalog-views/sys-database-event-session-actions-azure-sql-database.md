---
title: sys. database_event_session_actions (banco de dados SQL do Azure) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
ms.assetid: 32494df1-7ab7-4b88-a858-6b1021d67433
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: d2171403f78fe3de84223e24ef189fd08c53fd88
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86920704"
---
# <a name="sysdatabase_event_session_actions-azure-sql-database"></a>sys.database_event_session_actions (Banco de Dados SQL do Azure)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Retorna uma linha para cada ação em cada evento de uma sessão de eventos.  
  
||  
|-|  
|**Aplica-se a**: [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] V12 e a todas as versões posteriores.|  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|event_session_id|**int**|A identificação da sessão de evento. Não permite valor nulo.|  
|event_id|**int**|A ID do evento. Essa ID é exclusiva de um objeto da sessão de evento. Não permite valor nulo.|  
|name|**sysname**|O nome da ação. Permite valor nulo.|  
|pacote|**sysname**|O nome do pacote de eventos que contém um evento. Permite valor nulo.|  
|module|**sysname**|O nome do módulo que contém o evento. Permite valor nulo.|  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão VIEW DATABASE STATE no servidor.  
  
## <a name="remarks"></a>Comentários  
 Essa exibição tem as cardinalidades de relação a seguir.  
  
| De | Para | Relação |
| ---- | -- | ------------ |
|sys. database_event_session_actions. event_session_id|sys.sys. database_event_sessions. event_session_id|Muitos para um|  
|sys. database_event_session_actions. event_id<br /><br /> sys. database_event_session_actions. event_session_id|sys. database_event_session_events. event_session_id<br /><br /> sys. database_event_session_events. event_id|Muitos para um|  
  
  
