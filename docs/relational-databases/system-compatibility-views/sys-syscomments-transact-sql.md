---
title: sys.syscomentários (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.syscomments_TSQL
- syscomments
- syscomments_TSQL
- sys.syscomments
dev_langs:
- TSQL
helpviewer_keywords:
- sys.syscomments compatibility view
- syscomments system table
ms.assetid: 767dd410-6bc9-4c4a-ab0f-6d2cf6163426
author: rothja
ms.author: jroth
ms.openlocfilehash: 49473b85d6c0a52f9c7ec7ed4bab519b19b04693
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85883480"
---
# <a name="syssyscomments-transact-sql"></a>sys.syscomments (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contém entradas para cada exibição, regra, padrão, gatilho, restrição CHECK, restrição DEFAULT e procedimento armazenado no banco de dados. A coluna de **texto** contém as instruções de definição SQL originais.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] É recomendável usar sys.sql_modules. Para obter mais informações, consulte [Sys. sql_modules &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-sql-modules-transact-sql.md).  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|**id**|**int**|ID do objeto ao qual esse texto se aplica.|  
|**number**|**smallint**|Número no agrupamento do procedimento, se agrupado.<br /><br /> 0 = Entradas não são procedimentos.|  
|**colid**|**smallint**|Número de sequência de linha para definições de objeto superiores a 4.000 caracteres.|  
|**status**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**ctext**|**varbinary(8000)**|Os bytes brutos da instrução de definição SQL.|  
|**texttype**|**smallint**|0 = Comentário fornecido pelo usuário<br /><br /> 1 = Comentário fornecido pelo sistema<br /><br /> 4 = Comentário criptografado|  
|**idioma**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**criptografados**|**bit**|Indica se a definição de procedimento é ofuscada.<br /><br /> 0 = Não ofuscado<br /><br /> 1 = Ofuscado<br /><br /> Importante para ofuscar as definições de procedimento armazenado, use criar procedimento com a palavra-chave Encryption. ** \* \* \* \* **|  
|**compactados**|**bit**|Sempre retorna 0. Isso indica se o procedimento é compactado.|  
|**text**|**nvarchar(4000)**|Texto real da instrução de definição SQL.<br /><br /> A semântica da expressão decodificada equivale ao texto original; porém, não há nenhuma garantia sintática. Por exemplo, espaços em branco são removidos da expressão decodificada.<br /><br /> Essa [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] exibição compatível Obtém informações das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estruturas atuais e pode retornar mais caracteres do que a definição **nvarchar (4000)** . **sp_help** retorna **nvarchar (4000)** como o tipo de dados da coluna de texto. Ao trabalhar com **syscomments** , considere o uso **de nvarchar (max)**. Para novos trabalhos de desenvolvimento, não use **syscomments**.|  
  
## <a name="see-also"></a>Consulte Também  
 [Mapeando tabelas do sistema para exibições do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Exibições de compatibilidade &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
