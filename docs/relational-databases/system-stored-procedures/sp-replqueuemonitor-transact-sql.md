---
title: sp_replqueuemonitor (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_replqueuemonitor
- sp_replqueuemonitor_TSQL
helpviewer_keywords:
- sp_replqueuemonitor
ms.assetid: 6909a3f1-43a2-4df5-a6a5-9e6f347ac841
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73b999f1f6ee2ba49209f5763be6bb42e777ef78
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85626932"
---
# <a name="sp_replqueuemonitor-transact-sql"></a>sp_replqueuemonitor (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Lista as mensagens de fila de uma [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fila ou [!INCLUDE[msCoName](../../includes/msconame-md.md)] enfileiramento de mensagens para assinaturas de atualização enfileiradas em uma publicação especificada. Se as filas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forem usadas, esse procedimento armazenado será executado no banco de dados de assinatura. Se o Enfileiramento de Mensagens for usado, esse procedimento armazenado será executado no Distribuidor, no banco de dados de distribuição.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_replqueuemonitor [ @publisher = ] 'publisher'  
    [ , [ @publisherdb = ] 'publisher_db' ]  
    [ , [ @publication = ] 'publication' ]  
    [ , [ @tranid = ] 'tranid' ]  
    [ , [ @queuetype = ] 'queuetype' ]  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @publisher = ] 'publisher'`É o nome do Publicador. o *Publicador* é **sysname**, com um padrão de NULL. O servidor deve ser configurado para publicação. NULL para todos os Publicadores.  
  
`[ @publisherdb = ] 'publisher_db' ]`É o nome do banco de dados de publicação. *publisher_db* é **sysname**, com um padrão de NULL. NULL para todos os bancos de dados de publicação.  
  
`[ @publication = ] 'publication' ]`É o nome da publicação. a *publicação*é **sysname**, com um padrão de NULL. NULL para todas as publicações.  
  
`[ @tranid = ] 'tranid' ]`É a ID da transação. *tranid*é **sysname**, com um padrão de NULL. NULL para todas as transações.  
  
`[ @queuetype = ] 'queuetype' ]`É o tipo de fila que armazena transações. *QueueType* é **tinyint** com um padrão de **0**e pode ser um desses valores.  
  
|Valor|Descrição|  
|-----------|-----------------|  
|**0**|Todos os tipos de filas|  
|**1**|Enfileiramento de Mensagens|  
|**2**|Fila do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Comentários  
 **sp_replqueuemonitor** é usado na replicação de instantâneo ou na replicação transacional com assinaturas de atualização enfileiradas. As mensagens em fila que não contêm comandos SQL ou são parte de um comando SQL abrangente não são exibidas.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros da função de servidor fixa **sysadmin** ou **db_owner** função de banco de dados fixa podem ser executados **sp_replqueuemonitor**.  
  
## <a name="see-also"></a>Consulte Também  
 [Assinaturas atualizáveis para replicação transacional](../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
