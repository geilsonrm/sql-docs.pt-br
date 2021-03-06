---
title: DM db_objects_impacted_on_version_change
titleSuffix: Azure SQL Database
ms.date: 03/03/2017
ms.service: sql-database
ms.reviewer: ''
ms.topic: language-reference
f1_keywords:
- sys.dm_db_objects_impacted_on_version_change_TSQL
- dm_db_objects_impacted_on_version_change
- dm_db_objects_impacted_on_version_change_TSQL
- sys.dm_db_objects_impacted_on_version_change
dev_langs:
- TSQL
helpviewer_keywords:
- dm_db_objects_impacted_on_version_change
- sys.dm_db_objects_impacted_on_version_change
ms.assetid: b94af834-c4f6-4a27-80a6-e8e71fa8793a
author: CarlRabeler
ms.author: carlrab
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.custom: seo-dt-2019
ms.openlocfilehash: c0b26edb80b254ca6c7d3b161e618d2a6ad5849f
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85718784"
---
# <a name="sysdm_db_objects_impacted_on_version_change-azure-sql-database"></a>sys.dm_db_objects_impacted_on_version_change (Banco de Dados SQL do Azure)
[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

  Esta exibição do sistema com escopo no banco de dados é criada para fornecer um sistema de alerta rápido para determinar os objetos que serão afetados por uma atualização de versão principal no [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]. Você pode usar a exibição antes ou depois da atualização para obter uma descrição completa dos objetos afetados. Você precisará consultar essa exibição em cada banco de dados para obter uma contabilidade completa no servidor inteiro.  
  
|Nome da coluna|Tipo de Dados|Descrição|  
|-----------------|---------------|-----------------|  
|class|**int** NÃO NULO|A classe do objeto que será afetado:<br /><br /> **1** = restrição<br /><br /> **7** = Índices e heaps|  
|class_desc|**nvarchar (60)** NÃO NULO|Descrição da classe:<br /><br /> **OBJECT_OR_COLUMN**<br /><br /> **INDEX**|  
|major_id|**int** NÃO NULO|ID de objeto da restrição ou ID de objeto da tabela que contém índice ou heap.|  
|minor_id|**int** NULO|**NULL** para restrições<br /><br /> Index_id para índices e heaps|  
|dependência|**nvarchar (60)** NÃO NULO|Descrição da dependência que está causando efeito na restrição ou índice. O mesmo valor é usado também para os avisos gerados durante a atualização.<br /><br /> Exemplos:<br /><br /> **space** (para intrinsic)<br /><br /> **geometry** (para UDT de sistema)<br /><br /> **geography::Parse** (para método UDT de sistema)|  
  
## <a name="permissions"></a>Permissões  
 Exige a permissão VIEW DATABASE STATE.  
  
## <a name="example"></a>Exemplo  
 Os exemplos a seguir mostram uma consulta sobre **sys.dm_db_objects_impacted_on_version_change** para localizar objetos afetados por uma atualização na próxima versão do servidor principal  
  
```  
SELECT * FROM sys.dm_db_objects_disabled_on_version_change;  
GO  
```  
  
```  
class  class_desc        major_id    minor_id    dependency                       
------ ----------------- ----------- ----------- ----------   
1      OBJECT_OR_COLUMN  181575685   NULL        geometry                        
7      INDEX             37575172    1           geometry                        
7      INDEX             2121058592  1           geometry                        
1      OBJECT_OR_COLUMN  101575400   NULL        geometry     
```  
  
## <a name="remarks"></a>Comentários  
  
### <a name="how-to-update-impacted-objects"></a>Como atualizar objetos afetados  
 As etapas ordenadas a seguir descrevem a ação corretiva a ser realizada depois da atualização da próxima versão do serviço de junho.  
  
|Order|Objeto afetado|Ação corretiva|  
|-----------|---------------------|-----------------------|  
|1|**Índices**|Reconstrua qualquer índice identificado por **Sys. dm_db_objects_impacted_on_version_change** por exemplo:`ALTER INDEX ALL ON <table> REBUILD`<br />ou<br />`ALTER TABLE <table> REBUILD`|  
|2|**Objeto**|Todas as restrições definidas por **sys.dm_db_objects_impacted_on_version_change** devem ser revalidadas depois que os dados Geometry e Geography forem recomputados na tabela subjacente. Para restrições, revalide usando ALTER TABLE. <br />Por exemplo: <br />`ALTER TABLE <tab> WITH CHECK CHECK CONSTRAINT <constraint name>`<br />ou<br />`ALTER TABLE <tab> WITH CHECK CONSTRAINT ALL`|  
  
  
