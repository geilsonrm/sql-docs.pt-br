---
title: Removendo um procedimento armazenado estendido
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.custom: seo-dt-2019
ms.openlocfilehash: 4ec666e49ccc6da12e14f7f1c85ce6eda4b6a4d0
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85723411"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a>Removendo um procedimento armazenado estendido do SQL Server
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Em vez disso, use a integração CLR.  
  
 Para descartar cada função de procedimento armazenado estendido em uma DLL de procedimento armazenado estendido definida pelo usuário, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrador do sistema deve executar o procedimento armazenado do sistema **sp_dropextendedproc** , especificando o nome da função e o nome da dll na qual a função reside. Por exemplo, esse comando Remove a função **xp_hello**, localizada em uma DLL chamada xp_hello.dll, de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , **sp_dropextendedproc** não remove os procedimentos armazenados estendidos do sistema. Em vez disso, o administrador do sistema deve negar a permissão EXECUTE no procedimento armazenado estendido para a função **pública** .  
  
## <a name="see-also"></a>Consulte Também  
 [sp_dropextendedproc &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql.md)  
  
  
