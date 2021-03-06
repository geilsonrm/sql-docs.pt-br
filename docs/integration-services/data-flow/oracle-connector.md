---
title: Microsoft Connector para Oracle | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2019
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1ef8ccdfc30c772548cff4caa816ef1a582c8823
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86913792"
---
# <a name="microsoft-connector-for-oracle"></a>Microsoft Connector para Oracle

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]

O Microsoft Connector para Oracle permite a capacidade de exportar dados e carregar dados na fonte de dados do Oracle em um pacote SSIS.

## <a name="version-support"></a>Suporte à versão

Os seguintes produtos do Microsoft SQL Server são suportados pelo Microsoft Connector para Oracle:

- Desde o SQL Server 2019 CU1
- SSDT (SQL Server Data Tools) 15.9.3 ou posterior para Visual Studio 2017
- Microsoft SSDT (SQL Server Data Tools) para Visual Studio 2019

As seguintes versões do Oracle Database de fontes de dados têm suporte:

- Oracle 10.x
- Oracle 11.x
- Oracle 12c
- Oracle 18c (sem o suporte à Autenticação do Windows)
- Oracle 19c (sem o suporte à Autenticação do Windows)

O Oracle Database tem suporte em todos os sistemas operacionais e plataformas.
> [!NOTE]
>
> O cliente Oracle não é necessário para o Microsoft Connector para banco de dados Oracle no SQL Server 2019.

## <a name="installation"></a>Instalação

Para instalar o conector para o banco de dados Oracle, baixe e execute o instalador da [última versão do Microsoft Connector para Oracle](https://www.microsoft.com/download/details.aspx?id=58228). Em seguida, siga as instruções no assistente de instalação.

Depois de instalar o Conector, reinicie o SQL Server Integration Services para verificar se a origem e o destino Oracle podem funcionar corretamente.

Para executar o pacote SSIS com o direcionamento do SQL Server 2017 e anterior, além do **Microsoft Connector para Oracle**, você precisará instalar o **cliente Oracle** e o **Microsoft Connector para Oracle da Attunity** com a versão correspondente usando os links abaixo:

- [SQL Server 2017: Microsoft Connector versão 5.0 para Oracle da Attunity](https://www.microsoft.com/download/details.aspx?id=55179)
- [SQL Server 2016: Microsoft Connector versão 4.0 para Oracle da Attunity](https://www.microsoft.com/download/details.aspx?id=52950)
- [SQL Server 2014: Microsoft Connector versão 3.0 para Oracle da Attunity](https://www.microsoft.com/download/details.aspx?id=44582)
- [SQL Server 2012: Microsoft Connector versão 2.0 para Oracle da Attunity](https://www.microsoft.com/download/details.aspx?id=29283)

## <a name="uninstallation"></a>Desinstalação

Execute o assistente de desinstalação para remover o Microsoft Connector para banco de dados Oracle do SQL Server.

## <a name="next-steps"></a>Próximas etapas

- Configurar o [Gerenciador de Conexões do Oracle](oracle-connection-manager.md).
- Configurar a [Origem do Oracle](oracle-source.md).
- Configurar o [Destino Oracle](oracle-destination.md).
- Caso tenha dúvidas, visite a [TechCommunity](https://aka.ms/AA5u35j).
