---
title: Criando perfil de desempenho do driver ODBC
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0e6d7aed-28d2-419e-be6a-f60d3729bfd0
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 72e207210d4b731ad278c552861037ed7516f6f6
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "85998490"
---
# <a name="profiling-odbc-driver-performance-odbc"></a>Criar perfil de desempenho do driver ODBC (ODBC)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tem duas opções específicas do driver para a criação de perfil de desempenho do driver.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC pode registrar as estatísticas de desempenho no arquivo. O arquivo de log é um arquivo delimitado por tabulação que pode ser analisado em qualquer planilha com suporte para arquivos delimitados por tabulação, como o Microsoft Excel.  
  
 O driver também pode registrar consultas de longa execução (consultas que não obtêm uma resposta do servidor em um intervalo especificado de tempo). Essas consultas podem ser analisadas depois pelos programadores e pelos administradores de banco de dados.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Dados de desempenho de driver de perfil &#40;&#41;ODBC](../../relational-databases/native-client-odbc-how-to/profiling-odbc-driver-performance-data.md)  
  
-   [Consultas de execução longa do log &#40;&#41;ODBC](../../relational-databases/native-client-odbc-how-to/profiling-odbc-driver-performance-data-log-long-running-queries.md)  
  
## <a name="see-also"></a>Consulte Também  
 [Tópicos de instruções sobre ODBC](../../relational-databases/native-client-odbc-how-to/odbc-how-to-topics.md)  
  
  
