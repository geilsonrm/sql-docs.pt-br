---
title: Objeto de procedimento (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Procedure
helpviewer_keywords:
- Procedure object [ADOX]
ms.assetid: 927bcf3e-32f5-4a80-98d3-600779f0732e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4a56088e47a9f794f1862ef87bf142a8d3ab12c4
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763687"
---
# <a name="procedure-object-adox"></a>Objeto Procedure (ADOX)
Representa um procedimento armazenado. Quando usado em conjunto com o objeto de [comando](../../../ado/reference/ado-api/command-object-ado.md) ADO, o objeto de **procedimento** pode ser usado para adicionar, excluir ou modificar procedimentos armazenados.  
  
## <a name="remarks"></a>Comentários  
 O objeto **Procedure** permite que você crie um procedimento armazenado sem precisar saber ou usar a sintaxe "criar procedimento" do provedor.  
  
 Com as propriedades de um objeto de **procedimento** , você pode:  
  
-   Identifique o procedimento com a propriedade [Name](../../../ado/reference/adox-api/name-property-adox.md) .  
  
-   Especifique o objeto de **comando** ADO que pode ser usado para criar ou executar o procedimento com a propriedade [Command](../../../ado/reference/adox-api/command-property-adox.md) .  
  
-   Retornar informações de data com as propriedades [DateCreated](../../../ado/reference/adox-api/datecreated-property-adox.md) e [DateModified](../../../ado/reference/adox-api/datemodified-property-adox.md) .  
  
 Esta seção contém o tópico a seguir.  
  
-   [Propriedades, Métodos e Eventos do objeto Procedure](../../../ado/reference/adox-api/procedure-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Exemplo das propriedades Command e CommandText (VB)](../../../ado/reference/adox-api/command-and-commandtext-properties-example-vb.md)   
 [Coleção Parameters, exemplo da Propriedade Command (VB)](../../../ado/reference/adox-api/parameters-collection-command-property-example-vb.md)   
 [Exemplo do método Append Procedures (VB)](../../../ado/reference/adox-api/procedures-append-method-example-vb.md)   
 [Exemplo do método Delete de procedimentos (VB)](../../../ado/reference/adox-api/procedures-delete-method-example-vb.md)   
 [Coleção Procedures (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)
