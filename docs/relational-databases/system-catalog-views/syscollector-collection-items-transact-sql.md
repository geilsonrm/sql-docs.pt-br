---
title: syscollector_collection_items (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syscollector_collection_items_TSQL
- syscollector_collection_items
dev_langs:
- TSQL
helpviewer_keywords:
- syscollector_collection_items view
- add data collector view
ms.assetid: a279ecd1-a59c-4315-9f08-bf221f00a465
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f775d96b0bc56217f1400021e6c51b62d2886e5f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85899956"
---
# <a name="syscollector_collection_items-transact-sql"></a>syscollector_collection_items (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Retorna informações sobre um item em um conjunto de coleta.  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**collection_set_id**|**int**|Identifica o conjunto de coleta. Não permite valor nulo.|  
|**collection_item_id**|**int**|Identifica um item no conjunto de coleta. Não permite valor nulo.|  
|**collector_type_uid**|**uniqueidentifier**|GUID usado para identificar o tipo de coletor. Não permite valor nulo.|  
|**name**|**nvarchar(4000)**|Nome do conjunto de coleta. Permite valor nulo.|  
|**frequência**|**int**|Frequência com que os dados são coletados por um item de coleta. Não permite valor nulo.|  
|**parameters**|**xml**|Descreve a parametrização para o tipo de coletor associado ao item de coleta. O esquema XML para esse item de coleta é validado com o esquema XML (XSD) armazenado no **parameter_schema** para um tipo de coletor específico. Permite valor nulo. Para obter mais informações, consulte [syscollector_collector_types &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/syscollector-collector-types-transact-sql.md).|  
  
## <a name="permissions"></a>Permissões  
 Requer SELECT for **dc_operator**, **dc_proxy**.  
  
## <a name="see-also"></a>Consulte Também  
 [Procedimentos armazenados do coletor de dados &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [Exibições do coletor de dados &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/data-collector-views-transact-sql.md)   
 [Coleta de dados](../../relational-databases/data-collection/data-collection.md)  
  
  
