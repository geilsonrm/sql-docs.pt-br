---
title: Microsoft ODBC Driver for SQL Server
description: O Microsoft ODBC Driver for SQL Server fornece conectividade para o SQL Server e o Banco de Dados SQL do Microsoft Azure por meio de APIs ODBC padrão.
ms.custom: ''
ms.date: 05/06/2020
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 9f2ae91b-06af-4c9a-9d24-062df7bc4662
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 42fce5ed05099227cf134b7bd244b7c93e98d501
ms.sourcegitcommit: fb1430aedbb91b55b92f07934e9b9bdfbbd2b0c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82886333"
---
# <a name="microsoft-odbc-driver-for-sql-server"></a>Microsoft ODBC Driver for SQL Server

[!INCLUDE[ODBC_Current_Version](../../includes/odbc-latest-release.md)]

[!INCLUDE[Driver_ODBC_Download](../../includes/driver_odbc_download.md)]

O ODBC é a API de acesso a dados nativo primária para aplicativos escritos em C e C++ para o SQL Server. Há um driver ODBC para a maioria das fontes de dados. Outros idiomas que usam o ODBC incluem COBOL, Perl, PHP e Python. ODBC é amplamente usado em cenários de integração de dados.

O driver ODBC é fornecido com ferramentas como [**sqlcmd**](../../tools/sqlcmd-utility.md) e [**bcp**](../../tools/bcp-utility.md). O utilitário **sqlcmd** permite executar instruções Transact-SQL, procedimentos do sistema e scripts SQL. O utilitário **bcp** copia dados em massa entre uma instância do Microsoft SQL Server e um arquivo de dados no formato especificado pelo usuário. O utilitário **bcp** pode ser usado para importar um grande número de linhas novas em tabelas do SQL Server ou para exportar dados de tabelas para arquivos de dados.  

## <a name="code-example-in-c"></a>Exemplo de código em C++

O exemplo C++ a seguir demonstra como usar as APIs de ODBC para conectar e acessar um banco de dados:

- [Exemplo de código C++ usando o ODBC](../../odbc/reference/sample-odbc-program.md)

## <a name="download"></a>Baixar

- ![Download-DownArrow-Circled](../../ssms/media/download-icon.png)[Para baixar o driver ODBC](download-odbc-driver-for-sql-server.md)

## <a name="documentation"></a>Documentação

### <a name="features"></a>Recursos

- [Provedores de repositórios de chaves personalizados](../../connect/odbc/custom-keystore-providers.md)
- [Classificação de Dados](../../connect/odbc/data-classification.md)
- [Atributos e palavras-chave da cadeia de conexão e DSN](dsn-connection-string-attribute.md)
- [SQL Server Native Client](../../relational-databases/native-client/features/sql-server-native-client-features.md) (os recursos disponíveis também se aplicam, sem OLEDB, para o Driver ODBC para SQL Server)
- [Como usar o Always Encrypted](../../connect/odbc/using-always-encrypted-with-the-odbc-driver.md)
- [Como usar o Azure Active Directory](../../connect/odbc/using-azure-active-directory.md)
- [Como usar a resolução IP de rede transparente](../../connect/odbc/using-transparent-network-ip-resolution.md)
- [Como usar Transações XA](../../connect/odbc/use-xa-with-dtc.md)

### <a name="linux-and-macos"></a>Linux e macOS

- [Como instalar o driver no Linux](../../connect/odbc/linux-mac/installing-the-microsoft-odbc-driver-for-sql-server.md)
- [Como instalar o driver no macOS](../../connect/odbc/linux-mac/install-microsoft-odbc-driver-sql-server-macos.md)
- [Conectando ao SQL Server](../../connect/odbc/linux-mac/connection-string-keywords-and-data-source-names-dsns.md)
- [Conectando-se ao **bcp**](../../connect/odbc/linux-mac/connecting-with-bcp.md)
- [Conectando com **sqlcmd**](../../connect/odbc/linux-mac/connecting-with-sqlcmd.md)
- [Rastreamento de Acesso a Dados](../../connect/odbc/linux-mac/data-access-tracing-with-the-odbc-driver-on-linux.md)
- [Perguntas frequentes](../../connect/odbc/linux-mac/frequently-asked-questions-faq-for-odbc-linux.md)
- [Instalando o Gerenciador de Driver](../../connect/odbc/linux-mac/installing-the-driver-manager.md)
- [Problemas Conhecidos](../../connect/odbc/linux-mac/known-issues-in-this-version-of-the-driver.md)
- [Diretrizes de programação](../../connect/odbc/linux-mac/programming-guidelines.md)
- [Notas de Versão](../../connect/odbc/linux-mac/release-notes-odbc-sql-server-linux-mac.md)
- [Suporte a alta disponibilidade e recuperação de desastre](../../connect/odbc/linux-mac/odbc-driver-on-linux-support-for-high-availability-disaster-recovery.md)
- [Como usar a Autenticação Integrada (Kerberos)](../../connect/odbc/linux-mac/using-integrated-authentication.md)

### <a name="windows"></a>Windows

- [Exemplo de execução assíncrona (método de notificação)](../../connect/odbc/windows/asynchronous-execution-notification-method-sample.md)
- [Resiliência de conexão no driver ODBC do Windows](../../connect/odbc/windows/connection-resiliency-in-the-windows-odbc-driver.md)
- [Pool de conexões com reconhecimento de driver](../../connect/odbc/windows/driver-aware-connection-pooling-in-the-odbc-driver-for-sql-server.md)
- [Recursos e alterações de comportamento](../../connect/odbc/windows/features-of-the-microsoft-odbc-driver-for-sql-server-on-windows.md)
- [Notas sobre a Versão para ODBC para SQL Server no Windows](windows/release-notes-odbc-sql-server-windows.md)
- [Requisitos do sistema, instalação e arquivos de driver](../../connect/odbc/windows/system-requirements-installation-and-driver-files.md)

## <a name="community"></a>Comunidade

- [Blog dos Drivers do SQL Server](https://techcommunity.microsoft.com/t5/SQL-Server/bg-p/SQLServer/label-name/SQLServerDrivers)  
- [SQL Server Data Access Forum](https://social.technet.microsoft.com/Forums/en/sqldataaccess/threads)  
