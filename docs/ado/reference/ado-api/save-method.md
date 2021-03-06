---
title: Salvar método | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Recordset::Save
- _Recordset::raw_Save
helpviewer_keywords:
- Save method [ADO]
ms.assetid: ed3d9678-5c28-4e61-8bb3-7dfb66d99cf5
author: rothja
ms.author: jroth
ms.openlocfilehash: db4b5d86c59e35ac3a7aa66684115668d19ead42
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87243197"
---
# <a name="save-method"></a>Método Save
Salva o [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) em um objeto de arquivo ou [fluxo](../../../ado/reference/ado-api/stream-object-ado.md) .  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
recordset.Save Destination, PersistFormat  
```  
  
#### <a name="parameters"></a>parâmetros  
 *Destino*  
 Opcional. Uma **variante** que representa o nome completo do caminho do arquivo em que o **conjunto de registros** deve ser salvo ou uma referência a um objeto de **fluxo** .  
  
 *PersistFormat*  
 Opcional. Um valor [PersistFormatEnum](../../../ado/reference/ado-api/persistformatenum.md) que especifica o formato no qual o **conjunto de registros** deve ser salvo (XML ou ADTG). O valor padrão é **adPersistADTG**.  
  
## <a name="remarks"></a>Comentários  
 O método [Save Method](../../../ado/reference/ado-api/save-method.md) só pode ser invocado em um **conjunto de registros**aberto. Use o método [Open do método (ADO Recordset)](../../../ado/reference/ado-api/open-method-ado-recordset.md) para restaurar posteriormente o **conjunto de registros** do *destino*.  
  
 Se a propriedade de [propriedade de filtro](../../../ado/reference/ado-api/filter-property.md) estiver em vigor para o **conjunto de registros**, somente as linhas acessíveis no filtro serão salvas. Se o **conjunto de registros** for hierárquico, o **conjunto de registros** filho atual e seus filhos serão salvos, incluindo o **conjunto de registros**pai. Se o método Save de um **conjunto de registros** filho for chamado, o filho e todos os seus filhos serão salvos, mas o pai não será.  
  
 Na primeira vez que você salvar o **conjunto de registros**, é opcional especificar *destino*. Se você omitir o *destino*, um novo arquivo será criado com um nome definido como o valor da propriedade Source do **conjunto de registros**.  
  
 Omita o *destino* quando você chamar o **salvamento** depois do primeiro salvamento ou se ocorrer um erro de tempo de execução. Se, posteriormente, você chamar **Save** com um novo *destino*, o **conjunto de registros** será salvo no novo destino. No entanto, o novo destino e o destino original serão abertos.  
  
 **Salvar** não fecha o **conjunto de registros** ou *destino*, para que você possa continuar a trabalhar com o **conjunto de registros** e salvar suas alterações mais recentes. O *destino* permanece aberto até que o **conjunto de registros** seja fechado.  
  
 Por motivos de segurança, o método **Save** permite apenas o uso de configurações de segurança baixas e personalizadas de um script executado pelo Microsoft Internet Explorer.  
  
 Se o método **Save** for chamado enquanto uma operação de busca, execução ou atualização do **conjunto de registros** assíncrono estiver em andamento, o **salvamento** esperará até que a operação assíncrona seja concluída.  
  
 Os registros são salvos a partir da primeira linha do **conjunto de registros**. Quando o método **Save** é concluído, a posição da linha atual é movida para a primeira linha do **conjunto de registros**.  
  
 Para obter melhores resultados, defina a propriedade [CursorLocation (ADO)](../../../ado/reference/ado-api/cursorlocation-property-ado.md) como **adUseClient** com **salvar**. Se seu provedor não oferecer suporte a toda a funcionalidade necessária para salvar objetos do **conjunto de registros** , o serviço de cursor fornecerá essa funcionalidade.  
  
 Quando um **conjunto de registros** é persistido com a propriedade **CursorLocation** definida como **adUseServer**, o recurso de atualização para o **conjunto de registros** é limitado. Normalmente, apenas atualizações de tabela única, inserções e exclusões são permitidas (dependendo da funcionalidade do provedor). O método de [resincronização](../../../ado/reference/ado-api/resync-method.md) também está indisponível nessa configuração.  
  
> [!NOTE]
>  Não há suporte para salvar um **conjunto de registros** com **campos** do tipo **adVariant**, **adIDispatch**ou **adIUnknown** no ADO e isso pode causar resultados imprevisíveis.  
  
 Somente filtros na forma de cadeias de caracteres de critérios (por exemplo, DataDoPedido > ' 12/31/1999 ') afetam o conteúdo de um **conjunto de registros**persistente. Os filtros criados com uma matriz de **indicadores** ou usando um valor de [FilterGroupEnum](../../../ado/reference/ado-api/filtergroupenum.md) não afetarão o conteúdo do **conjunto de registros**persistente. Essas regras se aplicam ao **conjunto de registros**s criado com cursores do lado do cliente ou do servidor.  
  
 Como o parâmetro de *destino* pode aceitar qualquer objeto que dê suporte à interface OLE DB IStream, você pode salvar um **conjunto de registros** diretamente no objeto de resposta ASP. Para obter mais detalhes, consulte o **cenário de persistência do conjunto de registros XML**.  
  
 Você também pode salvar um **conjunto de registros** em formato XML em uma instância de um objeto dom do MSXML, como é mostrado no código de Visual Basic a seguir:  
  
```  
Dim xDOM As New MSXML.DOMDocument  
Dim rsXML As New ADODB.Recordset  
Dim sSQL As String, sConn As String  
  
sSQL = "SELECT customerid, companyname, contactname FROM customers"  
sConn="Provider=Microsoft.Jet.OLEDB.4.0;Data Source=Northwind.mdb"  
rsXML.Open sSQL, sConn  
rsXML.Save xDOM, adPersistXML   'Save Recordset directly into a DOM tree.  
...  
```  
  
> [!NOTE]
>  Duas limitações se aplicam ao salvar conjuntos de registros hierárquicos (formas de dados) em formato XML. Você não poderá salvar em XML se o **conjunto de registros** hierárquico contiver atualizações pendentes e não for possível salvar um **conjunto de registros**hierárquicos parametrizados.  
  
 Um **conjunto de registros** salvo em formato XML é salvo usando o formato UTF-8. Quando esse arquivo é carregado em um fluxo ADO, o objeto Stream não tentará abrir um conjunto de **registros** a partir do fluxo, a menos que a propriedade charset do fluxo seja definida como o valor apropriado para o formato UTF-8.  
  
## <a name="applies-to"></a>Aplica-se A  

:::row:::
    :::column:::
        [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
    :::column-end:::
    :::column:::
        [Objeto Stream (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>Consulte Também  
 [Exemplo dos métodos Save e Open (VB)](../../../ado/reference/ado-api/save-and-open-methods-example-vb.md)   
 [Exemplo dos métodos Save e Open (VC + +)](../../../ado/reference/ado-api/save-and-open-methods-example-vc.md)   
 [Método Open (conjunto de registros ADO)](../../../ado/reference/ado-api/open-method-ado-recordset.md)   
 [Método Open (fluxo ADO)](../../../ado/reference/ado-api/open-method-ado-stream.md)   
 [Método SaveToFile](../../../ado/reference/ado-api/savetofile-method.md)
