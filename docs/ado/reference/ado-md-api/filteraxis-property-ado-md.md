---
title: Propriedade FilterAxis (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Cellset::FilterAxis
- FilterAxis
helpviewer_keywords:
- FilterAxis property [ADO MD]
ms.assetid: 9c656963-531e-4cd1-b698-d5f42a9b7ba3
author: rothja
ms.author: jroth
ms.openlocfilehash: b7f9b34757970ce98dedaa9601340cad533ad002
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764227"
---
# <a name="filteraxis-property-ado-md"></a>Propriedade FilterAxis (ADO MD)
Indica informações de filtro sobre o [células](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)atual.  
  
## <a name="return-values"></a>Valores de retorno  
 Retorna um objeto [Axis](../../../ado/reference/ado-md-api/axis-object-ado-md.md) e é somente leitura.  
  
## <a name="remarks"></a>Comentários  
 Use a propriedade **FilterAxis** para retornar informações sobre as dimensões que foram usadas para dividir os dados. A propriedade [DimensionCount](../../../ado/reference/ado-md-api/dimensioncount-property-ado-md.md) do **eixo** retorna o número de dimensões da segmentação. Esse eixo geralmente tem apenas uma linha.  
  
 O **eixo** retornado por **FilterAxis** não está contido na coleção de [eixos](../../../ado/reference/ado-md-api/axes-collection-ado-md.md) de um objeto [células](../../../ado/reference/ado-md-api/cellset-object-ado-md.md) .  
  
## <a name="applies-to"></a>Aplica-se A  
 [Objeto Cellset (ADO MD)](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Objeto Axis (ADO MD)](../../../ado/reference/ado-md-api/axis-object-ado-md.md)   
 [Objeto Dimension (ADO MD)](../../../ado/reference/ado-md-api/dimension-object-ado-md.md)   
 [Propriedade DimensionCount (ADO MD)](../../../ado/reference/ado-md-api/dimensioncount-property-ado-md.md)
