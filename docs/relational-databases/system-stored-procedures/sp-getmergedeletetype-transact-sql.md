---
title: sp_getmergedeletetype (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_getmergedeletetype
- sp_getmergedeletetype_TSQL
helpviewer_keywords:
- sp_getmergedeletetype
ms.assetid: 64450e4d-844d-4176-874e-f3845536f7d2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 406eb51a43b350a5e6f0f2d4723baab40a62ce5e
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85881614"
---
# <a name="sp_getmergedeletetype-transact-sql"></a>sp_getmergedeletetype (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Retorna o tipo de exclusão de mesclagem. Esse procedimento armazenado é executado no Publicador do banco de dados de publicação ou no Assinante no banco de dados de assinatura.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_getmergedeletetype [ @source_object = ] 'source_object', [ @rowguid =] 'rowguid', [ @delete_type=] delete_type OUTPUT  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @source_object = ] 'source_object'`É o nome do objeto de origem. *source_object* é **nvarchar (386)**, sem padrão.  
  
`[ @rowguid = ] 'rowguid'`É o identificador de linha para o tipo de exclusão. *ROWGUID* é **uniqueidentifier**, sem padrão.  
  
`[ @delete_type = ] delete_type OUTPUT`É o código que indica o tipo de exclusão. *delete_type* é **int**, sem padrão. *delete_type* também é um parâmetro de saída e pode ser um desses valores.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|**1**|Exclusão de usuário|  
|**5**|Exclusão parcial|  
|**6**|Exclusão de sistema|  
  
## <a name="remarks"></a>Comentários  
 **sp_getmergedeletetype** é usado na replicação de mesclagem.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros da função de servidor fixa **sysadmin** ou a função de banco de dados fixa **db_owner** podem ser executados **sp_getmergedeletetype**.  
  
## <a name="see-also"></a>Consulte Também  
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
