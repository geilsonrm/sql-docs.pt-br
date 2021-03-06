---
title: Utilitário rsconfig | Microsoft Docs
ms.date: 03/20/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: tools
ms.topic: conceptual
helpviewer_keywords:
- connections [Reporting Services], configuring
- rsconfig utility
- report servers [Reporting Services], connections
- command prompt utilities [Reporting Services]
- command prompt utilities [SQL Server], rsconfig
ms.assetid: 84e45a2f-3ca6-4c16-8259-c15ff49d72ad
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7ad41870ac9bcb162e792dc6abd8ca21ceeeb3f2
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2020
ms.locfileid: "77082182"
---
# <a name="rsconfig-utility-ssrs"></a>Utilitário rsconfig (SSRS)
  O utilitário **rsconfig.exe** criptografa e armazena conexão e valores de conta no arquivo RSReportServer.config. Valores criptografados incluem informações de conexão de banco de dados do servidor de relatório e valores de conta usados para processamento de relatório autônomo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
rsconfig {-?}  
{-cconnection}  
{-eunattendedaccount}  
{-mcomputername}  
{-iinstancename}  
{-sservername}  
{-ddatabasename}  
{-aauthmethod}  
{-uusername}  
{-ppassword}  
{-ttrace}  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Termo|Opcional/Necessário|Definição|  
|----------|------------------------|----------------|  
|**-?**|Opcional.|Exibe a sintaxe de argumentos Rsconfig.exe.|  
|**-c**|Obrigatório se **-e** não for usado.|Especifica a cadeia de conexão, credenciais e valores de fonte de dados usados para conectar um servidor de relatório ao banco de dados do servidor de relatório.<br /><br /> Esse argumento não exige um valor. Porém, devem ser especificados argumentos adicionais com ele para fornecer todos os valores de conexão exigidos.<br /><br /> Os argumentos que você pode especificar com **-c** incluem **-m**, **-s**, **-i**, **-d**, **-a**, **-u**, **-p**e **-t**.|  
|**-e**|Obrigatório se o argumento **-c** não for usado.|Especifica a conta de execução autônoma do relatório.<br /><br /> Esse argumento não exige um valor. Porém, você deve incluir argumentos adicionais na linha de comando para especificar os valores criptografados no arquivo de configuração.<br /><br /> Os argumentos que você pode especificar com **-e** incluem **-u** e **-p**. Você também pode definir **-t**.|  
|**-m** *computername*|Obrigatório se você estiver configurando uma instância de servidor de relatório remota.|Especifica o nome do computador que está hospedando o servidor de relatório. Se esse argumento for omitido, o padrão será **localhost**.|  
|**-s** *servername*|Obrigatórios.|Especifica a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados do servidor de relatório.|  
|**-i** *instancename*|Obrigatório se você estiver usando instâncias nomeadas.|Se você usou uma instância nomeada do Reporting Services, esse valor especifica o nome da instância do Reporting Services.|  
|**-d** *databasename*|Obrigatórios.|Especifica o nome do banco de dados do servidor de relatório.|  
|**-a** *authmethod*|Obrigatórios.|Especifica o método de autenticação usado pelo servidor de relatório para se conectar ao banco de dados do servidor de relatório. Os valores válidos são **Windows** ou **SQL** (este argumento não diferencia maiúsculas de minúsculas).<br /><br /> O**Windows** especifica que o servidor de relatório usa a Autenticação do Windows.<br /><br /> O**SQL** especifica que o servidor de relatório usa a Autenticação do SQL Server.|  
|**-u** *[domain\\]username*|Obrigatório com **-e** , opcional com **-c**.|Especifica uma conta de usuário para a conexão de banco de dados do servidor de relatório ou para a conta autônoma.<br /><br /> Para **rsconfig -e**, esse argumento é obrigatório. Deve ser uma conta de usuário do domínio.<br /><br /> Para **rsconfig -c** e **-a SQL**, esse argumento deve especificar um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .<br /><br /> Para **rsconfig -c** e **-a Windows**, este argumento pode especificar um usuário do domínio, uma conta interna ou as credenciais da conta de serviço. Se você estiver especificando uma conta de domínio, defina *domínio* e *nome de usuário* no formato *domínio\nomedeusuário*. Se você estiver usando uma conta interna, esse argumento será opcional. Se você quiser usar credenciais de conta de serviço, omita esse argumento.|  
|**-p** *password*|Obrigatório se **-u** for especificado.|Especifica a senha a ser usada com o argumento *username* . Você poderá definir esse argumento como um valor em branco se a conta não exigir uma senha. Esse valor diferencia maiúsculas de minúsculas em contas de domínio.|  
|**-t**|Opcional.|Produz mensagens de erro para o log de rastreamento. Esse argumento não exige um valor. Para obter mais informações, consulte [Report Server Service Trace Log](../../reporting-services/report-server/report-server-service-trace-log.md).|  
  
## <a name="permissions"></a>Permissões  
 Você deve ser um administrador local no computador que hospeda o servidor de relatório que você está configurando.  
  
## <a name="file-location"></a>Local do arquivo  
 O Rsconfig.exe está localizado em **\Arquivos de Programas\Microsoft SQL Server\110\Tools\Binn**. Você pode executar o utilitário de qualquer pasta em seu sistema de arquivos.  
  
