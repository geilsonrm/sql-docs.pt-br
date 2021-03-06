---
title: Propriedade Precision (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Parameter::Precision
- Field20::Precision
helpviewer_keywords:
- Precision property [ADO]
ms.assetid: 1fa38e78-6b5b-414d-ba0a-3dd26b29b766
author: rothja
ms.author: jroth
ms.openlocfilehash: a7a9b9a0a8416cb47adf8d959990ba1e39c60595
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242590"
---
# <a name="precision-property-ado"></a>Propriedade Precision (ADO)
Indica o grau de precisão para valores numéricos em um objeto de [parâmetro](../../../ado/reference/ado-api/parameter-object.md) ou para objetos de [campo](../../../ado/reference/ado-api/field-object.md) numérico.  
  
## <a name="settings-and-return-values"></a>Configurações e valores de retorno  
 Define ou retorna um valor de **byte** que indica o número máximo de dígitos usados para representar valores.  
  
## <a name="remarks"></a>Comentários  
 Use a propriedade **precisão** para determinar o número máximo de dígitos usados para representar valores para um **parâmetro** numérico ou objeto de **campo** .  
  
 O valor é leitura/gravação em um objeto de **parâmetro** .  
  
 Para um objeto **Field**, **Precision** normalmente é somente leitura. No entanto, para novos objetos **Field** que foram acrescentados à coleção [Fields](../../../ado/reference/ado-api/fields-collection-ado.md) de um [registro](../../../ado/reference/ado-api/record-object-ado.md), **Precision** é Read/Write only após a propriedade [Value](../../../ado/reference/ado-api/value-property-ado.md) do **campo** ter sido especificada e o provedor de dados adicionou com êxito o novo **campo** chamando o método [Update](../../../ado/reference/ado-api/update-method.md) da coleção **Fields** .  
  
## <a name="applies-to"></a>Aplica-se A  

:::row:::
    :::column:::
        [Objeto Campo](../../../ado/reference/ado-api/field-object.md)  
    :::column-end:::
    :::column:::
        [Objeto Parameter](../../../ado/reference/ado-api/parameter-object.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>Consulte Também  
 [Exemplo das propriedades NumericScale e Precision (VB)](../../../ado/reference/ado-api/numericscale-and-precision-properties-example-vb.md)   
 [Exemplo das propriedades NumericScale e Precision (VC + +)](../../../ado/reference/ado-api/numericscale-and-precision-properties-example-vc.md)   
 [Propriedade NumericScale (ADO)](../../../ado/reference/ado-api/numericscale-property-ado.md)
