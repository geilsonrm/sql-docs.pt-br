---
title: Objeto de conexão (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Connection
helpviewer_keywords:
- Connection object [ADO]
ms.assetid: ef6b1824-5b12-43db-89d7-8f3d13896d4d
author: rothja
ms.author: jroth
ms.openlocfilehash: 49a270f143e57c1e093ac94732b67b6424c88607
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760292"
---
# <a name="connection-object-ado"></a>Objeto Connection (ADO)
Representa uma conexão aberta com uma fonte de dados.  
  
## <a name="remarks"></a>Comentários  
 Um objeto de **conexão** representa uma sessão exclusiva com uma fonte de dados. Em um sistema de banco de dados cliente/servidor, pode ser equivalente a uma conexão de rede real com o servidor. Dependendo da funcionalidade suportada pelo provedor, algumas coleções, métodos ou propriedades de um objeto de **conexão** podem não estar disponíveis.  
  
 Com as coleções, métodos e propriedades de um objeto de **conexão** , você pode fazer o seguinte:  
  
-   Configure a conexão antes de abri-la com as propriedades [ConnectionString](../../../ado/reference/ado-api/connectionstring-property-ado.md), [connectionTimeout](../../../ado/reference/ado-api/connectiontimeout-property-ado.md)e [Mode](../../../ado/reference/ado-api/mode-property-ado.md) . **ConnectionString** é a propriedade padrão do objeto **Connection** .  
  
-   Defina a propriedade [CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md) como Client para invocar o [serviço de cursor da Microsoft para OLE DB](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md), que oferece suporte a atualizações em lotes.  
  
-   Defina o banco de dados padrão para a conexão com a propriedade [DefaultDatabase](../../../ado/reference/ado-api/defaultdatabase-property.md) .  
  
-   Defina o nível de isolamento para as transações abertas na conexão com a propriedade [IsolationLevel](../../../ado/reference/ado-api/isolationlevel-property.md) .  
  
-   Especifique um provedor de OLE DB com a propriedade do [provedor](../../../ado/reference/ado-api/provider-property-ado.md) .  
  
-   Estabelecer, e posteriormente, interromper, a conexão física com a fonte de dados com os métodos [Open](../../../ado/reference/ado-api/open-method-ado-connection.md) e [Close](../../../ado/reference/ado-api/close-method-ado.md) .  
  
-   Execute um comando na conexão com o método [Execute](../../../ado/reference/ado-api/execute-method-ado-connection.md) e configure a execução com a propriedade [CommandTimeout](../../../ado/reference/ado-api/commandtimeout-property-ado.md) .  
  
    > [!NOTE]
    >  Para executar uma consulta sem usar um objeto Command, passe uma cadeia de caracteres de consulta para o método **Execute** de um objeto **Connection** . No entanto, um objeto de [comando](../../../ado/reference/ado-api/command-object-ado.md) é necessário quando você deseja manter o texto do comando e executá-lo novamente, ou usar parâmetros de consulta.  
  
-   Gerencie transações na conexão aberta, incluindo transações aninhadas, se o provedor oferecer suporte a elas, com os métodos [BeginTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md), [CommitTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md)e [RollbackTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) e a propriedade [Attributes](../../../ado/reference/ado-api/attributes-property-ado.md) .  
  
-   Examine os erros retornados da fonte de dados com a coleção de [erros](../../../ado/reference/ado-api/errors-collection-ado.md) .  
  
-   Leia a versão da implementação do ADO usada com a propriedade [version](../../../ado/reference/ado-api/version-property-ado.md) .  
  
-   Obtenha informações de esquema sobre seu banco de dados com o método [OpenSchema](../../../ado/reference/ado-api/openschema-method.md) .  
  
 Você pode criar objetos de **conexão** independentemente de qualquer outro objeto definido anteriormente.  
  
 Você pode executar comandos nomeados ou procedimentos armazenados como se fossem métodos nativos em um objeto de **conexão** , como mostrado na próxima seção. Quando um comando nomeado tem o mesmo nome que um procedimento armazenado, invocar a "chamada de método nativo" em um objeto de **conexão** sempre executa o comando nomeado em vez do procedimento Store.  
  
> [!NOTE]
>  Não use esse recurso (chamando um comando nomeado ou um procedimento armazenado como se fosse um método nativo no objeto de **conexão** ) em um aplicativo do Microsoft® .NET Framework, pois a implementação subjacente do recurso está em conflito com a maneira como o .NET Framework interopera com com.  
  
## <a name="execute-a-command-as-a-native-method-of-a-connection-object"></a>Executar um comando como um método nativo de um objeto de conexão  
 Para executar um comando, dê um nome ao comando usando a propriedade [nome](../../../ado/reference/ado-api/name-property-ado.md) do objeto de **comando** . Defina a propriedade **ActiveConnection** do objeto de **comando** para a conexão. Em seguida, emita uma instrução em que o nome do comando seja usado como se fosse um método no objeto de **conexão** , seguido por qualquer parâmetro e um objeto **Recordset** se qualquer linha for retornada. Defina as propriedades do **conjunto de registros** para personalizar o **conjunto de registros**resultante. Por exemplo:  
  
```  
Dim cnn As New ADODB.Connection  
Dim cmd As New ADODB.Command  
Dim rst As New ADODB.Recordset  
...  
cnn.Open "..."  
cmd.Name = "yourCommandName"  
cmd.ActiveConnection = cnn  
...  
'Your command name, any parameters, and an optional Recordset.  
cnn. "parameter", rst  
```  
  
## <a name="execute-a-stored-procedure-as-a-native-method-of-a-connection-object"></a>Executar um procedimento armazenado como um método nativo de um objeto de conexão  
 Para executar um procedimento armazenado, emita uma instrução em que o nome do procedimento armazenado é usado como se fosse um método no objeto de **conexão** , seguido por qualquer parâmetro. O ADO fará uma "melhor adivinhação" dos tipos de parâmetro. Por exemplo:  
  
```  
Dim cnn As New ADODB.Connection  
...  
'Your stored procedure name and any parameters.  
cnn. "parameter"  
```  
  
 O objeto de **conexão** é seguro para scripts.  
  
 Esta seção contém o tópico a seguir.  
  
-   [Propriedades, métodos e eventos do objeto Connection](../../../ado/reference/ado-api/connection-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Objeto Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)   
 [Coleta de erros (ADO)](../../../ado/reference/ado-api/errors-collection-ado.md)   
 [Coleção Properties (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)   
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)   
 [Apêndice A: Provedores](../../../ado/guide/appendixes/appendix-a-providers.md)
