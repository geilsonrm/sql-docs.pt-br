---
title: IsInNode (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 063c436f2e0d76ca891f332f25be385c2f16fdfa
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "86969559"
---
# <a name="isinnode-dmx"></a>IsInNode (DMX)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Indica se o nó especificado contém o caso atual.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
IsInNode(<NodeID>)  
```  
  
## <a name="return-type"></a>Tipo de retorno  
 Um tipo booliano.  
  
## <a name="remarks"></a>Comentários  
 **IsInNode** é usado somente no [&#62; de modelo de seleção de &#60;. CASOS &#40;&#41;DMX](../dmx/select-from-model-cases-dmx.md) e [selecione &#60;modelo&#62;. SAMPLE_CASES &#40;consultas&#41;DMX](../dmx/select-from-model-sample-cases-dmx.md) .  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir retorna todos os casos usados para criar o modelo associado ao nó especificado na função IsInNode.  
  
```  
Select * from [TM Decision Tree].Cases  
WHERE IsInNode('0')  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de função&#41; DMX &#40;extensões de mineração de dados](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Funções &#40;&#41;DMX](../dmx/functions-dmx.md)   
 [Funções de previsão gerais &#40;&#41;DMX](../dmx/general-prediction-functions-dmx.md)  
  
  
