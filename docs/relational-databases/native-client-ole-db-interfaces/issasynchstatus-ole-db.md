---
title: ISSAsynchStatus (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apiname:
- ISSAsynchStatus (OLE DB)
apitype: COM
helpviewer_keywords:
- ISSAsynchStatus interface
ms.assetid: c643f09f-9ccc-4d8b-9243-3cde86c2bd46
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 8d5b52a2940f2db4a4128fa9a73acdc2f871c174
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "86005377"
---
# <a name="issasynchstatus-ole-db"></a>ISSAsynchStatus (OLE DB)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  **ISSAsynchStatus** expõe o suporte a operações assíncronas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Esta é uma interface opcional herdada da interface OLE DB central **IDBAsynchStatus**. Além dos métodos **Abort** e **GetStatus** herdados de **IDBAsynchStatus**, **ISSAsynchStatus** fornece um novo método usado para aguardar até que uma operação assíncrona tenha sido concluída ou um tempo limite tenha sido atingido.  
  
|Método|Descrição|  
|------------|-----------------|  
|[ISSAsynchStatus::Abort &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/issasynchstatus-abort-ole-db.md)|Cancela uma operação que está sendo executada de forma assíncrona.|  
|[ISSAsynchStatus::GetStatus &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/issasynchstatus-getstatus-ole-db.md)|Retorna o status de uma operação que está sendo executada de forma assíncrona.|  
|[ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-interfaces/issasynchstatus-waitforasynchcompletion-ole-db.md)|Aguarda até que a operação com execução assíncrona seja concluída ou um tempo limite seja atingido.|  
  
## <a name="remarks"></a>Comentários  
 A implementação de **ISSAsynchStatus** do método **ISSAsynchStatus::GetStatus** é a mesma do método **IDBAsynchStatus::GetStatus** , com exceção de que, se a inicialização de um objeto de fonte de dados for anulada, E_UNEXPECTED será retornado, em vez de DB_E_CANCELED (apesar de que **ISSAsynchStatus::WaitForAsynchCompletion** retorna DB_E_CANCELED). Isso ocorre porque o objeto de fonte de dados não é deixado no estado normal após uma operação de anulação, para que possa haver outras tentativas de operações de inicialização.  
  
 Os métodos a seguir suportam o uso da execução assíncrona no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
-   **ICommand::Execute**  
  
-   **IOpenRowset::OpenRowset**  
  
-   **IMultipleResults::GetResult**  
  
## <a name="see-also"></a>Consulte Também  
 [Interfaces &#40;OLE DB&#41;](https://msdn.microsoft.com/library/34c33364-8538-45db-ae41-5654481cda93)   
 [Executando operações assíncronas](../../relational-databases/native-client/features/performing-asynchronous-operations.md)  
  
  
