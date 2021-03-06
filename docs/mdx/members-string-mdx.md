---
title: Membros (cadeia de caracteres) (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 05df2d0a846af30d46e702c1d5489945d57c9115
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "68001497"
---
# <a name="members-string-mdx"></a>Membros (cadeia de caracteres) (MDX)


  Retorna um membro especificado por uma expressão de cadeia de caracteres.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Members(Member_Name)   
```  
  
## <a name="arguments"></a>Argumentos  
 *Member_Name*  
 Uma expressão de cadeia de caracteres válida que especifica um nome de membro.  
  
## <a name="remarks"></a>Comentários  
 A função **Members (cadeia de caracteres)** retorna um único membro cujo nome é especificado. Normalmente, você usa a função **Members (cadeia de caracteres)** com funções externas, fornecendo à função **Members (String)** uma cadeia de caracteres que identifica um membro e a função **Members (String)** retorna o valor para esse membro especificado.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir usa a função **Members (cadeia de caracteres)** para converter a cadeia de caracteres especificada em um membro válido e, em seguida, retorna a medida padrão para o membro especificado na cadeia de caracteres. A cadeia de caracteres especificada está entre aspas simples. A medida padrão é a medida Valor das Vendas do Revendedor.  
  
```  
SELECT Members ('[Geography].[Geography].[Country].&[United States] ') ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Referência da Função MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
