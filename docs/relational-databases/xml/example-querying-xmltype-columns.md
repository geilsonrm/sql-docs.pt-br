---
title: 'Exemplo: consultando colunas de tipo XML | Microsoft Docs'
description: Veja um exemplo de como consultar colunas do tipo de dados XML.
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, querying XML example
ms.assetid: d9f3710d-7a2e-4abe-9c02-3e3c0df4d620
author: MightyPen
ms.author: genemi
ms.openlocfilehash: d5e28c3b6a68e765287cfcc2934c06fb25270f5d
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85633113"
---
# <a name="example-querying-xmltype-columns"></a>Exemplo: consultando colunas XMLType
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  A consulta a seguir inclui colunas de tipo **xml** . A consulta recupera a ID, nome e etapas de fabricação do modelo do produto no primeiro local da coluna `Instructions` de tipo **xml** .  
  
## <a name="example"></a>Exemplo  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
')   
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
GO  
```  
  
 O seguinte é o resultado. Observe que a tabela armazena instruções de fabricação para apenas alguns modelos do produto. As etapas de fabricação são retornadas como subelementos do elemento <`ProductModelData`> no resultado.  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
    <MI:step> ... </MI:step>  
    <MI:step> ... </MI:step>  
 </ProductModelData>  
```  
  
 Se a consulta especificar um nome de coluna para o XML retornado pelo XQuery, conforme especificado na instrução `SELECT` a seguir, as etapas de fabricação serão encapsuladas no elemento que tem o nome especificado.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData')  
go  
```  
  
 Este é o resultado:  
  
```  
<ProductModelData ProductModelID="5" Name="HL Mountain Frame" />  
<ProductModelData ProductModelID="6" Name="HL Road Frame" />  
<ProductModelData ProductModelID="7" Name="HL Touring Frame">  
  <ManuSteps>  
    <MI:step ... </MI:step>  
    <MI:step ... </MI:step>  
  </ManuSteps>  
</ProductModelData>  
```  
  
 A consulta a seguir especifica a política `ELEMENTS` . Portanto o resultado retornado é centrado em elemento. A opção `XSINIL` especificada com a política `ELEMENTS` retorna os elementos <`ManuSteps`>, mesmo que a colunas correspondentes no conjunto de linhas sejam NULL.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name,  
   Instructions.query('  
declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"  
   /MI:root/MI:Location[1]/MI:step  
') as ManuSteps  
FROM Production.ProductModel  
FOR XML RAW ('ProductModelData'), root('MyRoot'), ELEMENTS XSINIL  
go  
```  
  
 Este é o resultado:  
  
```  
<MyRoot xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   ...  
  <ProductModelData>  
    <ProductModelID>6</ProductModelID>  
    <Name>HL Road Frame</Name>  
    <ManuSteps xsi:nil="true" />  
  </ProductModelData>  
  <ProductModelData>  
    <ProductModelID>7</ProductModelID>  
    <Name>HL Touring Frame</Name>  
    <ManuSteps>  
      <MI:step ... </MI:step>  
      <MI:step ...</MI:step>  
       ...  
    </ManuSteps>  
  </ProductModelData>  
</MyRoot>  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Usar o modo RAW com FOR XML](../../relational-databases/xml/use-raw-mode-with-for-xml.md)  
  
  
