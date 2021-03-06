---
title: Interface ADOStreamConstruction | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADOStreamConstruction
helpviewer_keywords:
- ADOStreamConstruction interface [ADO]
ms.assetid: 92f5a939-3e1a-4b14-a9dd-90e6ce2dec74
author: rothja
ms.author: jroth
ms.openlocfilehash: 2c120667a0ce279ea03922adf487f58c1fdc92de
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82747054"
---
# <a name="adostreamconstruction-interface"></a>ADOStreamConstruction Interface
A interface **ADOStreamConstruction** é usada para construir um objeto de **fluxo** ADO de um objeto OLE DB **IStream** em um aplicativo C/C++.  
  
## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|[Propriedade Stream](../../../ado/reference/ado-api/stream-property.md)|Leitura/gravação. Obtém/define um objeto de **fluxo** de OLE DB.|  
  
## <a name="methods"></a>Métodos  
 Nenhum.  
  
## <a name="events"></a>Eventos  
 Nenhum.  
  
## <a name="remarks"></a>Comentários  
 Dado um OLE DB objeto **IStream** ( `pStream` ), a construção de um objeto de **fluxo** ADO ( `adoStr` ) é quantiada para as três operações básicas a seguir:  
  
1.  Criar um objeto de **fluxo** ADO:  
  
    ```  
    Stream20Ptr adoStr;  
    adoStr.CreateInstance(__uuidof(Stream));  
    ```  
  
2.  Consulte a interface **IADOStreamConstruction** no objeto **Stream** :  
  
    ```  
    adoStreamConstructionPtr adoStrConstruct=NULL;  
    adoStr->QueryInterface(__uuidof(ADOStreamConstruction),  
                         (void**)&adoStrConstruct);  
    ```  
  
 Chame o `IADOStreamConstruction::get_Stream` método Property para definir o objeto OLE DB **IStream** no objeto de **fluxo** ADO:  
  
```  
IUnknown *pUnk=NULL;  
pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);  
adoStrConstruct->put_Stream(pUnk);  
```  
  
 O objeto resultante `adoStr` agora representa o objeto de **fluxo** ADO construído a partir do objeto OLE DB **IStream** .  
  
## <a name="requirements"></a>Requisitos  
 **Versão:** ADO 2,0 ou uma versão posterior  
  
 **Biblioteca:** MsADO15. dll  
  
 **UUID:** 00000283-0000-0010-8000-00AA006D2EA4  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de API ADO](../../../ado/reference/ado-api/ado-api-reference.md)
