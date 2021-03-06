---
title: syspolicy_policy_categories (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syspolicy_policy_categories
- syspolicy_policy_categories_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syspolicy_policy_groups view
ms.assetid: 65f080c7-771f-4cf6-a7a0-88882c637f8d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 766aa7e2d60a19c5f6b6093dc72685175d8fbc3b
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85900594"
---
# <a name="syspolicy_policy_categories-transact-sql"></a>syspolicy_policy_categories (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Exibe uma linha para cada categoria de política do Gerenciamento Baseado em Políticas na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. As categorias de políticas ajudam a organizar as políticas quando há muitas delas. A tabela a seguir descreve as colunas na exibição syspolicy_policy_groups.  
 
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|policy_category_id|**int**|Identificador da categoria da política.|  
|name|**sysname**|Nome da categoria de política.|  
|mandate_database_subscriptions|**bit**|Indica se a categoria da política aplica-se a todos os bancos de dados de uma instância sem uma assinatura explícita (1) ou se a categoria da política deve ser aplicada a um banco de dados usando uma assinatura explícita (0).|  
  
## <a name="remarks"></a>Comentários  
 Exibe uma lista dos grupos de políticas do Gerenciamento Baseado em Política.  
  
## <a name="permissions"></a>Permissões  
 Requer a associação à função PolicyAdministratorRole no banco de dados msdb.  
  
## <a name="see-also"></a>Consulte Também  
 [Administrar servidores usando o gerenciamento baseado em políticas](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)   
 [Exibições de Gerenciamento Baseado em Políticas &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/policy-based-management-views-transact-sql.md)  
  
  
