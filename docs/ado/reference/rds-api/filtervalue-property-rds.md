---
title: Propriedade FilterValue (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- FilterValue property [ADO]
ms.assetid: 28f17186-b842-4cf9-b320-a9bb941c481b
author: rothja
ms.author: jroth
ms.openlocfilehash: 17d4585a237b2dcd32df1508aeb85b291d4d9296
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82751998"
---
# <a name="filtervalue-property-rds"></a>Propriedade FilterValue (RDS)
Indica o valor com o qual filtrar os registros.  
  
> [!IMPORTANT]
>  A partir do Windows 8 e do Windows Server 2012, os componentes do servidor RDS não são mais incluídos no sistema operacional Windows (consulte Windows 8 e [Windows Server 2012 Compatibility Cookbook](https://www.microsoft.com/download/details.aspx?id=27416) para obter mais detalhes). Os componentes do cliente RDS serão removidos em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. Os aplicativos que usam o RDS devem migrar para o [WCF Data Service](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
DataControl.FilterValue = String  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *DataControl*  
 Uma variável de objeto que representa um [RDS. Objeto DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) .  
  
 *Cadeia de caracteres*  
 Um valor de **cadeia de caracteres** que representa um valor de dados com o qual filtrar registros (por exemplo, `'Programmer'` ou `125` ).  
  
## <a name="remarks"></a>Comentários  
 As propriedades [SortColumn](../../../ado/reference/rds-api/sortcolumn-property-rds.md), [SortDirection](../../../ado/reference/rds-api/sortdirection-property-rds.md), **FilterValue**, [FilterCriterion](../../../ado/reference/rds-api/filtercriterion-property-rds.md)e [FilterColumn](../../../ado/reference/rds-api/filtercolumn-property-rds.md) fornecem funcionalidade de classificação e filtragem no cache do lado do cliente. A funcionalidade de classificação ordena registros por valores de uma coluna. A funcionalidade de filtragem exibe um subconjunto de registros com base em critérios de localização, enquanto o [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) completo é mantido no cache. O método [Reset](../../../ado/reference/rds-api/reset-method-rds.md) executará os critérios e substituirá o **conjunto** de registros atual por um **conjunto de registros**atualizável.  
  
 Valores nulos resultam em um erro de tipo incompatível.  
  
## <a name="applies-to"></a>Aplica-se A  
 [Objeto DataControl (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Exemplo das propriedades FilterColumn, FilterCriterion, FilterValue, SortColumn e SortDirection e Método Reset (VBScript)](../../../ado/reference/rds-api/filter-column-criterion-value-sortcolumn-sortdirection-example-vbscript.md)   
 [Propriedade FilterColumn (RDS)](../../../ado/reference/rds-api/filtercolumn-property-rds.md)   
 [Propriedade FilterCriterion (RDS)](../../../ado/reference/rds-api/filtercriterion-property-rds.md)   
 [Propriedade SortColumn (RDS)](../../../ado/reference/rds-api/sortcolumn-property-rds.md)   
 [Propriedade SortDirection (RDS)](../../../ado/reference/rds-api/sortdirection-property-rds.md)






















