---
title: ISJSON (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/03/2020
ms.prod: sql
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- ISJSON
- ISJSON_TSQL
helpviewer_keywords:
- ISJSON function
- JSON, validating
ms.assetid: c836f3d3-3e17-44ae-92bf-f341918896c3
author: jovanpop-msft
ms.author: jovanpop
ms.reviewer: jroth
monikerRange: = azuresqldb-current||= azure-sqldw-latest||>= sql-server-2016||>= sql-server-linux-2017||= sqlallproducts-allversions
ms.openlocfilehash: c29bacf9d9342bcad526d46042203cb3e1848c64
ms.sourcegitcommit: 768f046107642f72693514f51bf2cbd00f58f58a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87112929"
---
# <a name="isjson-transact-sql"></a>ISJSON (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-asdw-xxx-md.md)]

  Testa se uma cadeia de caracteres contém um JSON válido.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```sql  
ISJSON ( expression )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Argumentos
 *expressão*  
 A cadeia de caracteres a ser testada.  
  
## <a name="return-value"></a>Valor retornado  
 Retornará 1 se a cadeia de caracteres contiver um JSON válido, caso contrário, retornará 0. Retornará nulo se a *expressão* for nula.  
  
 Não retorna erros.  
  
## <a name="remarks"></a>Comentários  
 **ISJSON** não verifica a exclusividade das chaves no mesmo nível.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="example-1"></a>Exemplo 1  
O exemplo a seguir executará um bloco de instruções condicionalmente se o valor do parâmetro `@param` contiver um JSON válido.  
  
```sql  
DECLARE @param <data type>
SET @param = <value>

IF (ISJSON(@param) > 0)  
BEGIN  
     -- Do something with the valid JSON value of @param.  
END
```  
  
### <a name="example-2"></a>Exemplo 2  
O exemplo a seguir retorna linhas em que a coluna `json_col` contém um JSON válido.  
  
```sql  
SELECT id, json_col
FROM tab1
WHERE ISJSON(json_col) > 0 
```  
  
## <a name="see-also"></a>Consulte Também  
 [Dados JSON &#40;SQL Server&#41;](../../relational-databases/json/json-data-sql-server.md)  
  
  
