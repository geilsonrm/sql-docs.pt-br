---
title: SQL Server, objeto ExecStatistics | Microsoft Docs
description: Saiba mais sobre o objeto SQLServer:ExecStatistics, que fornece contadores para monitorar diversas execuções.
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQLServer:ExecStatistics
- ExecStatistics object
ms.assetid: 4f8557a8-345f-4622-a8a5-763a0388ad94
author: julieMSFT
ms.author: jrasnick
ms.openlocfilehash: 1c6cf9cb90a6b19e3472e7d0fb41475b9deb47f6
ms.sourcegitcommit: 9470c4d1fc8d2d9d08525c4f811282999d765e6e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86458346"
---
# <a name="sql-server-execstatistics-object"></a>SQL Server, objeto ExecStatistics
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  O objeto **SQLServer:ExecStatistics** do Microsoft SQL Server oferece contadores para o monitoramento de diversas execuções.  
  
 Esta tabela descreve os contadores **Exec Statistics** do SQL Server.  
  
|Contadores Exec Statistics do SQL Server|Descrição|  
|-----------------------------------------|-----------------|  
|**Consulta Distribuída**|Estatísticas referentes à execução de consultas distribuídas.|  
|**Chamadas DTC**|Estatísticas referentes à execução de chamadas DTC.|  
|**Procedimentos Estendidos**|Estatísticas referentes à execução de procedimentos estendidos.|  
|**Chamadas OLEDB**|Estatísticas referentes à execução de chamadas OLEDB.|  
  
 Cada contador no objeto contém as seguintes instâncias:  
  
|Item|Descrição|  
|----------|-----------------|  
|**Tempo médio de execução (ms)**|Tempo médio de execução do tipo de execução selecionado.|  
|**Tempo de execução cumulativo (ms) por segundo**|Tempo de execução agregado, por segundo, do tipo de execução selecionado.|  
|**Execuções em andamento**|Número de execuções em andamento do tipo de execução selecionado.|  
|**Execuções iniciadas por segundo**|Número de execuções iniciadas por segundo, do tipo de execução selecionado.|  
  
## <a name="see-also"></a>Consulte Também  
 [Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
