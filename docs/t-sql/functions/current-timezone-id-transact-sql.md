---
title: CURRENT_TIMEZONE (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2020
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- CURRENT_TIMEZONE)ID
- CURRENT_TIMEZONE_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- current time zone id [SQL Server]
- current timezoneid [SQL Server]
- system time zone id[SQL Server]
- system timezone id[SQL Server]
- functions [SQL Server], time zone id
- functions [SQL Server], timezoneid
- timezoneid [SQL Server], functions
- time zone id [SQL Server], functions
- CURRENT_TIMEZONE_ID function [SQL Server]
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 3cadc9cd33fd1cdabb96cf450ad09253fdd435d1
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85684619"
---
# <a name="current_timezone_id-transact-sql"></a>CURRENT_TIMEZONE_ID (Transact-SQL)

[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

Essa função retorna a ID do fuso horário observado por um servidor ou uma instância. Para a Instância Gerenciada de SQL do Azure, o valor retornado se baseia no fuso horário da própria instância atribuído durante sua criação, e não no fuso horário do sistema operacional subjacente.
  
> [!NOTE]  
> Para os Banco de Dados SQL únicos e em pool, o fuso horário é sempre definido como UTC e `CURRENT_TIMEZONE_ID` retorna a ID do fuso horário UTC.
  
## <a name="syntax"></a>Sintaxe  
  
```sql
CURRENT_TIMEZONE_ID ( )  
```
  
## <a name="arguments"></a>Argumentos

Essa função não utiliza argumentos.
  
## <a name="return-type"></a>Tipo de retorno  

**varchar**
  
## <a name="remarks"></a>Comentários  

`CURRENT_TIMEZONE_ID` é uma função não determinística. Exibições e expressões que fazem referência a esta coluna não podem ser indexadas.
  
## <a name="example"></a>Exemplo

O valor retornado refletirá o fuso horário real e as configurações de idioma do servidor ou da instância.

```sql
SELECT CURRENT_TIMEZONE_ID();  
/* Returned:  
W. Europe Standard Time
*/
```  
  
## <a name="see-also"></a>Confira também

[Fuso Horário da Instância Gerenciada do Banco de Dados SQL](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-timezone)

[CURRENT_TIMEZONE()](https://docs.microsoft.com/sql/t-sql/functions/current-timezone-transact-sql)
