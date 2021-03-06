---
title: Definindo o formato de marshaling de fluxo DCOM | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- dcom stream marshaling format in rds [ADO]
ms.assetid: 46664ac5-d6e6-4457-8bae-3a98300f2a41
author: rothja
ms.author: jroth
ms.openlocfilehash: f3e7dd82d54b20ccceec73c0917f4f81c3cf16dd
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82758952"
---
# <a name="setting-dcom-stream-marshaling-format"></a>Configurar o formato de marshaling de fluxo DCOM
Um computador cliente que usa componentes do RDS 1,5 ou anterior não é compatível com um servidor usando componentes do RDS 2,0 ou posterior. Ao usar o DCOM como o protocolo subjacente, o suporte para o RDS 2,0 ou posterior é mais eficiente no transporte de objetos [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md) . Se o cliente estiver executando componentes do RDS 1,5 ou anterior, você poderá definir seu servidor para trabalhar com o suporte RDS anterior (chamado RDS 1,0) ou com o suporte RDS mais recente (chamado RDS 2,0 ou posterior). Defina uma das seguintes entradas do registro:  
  
> [!IMPORTANT]
>  A partir do Windows 8 e do Windows Server 2012, os componentes do servidor RDS não são mais incluídos no sistema operacional Windows (consulte Windows 8 e [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) para obter mais detalhes). Os componentes do cliente RDS serão removidos em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Os aplicativos que usam o RDS devem migrar para o [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
```console
[HKEY_CLASSES_ROOT]  
\CLSID\[58ECEE30-E715-11CF-B0E3-00AA003F000F}\ADTGOptions]"MarshalFormat"="RDS10"  
```  
  
 – ou –  
  
```console
[HKEY_CLASSES_ROOT]  
\CLSID\[58ECEE30-E715-11CF-B0E3-00AA003F000F}\ADTGOptions]"MarshalFormat"="RDS20"  
```


