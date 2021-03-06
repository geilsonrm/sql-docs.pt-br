---
title: managed_backup. fn_get_current_xevent_settings (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- fn_get_current_xevent_settings
- smart_admin.fn_get_current_xevent_settings_TSQL
- fn_get_current_xevent_settings_TSQL
- smart_admin.fn_get_current_xevent_settings
dev_langs:
- TSQL
helpviewer_keywords:
- smart_admin.fn_get_current_xevent_settings
- fn_get_current_xevent_settings
ms.assetid: 95d3adaa-bb9d-4833-b8b4-3d9fd4f9c82a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cff78d30f768360c55b212742770d8caded6f5ee
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86053442"
---
# <a name="managed_backupfn_get_current_xevent_settings-transact-sql"></a>managed_backup. fn_get_current_xevent_settings (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  Retorna 1 linha para cada tipo de Evento Estendido com suporte no Administrador Inteligente.  
  
 Use esta função para retornar ou examinar as configurações atuais do Evento Estendido para identificar o tipo de eventos que são configuráveis e as configurações atuais.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```sql  
smart_admin.fn_get_current_xevent_settings ()   
```  
  
##  <a name="arguments"></a><a name="Arguments"></a>Argumentos  
 Essa função não tem nenhum argumento.  
  
## <a name="table-returned"></a>Tabela retornada  
 A administração, as análises e os canais operacionais dos Eventos Estendidos são necessários, habilitados por padrão e não são configuráveis.  
  
|Nome da coluna|Tipo de Dados|Descrição|  
|-----------------|---------------|-----------------|  
|Event_name|NVARCHAR(128)|Tipo de eventos estendidos|  
|is_configurable|NVARCHAR(128)|Isso será definido como **true** se o evento for configurável, caso contrário, ele será definido como **false**.|  
|is_enabled|NVARCHAR(128)|Isso será definido como True se o evento estiver habilitado; defina como False se não estiver habilitado. Use o smart_admin.sp_set_parameter para habilitar eventos de depuração.|  
  
## <a name="security"></a>Segurança  
  
### <a name="permissions"></a>Permissões  
 Requer permissões **Select** na função.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir retorna todos os Eventos Estendidos com seu status atual.  
  
```  
SELECT *   
FROM smart_admin.fn_get_current_xevent_settings ()  
  
```  
  
  
