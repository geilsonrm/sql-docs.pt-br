---
title: FORMA (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 4d5d93d4236b3cf86719c416ba87517401e4b4f5
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "86970286"
---
# <a name="ltsource-data-querygt---shape"></a>&lt;consulta de dados &gt; de origem-forma
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Combina consultas de várias fontes de dados em uma tabela hierárquica única (ou seja, uma tabela com tabelas aninhadas), que se torna a tabela de caso do modelo de mineração.  
  
 A sintaxe completa do comando **forma** é documentada no [!INCLUDE[msCoName](../includes/msconame-md.md)] SDK (Software Development Kit) do MDAC (Data Access Components).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
SHAPE {<primary query>}  
APPEND ({ <child table query> }   
     RELATE <primary column> TO <child column>)   
          AS <column table name>  
[  
     ({ <child table query> }   
     RELATE <primary column> TO <child column>)   
          AS < column table name>  
...  
]       
```  
  
## <a name="arguments"></a>Argumentos  
 *consulta principal*  
 Consulta que retorna a tabela pai.  
  
 *consulta de tabela filho*  
 Consulta que retorna a tabela aninhada.  
  
 *coluna primária*  
 Coluna da tabela pai para identificar linhas filho no resultado de uma consulta de tabela filho.  
  
 *coluna filho*  
 A coluna na tabela filho para identificar a linha pai do resultado de uma consulta primária.  
  
 *nome da tabela de colunas*  
 Nome de coluna recentemente adicionada à tabela pai da tabela aninhada.  
  
## <a name="remarks"></a>Comentários  
 É preciso classificar as consultas pela coluna que relaciona a tabela pai à tabela filho.  
  
## <a name="examples"></a>Exemplos  
 Você pode usar o exemplo a seguir em uma instrução [INSERT INTO &#40;DMX&#41;](../dmx/insert-into-dmx.md) para treinar um modelo que contém uma tabela aninhada. As duas tabelas dentro da instrução **Shape** estão relacionadas por meio da coluna **OrderNumber** .  
  
```  
SHAPE {  
    OPENQUERY([Adventure Works DW Multidimensional 2012],'SELECT OrderNumber  
    FROM vAssocSeqOrders ORDER BY OrderNumber')  
} APPEND (  
    {OPENQUERY([Adventure Works DW Multidimensional 2012],'SELECT OrderNumber, model FROM   
    dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')}  
  RELATE OrderNumber to OrderNumber)   
```  
  
## <a name="see-also"></a>Consulte Também  
 [&#62;de consulta de dados de origem&#60;](../dmx/source-data-query.md)   
 [&#40;&#41; instruções de definição de dados DMX de extensões de mineração de dados](../dmx/dmx-statements-data-definition.md)   
 [&#40;instruções de manipulação de dados do DMX&#41; extensões do Data Mining](../dmx/dmx-statements-data-manipulation.md)   
 [Referência de instruções de DMX &#40extensões de Mineração de Dados&#41;](../dmx/data-mining-extensions-dmx-statements.md)  
  
  
