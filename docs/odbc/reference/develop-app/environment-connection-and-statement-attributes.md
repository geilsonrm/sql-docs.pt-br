---
title: Atributos de ambiente, conexão e instrução | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- environment attributes [ODBC]
- connection attributes [ODBC]
- statement attributes [ODBC]
ms.assetid: 9e15b276-3b7a-428a-b72f-a3ddfe1ba1ce
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 86cecaf0b82c7b6d15b3f37262507d2cff0c3c10
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300926"
---
# <a name="environment-connection-and-statement-attributes"></a>Atributos de ambiente, conexão e instrução
O ODBC define um número de atributos associados a ambientes, conexões ou instruções.  
  
 Os atributos de ambiente afetam todo o ambiente, como se o pool de conexões está habilitado. Os atributos de ambiente são definidos com **SQLSetEnvAttr** e recuperados com **SQLGetEnvAttr**.  
  
 Os atributos de conexão afetam cada conexão individualmente, como quanto tempo um driver deve aguardar ao tentar se conectar a uma fonte de dados antes de atingir o tempo limite. Os atributos de conexão são definidos com **SQLSetConnectAttr** e recuperados com **SQLGetConnectAttr**. Para obter mais informações sobre atributos de conexão, consulte [atributos de conexão](../../../odbc/reference/develop-app/connection-attributes.md).  
  
 Os atributos de instrução afetam cada instrução individualmente, como se uma instrução deve ser executada de forma assíncrona. Os atributos de instrução são definidos com **SQLSetStmtAttr** e recuperados com **SQLGetStmtAttr**. Alguns atributos de instrução são atributos somente leitura e não podem ser definidos. Por exemplo, o atributo de instrução SQL_ATTR_ROW_NUMBER, que é usado para recuperar o número da linha atual no cursor, é somente leitura. Para obter mais informações sobre atributos de instrução, consulte [atributos de instrução](../../../odbc/reference/develop-app/statement-attributes.md).  
  
 Além dos atributos definidos pelo ODBC, um driver pode definir seus próprios atributos de conexão e instrução. Os atributos definidos pelo driver devem ser registrados com o grupo aberto para garantir que dois fornecedores de driver não atribuam o mesmo valor inteiro a atributos proprietários e diferentes. Para obter mais informações, consulte [tipos de dados específicos do driver, tipos de descritores, tipos de informações, tipos de diagnóstico e atributos](../../../odbc/reference/develop-app/driver-specific-data-types-descriptor-information-diagnostic.md).  
  
 Para obter uma lista completa de atributos, consulte [SQLSetEnvAttr](../../../odbc/reference/syntax/sqlsetenvattr-function.md), [SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md)e [SQLSetStmtAttr](../../../odbc/reference/syntax/sqlsetstmtattr-function.md). A maioria dos atributos também é descrita na descrição da função ODBC que eles afetam.
