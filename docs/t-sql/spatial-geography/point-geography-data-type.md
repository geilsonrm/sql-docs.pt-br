---
title: Point (tipo de dados geography) | Microsoft Docs
ms.custom: ''
ms.date: 10/10/2019
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- Point
- Point_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- Point method
- Point (geography Data Type)
ms.assetid: 0dc6f422-7aae-4016-b7f4-3289fa8f989c
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 04db3c6617669010f63e173415de0ebf6b7a3dca
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86556146"
---
# <a name="point-geography-data-type"></a>Point (tipo de dados geography)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Constrói uma instância de **geography** que representa uma instância de **Point** de seus valores de latitude e de longitude e uma SRID (ID de referência espacial).
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Point ( Lat, Long, SRID )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Argumentos
 *Lat*  
 É uma expressão **float** que representa a coordenada Y do **Point** gerado.  
  
 *Long*  
 É uma expressão **float** que representa a coordenada X do **Point** que está sendo gerado. Para obter mais informações sobre os valores válidos de longitude e latitude, confira [Point](../../relational-databases/spatial/point.md).  
  
 *SRID*  
 É uma expressão **int** que representa a [ID de referência espacial](https://docs.microsoft.com/sql/relational-databases/spatial/spatial-reference-identifiers-srids) da instância de **geography** que você deseja retornar.  
  
> [!NOTE]  
>  Argumentos para o método Point (tipo de dados geography) têm coordenadas em ordem inversa se comparados a WKT.  
  
## <a name="return-types"></a>Tipos de retorno  
 Tipo de retorno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geography**  
  
 Tipo de retorno CLR: **SqlGeography**  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir usa `Point()` para criar uma instância `geography`.  
  
```  
DECLARE @g geography;   
SET @g = geography::Point(47.65100, -122.34900, 4326)  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Extended Static Geography Methods](../../t-sql/spatial-geography/extended-static-geography-methods.md)  
