---
title: GeometryCollection | Microsoft Docs
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
author: MladjoA
ms.author: mlandzic
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: ac76c82401a1f9796ce411d2eb15303f8f7013c6
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85751074"
---
# <a name="geometrycollection"></a>GeometryCollection
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  Uma **GeometryCollection** é uma coleção de zero ou mais instâncias de **geometry** ou de **geography** . Uma **GeometryCollection** pode estar vazia.  
  
## <a name="geometrycollection-instances"></a>Instâncias de GeometryCollection  
  
### <a name="accepted-instances"></a>Instâncias aceitas  
 Para que uma instância de **GeometryCollection** seja aceita, ela deve ser uma instância de **GeometryCollection** vazia ou todas as instâncias que englobam a instância de **GeometryCollection** devem ser instâncias aceitas. O exemplo a seguir mostra as instâncias aceitas.  
  
```sql  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 O exemplo a seguir emite uma `System.FormatException` porque a instância de **LinesString** na instância de **GeometryCollection** não é aceita.  
  
```sql  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a>Instâncias válidas  
 Uma instância de **GeometryCollection** é válida quando todas as instâncias que englobam a instância de **GeometryCollection** são válidas. O exemplo a seguir mostra três instâncias de **GeometryCollection** válidas e uma instância que não é válida.  
  
```sql  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 `@g4` não é válida porque a instância de **Polygon** na instância de **GeometryCollection** não é válida.  
  
 Para obter mais informações sobre instâncias aceitas e válidas, consulte [Point](../../relational-databases/spatial/point.md), [MultiPoint](../../relational-databases/spatial/multipoint.md), [LineString](../../relational-databases/spatial/linestring.md), [MultiLineString](../../relational-databases/spatial/multilinestring.md), [Polygon](../../relational-databases/spatial/polygon.md)e [MultiPolygon](../../relational-databases/spatial/multipolygon.md).  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria uma instância de `geometry``GeometryCollection` com valores Z no SRID 1 contendo uma instância de `Point` e uma instância de `Polygon` .  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Dados espaciais &#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md)  
  
  
