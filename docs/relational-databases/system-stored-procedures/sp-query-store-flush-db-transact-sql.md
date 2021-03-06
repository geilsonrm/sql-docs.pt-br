---
title: sp_query_store_flush_db (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/24/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_query_store_flush_db_TSQL
- sys.sp_query_store_flush_db_TSQL
- sp_query_store_flush_db
- sys.sp_query_store_flush_db
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_query_store_flush_db
- sp_query_store_flush_db
ms.assetid: 580c03ae-57fc-4562-a6bb-5ec89521e38c
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 229a954f4665550e30c017fed59d71ac1ff3a0b6
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "86012653"
---
# <a name="sp_query_store_flush_db-transact-sql"></a>sp_query_store_flush_db (Transact-SQL)
[!INCLUDE [sqlserver2016-asdb-asdbmi-asa](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi-asa.md)]

  Libera a parte na memória do Repositório de Consultas dados para o disco.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_query_store_flush_db [;]  
```  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou 1 (falha)  
  
## <a name="remarks"></a>Comentários  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão **ALTER** no banco de dados.
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir libera a parte na memória do Repositório de Consultas dados para o disco.  
  
```  
EXEC sp_query_store_flush_db;  
```  
  
## <a name="see-also"></a>Consulte Também  
 [&#41;&#40;Transact-SQL de sp_query_store_force_plan](../../relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql.md)   
 [&#41;&#40;Transact-SQL de sp_query_store_remove_query](../../relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql.md)   
 [&#41;&#40;Transact-SQL de sp_query_store_unforce_plan](../../relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql.md)   
 [&#41;&#40;Transact-SQL de sp_query_store_reset_exec_stats](../../relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql.md)   
 [sp_query_store_remove_plan &#40;Transct-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql.md)   
 [&#41;&#40;Transact-SQL de sp_query_store_reset_exec_stats](../../relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql.md)   
 [Repositório de Consultas exibições de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/query-store-catalog-views-transact-sql.md)   
 [Monitorando o desempenho com o repositório de consultas](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md)  
  
  
