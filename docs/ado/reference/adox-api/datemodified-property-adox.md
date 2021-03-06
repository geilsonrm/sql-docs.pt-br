---
title: Propriedade DateModified (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Table::get_DateModified
- _Table::DateModified
- _Table::GetDateModified
helpviewer_keywords:
- DateModified property [ADOX]
ms.assetid: fed09266-1547-4bda-9088-c254d81cc738
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c3a2a8ba0890dd50621fac143aa102091abcc19
ms.sourcegitcommit: 591bbf4c7e4e2092f8abda6a2ffed263cb61c585
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86942708"
---
# <a name="datemodified-property-adox"></a>Propriedade DateModified (ADOX)
Indica a data em que o objeto foi modificado pela última vez.  
  
## <a name="return-values"></a>Valores de retorno  
 Retorna um valor **Variant** que especifica a data de modificação. O valor será NULL se **DateModified** não tiver suporte do provedor.  
  
## <a name="remarks"></a>Comentários  
 A propriedade **DateModified** é nula para objetos acrescentados recentemente. Depois de acrescentar uma nova [exibição](../../../ado/reference/adox-api/view-object-adox.md) ou [procedimento](../../../ado/reference/adox-api/procedure-object-adox.md), você deve chamar o método [Refresh](../../../ado/reference/ado-api/refresh-method-ado.md) da coleção [views](../../../ado/reference/adox-api/views-collection-adox.md) ou [procedures](../../../ado/reference/adox-api/procedures-collection-adox.md) para obter valores para a propriedade **DateModified** .  
  
## <a name="applies-to"></a>Aplica-se A  

:::row:::
    :::column:::
        [Objeto Procedure (ADOX)](../../../ado/reference/adox-api/procedure-object-adox.md)  
    :::column-end:::
    :::column:::
        [Objeto Table (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)  
    :::column-end:::
    :::column:::
        [Objeto View (ADOX)](../../../ado/reference/adox-api/view-object-adox.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>Consulte Também  
 [Exemplo das propriedades DateCreated e DateModified (VB)](../../../ado/reference/adox-api/datecreated-and-datemodified-properties-example-vb.md)   
 [Propriedade DateCreated (ADOX)](../../../ado/reference/adox-api/datecreated-property-adox.md)
