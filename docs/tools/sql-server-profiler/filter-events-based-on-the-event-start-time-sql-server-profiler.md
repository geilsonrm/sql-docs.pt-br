---
title: Filtrar eventos com base na hora de início do evento
titleSuffix: SQL Server Profiler
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
ms.assetid: e965579e-d006-41a3-89ec-cfd5398c67d2
author: markingmyname
ms.author: maghan
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.openlocfilehash: afdf2b5058e03e4539c46faa30fae1f7a2d6c98a
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2020
ms.locfileid: "75307239"
---
# <a name="filter-events-based-on-the-event-start-time-sql-server-profiler"></a>Filtrar eventos com base na hora de início do evento (SQL Server Profiler)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

Este tópico descreve como filtrar eventos de rastreamento de acordo com a hora de início do evento, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].  
  
### <a name="to-filter-an-event-based-on-the-event-start-time"></a>Para filtrar eventos com base na hora de início do evento  
  
1.  No menu **Arquivo** , clique em **Novo Rastreamento**e conecte-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
     A caixa de diálogo **Propriedades do Rastreamento**é exibida.  
  
    > [!NOTE]  
    >  Se a opção **Iniciar rastreamento imediatamente após estabelecer a conexão**estiver marcada, a caixa de diálogo **Propriedades do Rastreamento**não será exibida e o rastreamento será iniciado. Para desabilitar essa configuração, no menu **Ferramentas**, clique em **Opções**e desmarque a caixa de seleção **Iniciar rastreamento imediatamente após estabelecer a conexão** .  
  
2.  Na caixa **Nome do rastreamento** , digite um nome para o rastreamento.  
  
3.  Na lista de nomes **Usar o modelo**, selecione um modelo de rastreamento.  
  
4.  Opcionalmente, especifique um destino para os resultados do rastreamento.  
  
5.  Na guia **Seleção de Eventos**, clique no título de coluna **StartTime** . Você também pode clicar com o botão direito do mouse no título de coluna e clicar em **Editar Filtro de Coluna** para iniciar a caixa de diálogo **Editar Filtro** .  
  
6.  Expanda **Maior que** ou **Menor que**e insira um valor **datetime** no campo que aparece abaixo do operador de comparação.  
  
## <a name="see-also"></a>Consulte Também  
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
