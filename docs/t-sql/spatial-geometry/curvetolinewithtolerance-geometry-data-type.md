---
title: CurveToLineWithTolerance (tipo de dados geometry) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- CurveToLineWithTolerance method (geometry)
ms.assetid: 96871075-1998-4cd9-86b1-3fc55577aee4
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 99133135d568030646813026af0c6543a05218de
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86552843"
---
# <a name="curvetolinewithtolerance-geometry-data-type"></a>CurveToLineWithTolerance (tipo de dados geometry)
[!INCLUDE [SQL Server Azure SQL Database ](../../includes/applies-to-version/sql-asdb.md)]

Retorna uma aproximação poligonal de uma instância de **geometry** que contém segmentos de arco circulares.
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
.CurveToLineWithTolerance ( tolerance, relative )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Argumentos
 *tolerance*  
 É uma expressão **double** que define o erro máximo entre o segmento de arco circular original e sua aproximação linear.  
  
 *relative*  
 É uma expressão **bool** que indica se um máximo relativo para o desvio deve ser usado. Quando o relativo é definido como falso (0), um máximo absoluto é definido para o desvio que um aproximado linear poderá ter. Quando o relativo é definido como verdadeiro (1), a tolerância é calculada como um produto do parâmetro de tolerância e do diâmetro da caixa delimitadora do objeto espacial.  
  
## <a name="return-types"></a>Tipos de retorno  
 Tipo de retorno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geometry**  
  
 Tipo de retorno do CLR: **SqlGeometry**  
  
## <a name="exceptions"></a>Exceções  
 A configuração da tolerância <= 0 gera uma exceção `ArgumentOutOfRange`.  
  
## <a name="remarks"></a>Comentários  
 Esse método pode especificar uma quantidade de tolerância de erro para a **LineString** resultante.  
  
 A tabela a seguir mostra o tipo de instância retornado por `CurveToLineWithTolerance()`para vários tipos.  
  
|Invocando tipo de instância|Tipo espacial retornado|  
|----------------------------|---------------------------|  
|instância de geometry vazia|Instância de **GeometryCollection** vazia|  
|**Point** e **MultiPoint**|Instância de **Point**|  
|**MultiPoint**|Instância de **Point** ou **MultiPoint**|  
|**CircularString**, **CompoundCurve** ou **LineString**|Instância de **LineString**|  
|**MultiLineString**|Instância de **LineString** ou **MultiLineString**|  
|**CurvePolygon** e **Polygon**|Instância de **Polygon**|  
|**MultiPolygon**|Instância de **Polygon** ou **MultiPolygon**|  
|**GeometryCollection** com uma única instância que não contém um segmento de arco circular|A instância contida na **GeometryCollection** determina o tipo de instância retornada.|  
|**GeometryCollection** com uma instância de segmento único de arco circular unidimensional (**CircularString**, **CompoundCurve**)|Instância de **LineString**|  
|**GeometryCollection** com uma instância de segmento único de arco circular bidimensional (**CurvePolygon**)|Instância de **Polygon**|  
|**GeometryCollection** com várias instâncias unidimensionais|Instância de **MultiLineString**|  
|**GeometryCollection** com várias instâncias bidimensionais|Instância de **MultiPolygon**|  
|**GeometryCollection** com várias instâncias de dimensões diferentes|Instância de **GeometryCollection**|  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-using-different-tolerance-values-on-a-circularstring-instance"></a>a. Usando valores de tolerância diferentes em uma instância de CircularString  
 O seguinte exemplo mostra como a definição da tolerância afeta a instância de `LineString` retornada de uma instância de `CircularString`:  
  
```
 DECLARE @g geometry; 
 SET @g = geometry::Parse('CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)'); 
 SELECT @g.CurveToLineWithTolerance(0.1,0).STNumPoints(), @g.CurveToLineWithTolerance(0.01, 0).STNumPoints();
 ```  
  
### <a name="b-using-the-method-on-a-multilinestring-instance-containing-one-linestring"></a>B. Usando o método em uma instância de MultiLineString que contém uma LineString  
 O exemplo a seguir mostra o que é retornado de uma instância de `MultiLineString` que só contém uma instância de `LineString`:  
  
```
 DECLARE @g geometry; 
 SET @g = geometry::Parse('MULTILINESTRING((1 3, 4 8, 6 9))'); 
 SELECT @g.CurveToLineWithTolerance(0.1,0).ToString();
 ```  
  
### <a name="c-using-the-method-on-a-multilinestring-instance-containing-multiple-linestrings"></a>C. Usando o método em uma instância de MultiLineString que contém várias LineStrings  
 O exemplo a seguir mostra o que é retornado de uma instância de `MultiLineString` que contém mais de uma instância `LineString`:  
  
```
 DECLARE @g geometry; 
 SET @g = geometry::Parse('MULTILINESTRING((1 3, 4 8, 6 9),(4 4, 9 18))'); 
 SELECT @g.CurveToLineWithTolerance(0.1,0).ToString();
 ```  
  
### <a name="d-setting-relative-to-true-for-an-invoking-curvepolygon-instance"></a>D. Definindo o relativo como true para uma instância de CurvePolygon de invocação  
 O exemplo a seguir usa uma instância de `CurvePolygon` para chamar `CurveToLineWithTolerance()` com *relativo* definido como true:  
  
```
 DECLARE @g geometry = 'CURVEPOLYGON(COMPOUNDCURVE(CIRCULARSTRING(0 4, 4 0, 8 4), (8 4, 0 4)))'; 
 SELECT @g.CurveToLineWithTolerance(.5,1).ToString();
 ```  
  
### <a name="e-using-the-method-on-a-geometrycollection-instance"></a>E. Usando o método em uma instância de GeometryCollection  
 O exemplo a seguir chama `CurveToLineWithTolerance()` em um `GeometryCollection` que contém uma instância de `CurvePolygon` bidimensional e uma instância de `CircularString` unidimensional. `CurveToLineWithTolerance()` converte os dois tipos de segmento de arco circular para revestir tipos de segmento e os retorna em um tipo `GeometryCollection`.  
  
```
 DECLARE @g geometry; 
 SET @g = geometry::Parse('GEOMETRYCOLLECTION(CURVEPOLYGON( COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))), CIRCULARSTRING(4 4, 8 6, 9 5))'); 
 SELECT @g.CurveToLineWithTolerance(0.1,0).STNumPoints(), @g.CurveToLineWithTolerance(0.1, 0).ToString();
 ```  
  
## <a name="see-also"></a>Consulte Também  
 [CurveToLineWithTolerance &#40;tipo de dados geography&#41;](../../t-sql/spatial-geography/curvetolinewithtolerance-geography-data-type.md)   
 [STCurveToLine &#40;tipo de dados geometry&#41;](../../t-sql/spatial-geometry/stcurvetoline-geometry-data-type.md)  
  
  

