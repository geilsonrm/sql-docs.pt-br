---
title: Executar um comando | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: ba04931d5bfddd3e61df2a272d085dd6337d9a85
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "86005275"
---
# <a name="executing-a-command"></a>Executando um comando
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Depois de estabelecida a conexão com uma fonte de dados, o consumidor chama o método **IDBCreateSession::CreateSession** para criar uma sessão. A sessão atua como um comando, conjunto de linhas ou fábrica de transação.  
  
 Para trabalhar diretamente com tabelas ou índices individuais, o consumidor solicita a interface **IOpenRowset**. O método **IOpenRowset::OpenRowset** é aberto e retorna um conjunto de linhas que inclui todas as linhas de uma única tabela ou índice base.  
  
 Para executar um comando (como SELECT \* FROM Authors), o consumidor solicita a interface **IDBCreateCommand**. O consumidor pode executar o método **IDBCreateCommand::CreateCommand** para criar um objeto de comando e solicitar a interface **ICommandText**. O método **ICommandText::SetCommandText** é usado para especificar o comando que será executado.  
  
 O comando **Execute** é usado para executar o comando. O comando pode ser qualquer instrução SQL ou nome de procedimento. Nem todos os comandos geram um objeto de conjunto de resultados (conjunto de linhas). Comandos como SELECT * FROM Authors geram um conjunto de resultados.  
  
## <a name="see-also"></a>Consulte Também  
 [Criando um aplicativo provedor OLE DB do SQL Server Native Client](../../relational-databases/native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