## <a name="remarks"></a>Comentários  
 Rsconfig.exe é usado para dois propósitos:  
  
-   Para modificar a informações de conexão que um servidor de relatório usa para conectar-se a um banco de dados do servidor de relatório.  
  
-   Para configurar uma conta especial que o servidor de relatório usa para fazer logon em um servidor de banco de dados remoto quando outras credenciais não estão disponíveis.  
  
Execute o utilitário **rsconfig** em uma instância local ou remota do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Você não pode usar o utilitário **rsconfig** para descriptografar e exibir valores já definidos.  
  
Antes de executar esse utilitário, o WMI (Instrumentação de Gerenciamento do Windows) deve ser instalado no computador que você está configurando.  
  
## <a name="examples"></a>Exemplos  
 Os exemplos a seguir ilustram as maneiras de usar o **rsconfig**.  
  
#### <a name="specifying-a-domain-user-account"></a>Especificando uma conta de usuário de domínio  
 Este exemplo mostra como configurar um servidor de relatório para usar uma conta de usuário de domínio na conexão com um banco de dados do servidor de relatório local.  
  
```  
rsconfig -c -s <SQLSERVERNAME> -d reportserver -a Windows -u <MYDOMAIN\MYACCOUNT> -p <PASSWORD>  
```  
  
#### <a name="specifying-a-sql-server-database-user-account"></a>Especificando uma conta de usuário do banco de dados do SQL Server  
 Este exemplo mostra como configurar um servidor de relatório para usar o logo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na conexão com um banco de dados do servidor de relatório remoto.  
  
```  
rsconfig -c -m <REMOTECOMPUTERNAME> -s <SQLSERVERNAME> -d reportserver -a SQL -u SA -p <SAPASSWORD>  
```  
  
#### <a name="specifying-a-built-in-account"></a>Especificando uma conta interna  
 Este exemplo mostra como configurar um servidor de relatório para usar uma conta interna na conexão com um banco de dados do servidor de relatório local. Observe que **-u** não é usado. Exemplos de valores de conta interna compatíveis incluem NT AUTHORITY\SYSTEM para Sistema Local e NT AUTHORITY\NETWORKSERVICE para Serviço de Rede (somente [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] ).  
  
```  
rsconfig -c -s <SQLSERVERNAME> -d reportserver -a Windows "NT AUTHORITY\SYSTEM"  
```  
  
#### <a name="specifying-a-service-account"></a>Especificando uma conta de serviço  
 Este exemplo mostra como configurar um servidor de relatório para usar na conta de serviço do Servidor de Relatório do Windows e conta de serviço Web na conexão com um banco de dados do servidor de relatório local. Observe que **-u** não é usado e que nenhuma informação de conta é especificada. Quando valores de conta são eliminados do comando, o utilitário **rsconfig** usa segurança integrada e a conta de serviço na qual cada serviço é executado.  
  
```  
rsconfig -c -s <SQLSERVERNAME> -d reportserver -a Windows  
```  
  
#### <a name="specifying-the-unattended-account-on-a-local-server"></a>Especificando a conta autônoma em um servidor local  
 Este exemplo mostra como configurar a conta usada para execução de relatório autônomo, para relatórios que não passam credenciais para a fonte de dados externa. A conta deve ser uma conta de domínio do Windows. Você não pode especificar um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o nome de usuário e senha. A conta é configurada em uma instância do servidor de relatório local. Mensagens de erro são capturadas nos logs de rastreamento na pasta ReportingServices\LogFiles.  
  
```  
rsconfig -e -u <DOMAIN\ACCOUNT> -p <PASSWORD> -t  
```  
  
#### <a name="specifying-the-unattended-account-on-a-remote-server"></a>Especificando a conta autônoma em um servidor remoto  
 Este exemplo mostra como configurar a conta em uma instância do servidor remoto com a mesma versão de Rsconfig.exe (por exemplo, o servidor de relatório e Rsconfig.exe são a versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2008 R2). Informações de mensagem de erro são capturadas nos logs de rastreamento no servidor remoto.  
  
```  
rsconfig -e -m <REMOTECOMPUTERNAME> -s <SQLSERVERNAME> -u <DOMAIN\ACCOUNT> -p <PASSWORD> -t  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Configurar uma conexão de banco de dados do servidor de relatório &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager.md)   
 [Configurar a conta de execução autônoma &#40;Gerenciador de configurações do SSRS&#41;](../../reporting-services/install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)   
 [Servidor de relatório do Reporting Services &#40;Modo Nativo&#41;](../../reporting-services/report-server/reporting-services-report-server-native-mode.md)   
 [Armazenar dados criptografados do servidor de relatório &#40;Configuration Manager do SSRS&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md)   
 [Arquivos de configuração do Reporting Services](../../reporting-services/report-server/reporting-services-configuration-files.md)   
 [Utilitários de prompt de comando do servidor de relatório &#40;SSRS&#41;](../../reporting-services/tools/report-server-command-prompt-utilities-ssrs.md)   
 [Arquivo de configuração RsReportServer.config](../../reporting-services/report-server/rsreportserver-config-configuration-file.md)  
  
  
