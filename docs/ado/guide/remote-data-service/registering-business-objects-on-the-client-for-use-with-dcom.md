---
title: Registrando objetos comerciais no cliente para uso com DCOM | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- business objects in RDS [ADO]
ms.assetid: 75a21910-607f-463a-ae18-a17130dafb7e
author: rothja
ms.author: jroth
ms.openlocfilehash: 79f88f36b7eae83163ef2754f9b2c2265550c684
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82747664"
---
# <a name="registering-business-objects-on-the-client-for-use-with-dcom"></a>Registrar objetos de negócios no cliente para uso com DCOM
Os objetos comerciais personalizados precisam garantir que o lado do cliente possa mapear o nome do programa (ProgId) para um identificador (CLSID) que possa ser usado no DCOM. Por esse motivo, o ProgID do objeto DCOM deve estar no registro do lado do cliente e ser mapeado para a ID de classe do objeto comercial do lado do servidor. Para os outros protocolos com suporte (HTTP, HTTPS e em processo), isso não é necessário.  
  
> [!IMPORTANT]
>  A partir do Windows 8 e do Windows Server 2012, os componentes do servidor RDS não são mais incluídos no sistema operacional Windows (consulte Windows 8 e [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) para obter mais detalhes). Os componentes do cliente RDS serão removidos em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Os aplicativos que usam o RDS devem migrar para o [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 Por exemplo, se você expor um objeto comercial do lado do servidor chamado MyBObj com uma ID de classe específica, por exemplo, "{00112233-4455-6677-8899-00AABBCCDDEE}", certifique-se de que as seguintes entradas sejam adicionadas ao registro do lado do cliente:  
  
```console
[HKEY_CLASSES_ROOT]  
\MyBObj\Clsid\(Default) "{00112233-4455-6677-8899-00AABBCCDDEE}"  
```


