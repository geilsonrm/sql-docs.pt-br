---
title: MSSQLSERVER_9003 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d756a2d0c08f6ec7261a88243b23b526ecd27a57
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85636555"
---
# <a name="mssqlserver_9003"></a>MSSQLSERVER_9003
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Detalhes  
  
| Atributo | Valor |  
| :-------- | :---- |  
|Nome do Produto|SQL Server|  
|ID do evento|9003|  
|Origem do Evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|LOG_INVALID_LSN|  
|Texto da mensagem|O número de exames do log %S_LSN passado para o exame no banco de dados '%.*ls' não é válido. Esse erro pode indicar danos nos dados ou que o arquivo de log (.ldf) não corresponde ao arquivo de dados (.mdf). Se esse erro ocorreu durante a replicação, crie a publicação novamente. Caso contrário, se o problema resultar em uma falha durante a inicialização, restaure de um backup.|  
  
## <a name="explanation"></a>Explicação  
Um componente passou um número de sequência de log inválido ao gerenciador de log do banco de dados. Isso pode causar replicação, corrompimento ou uma inconsistência entre o arquivo de dados primário e o log.  
  
## <a name="user-action"></a>Ação do usuário  
Se ele ocorreu durante replicação, recrie a publicação. Caso contrário, faça uma restauração a partir do backup.  
  
