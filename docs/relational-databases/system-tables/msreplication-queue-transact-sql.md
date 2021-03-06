---
title: MSreplication_queue (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSreplication_queue
- MSreplication_queue_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSreplication_queue system table
ms.assetid: 664bf817-8021-4417-96d6-2bb1e4baabff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3bdbfed403a8b85a195134e053a151905efa128f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889425"
---
# <a name="msreplication_queue-transact-sql"></a>MSreplication_queue (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  A tabela de **MSreplication_queue** é usada pelo processo de replicação para armazenar os comandos na fila emitidos por todas as assinaturas de atualização enfileiradas que estão usando a fila baseada em SQL. Essa tabela é armazenada no banco de dados de assinatura.  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**programa**|**sysname**|O nome do Publicador.|  
|**publisher_db**|**sysname**|O nome do banco de dados de publicação.|  
|**documento**|**sysname**|O nome da publicação.|  
|**transid**|**sysname**|A ID da transação na qual o comando enfileirado foi executado.|  
|**dados**|**varbinary(8000)**|O pacote de fluxo de bytes que armazenou informações sobre os comandos na fila.|  
|**datalen**|**int**|O comprimento dos dados, em bytes.|  
|**CommandType**|**int**|O tipo de comando que está sendo enfileirado:<br /><br /> 1 = Comando de usuário na transação.<br /><br /> 2 = Comando de sincronização de assinatura.|  
|**insertdate**|**datetime**|A data da inserção.|  
|**orderkey**|**bigint**|A coluna de identidade que aumenta de forma monotônica.|  
|**cmdstate**|**bit**|O estado do comando:<br /><br /> 0 = Completo.<br /><br /> 1 = Parcial.|  
  
## <a name="see-also"></a>Consulte Também  
 [Tabelas de replicação &#40;&#41;Transact-SQL](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Exibições de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
