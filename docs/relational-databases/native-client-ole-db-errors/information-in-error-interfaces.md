---
title: Informações em interfaces de erro | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 1c0ef8694db1d2f5feb4a994fa2fb557a9a7b187
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87247941"
---
# <a name="information-in-ole-db-defined-error-interfaces"></a>Informações em interfaces de erro definidas pelo OLE DB
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo relata algumas informações de erro e status nas interfaces de erro definidas pelo OLE DB **IErrorInfo**, **IErrorRecords**e **ISQLErrorInfo**.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte às funções membro **IErrorInfo** da seguinte maneira.  
  
|Função de membro|Descrição|  
|---------------------|-----------------|  
|**GetDescription**|Cadeia de caracteres de mensagem de erro descritiva.|  
|**GetGUID**|GUID da interface que definiu o erro.|  
|**GetHelpContext**|Não há suporte. Sempre retorna zero.|  
|**GetHelpFile**|Sem suporte. Sempre retorna NULL.|  
|**GetSource**|Cadeia de caracteres "Microsoft SQL Server Native Client".|  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo oferece suporte a funções de membro **IErrorRecords** disponíveis para o consumidor da seguinte maneira.  
  
|Função de membro|Descrição|  
|---------------------|-----------------|  
|**GetBasicErrorInfo**|Preenche uma estrutura ERRORINFO com informações básica sobre um erro. Uma estrutura ERRORINFO contém membros que identificam o valor de retorno HRESULT para o erro e o provedor e interface aos quais o erro se aplica.|  
|**GetCustomErrorObject**|Retorna uma referência em interfaces **ISQLErrorInfo** e [ISQLServerErrorInfo](https://msdn.microsoft.com/library/a8323b5c-686a-4235-a8d2-bda43617b3a1).|  
|**GetErrorInfo**|Retorna uma referência em uma interface **IErrorInfo**.|  
|**GetErrorParameters**|O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo não retorna parâmetros para o consumidor por meio de **geterroparameters**.|  
|**GetRecordCount**|Contagem de registros de erro disponível.|  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo oferece suporte aos parâmetros **ISQLErrorInfo:: GetSQLInfo** da seguinte maneira.  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|*pbstrSQLState*|Retorna um valor SQLSTATE para o erro. São definidos valores SQLSTATE nas especificações SQL-92, ODBC ISO SQL e de API. Nem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB nativo não definiu valores SQLSTATE específicos de implementação.|  
|*plNativeError*|Retorna o número do erro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de **master.dbo.sysmessages** quando disponível. Os erros nativos estão disponíveis após uma tentativa bem-sucedida de inicializar uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonte de dados de provedor de OLE DB de cliente nativo. Antes da tentativa, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo sempre retorna zero.|  
  
## <a name="see-also"></a>Consulte Também  
 [Erros](../../relational-databases/native-client-ole-db-errors/errors.md)  
  
  
