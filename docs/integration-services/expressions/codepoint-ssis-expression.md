---
title: CODEPOINT (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CODEPOINT function
- leftmost character of expression
ms.assetid: 0783d05e-7f35-42fb-a2c4-9621c46effd6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e856482cd7ef4094b6383d6365efe88d83c84bb0
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86916442"
---
# <a name="codepoint-ssis-expression"></a>CODEPOINT (Expressão SSIS)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Retorna o ponto de código Unicode do caractere da extrema esquerda de uma expressão de caracteres.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
CODEPOINT(character_expression)  
```  
  
## <a name="arguments"></a>Argumentos  
 *character_expression*  
 É uma expressão de caracteres cujo caractere da extrema esquerda será avaliado.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_UI2  
  
## <a name="remarks"></a>Comentários  
 *character_expression* deve ter o tipo de dados DT_WSTR.  
  
 CODEPOINT retornará um resultado nulo se *character_expression* for nulo ou uma cadeia de caracteres vazia.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Este exemplo usa um literal de cadeia de caracteres. O resultado de retorno é 77, o ponto de código Unicode para M.  
  
```  
CODEPOINT("Mountain Bike")  
```  
  
 Este exemplo usa uma variável. Se **Name** for Roda Dianteira de Passeio, o resultado de retorno será 84, o ponto de código de Unicode para T.  
  
```  
CODEPOINT(@Name)  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Funções &#40;Expressão do SSIS&#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
