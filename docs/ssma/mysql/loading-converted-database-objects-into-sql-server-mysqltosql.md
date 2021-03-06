---
title: Carregando objetos de banco de dados convertidos em SQL Server (MySQLToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: ac993a6d-0283-4823-8793-6b217677dfa3
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: a6966209300e6959e7ba9cb1afa11eb42b855d82
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2020
ms.locfileid: "67909011"
---
# <a name="loading-converted-database-objects-into-sql-server-mysqltosql"></a>Carregar objetos de banco de dados convertidos no SQL Server (MySQLToSQL)
Depois de converter bancos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dados MySQL no ou SQL Azure, você pode carregar os objetos de banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resultantes no ou SQL Azure. Você pode fazer com que o SSMA crie os objetos, ou pode criar o script dos objetos e executar os scripts por conta própria. Além disso, o SSMA permite que você atualize os metadados de destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o conteúdo real do banco de dados ou SQL Azure.  
  
## <a name="choosing-between-synchronization-and-scripts"></a>Escolhendo entre a sincronização e os scripts  
Se você quiser carregar os objetos de banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] convertidos no ou SQL Azure sem modificação, poderá fazer com que o SSMA crie ou recrie os objetos de banco de dados diretamente. Esse método é rápido e fácil, mas não permite a personalização do código Transact-SQL que define os [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos ou SQL Azure.  
  
Se você quiser modificar o Transact-SQL que é usado para criar objetos ou se quiser mais controle sobre a criação de objetos, use o SSMA para criar scripts. Em seguida, você pode modificar esses scripts, criar cada objeto individualmente e até mesmo usar SQL Server Agent para agendar a criação desses objetos.  
  
## <a name="using-ssma-to-synchronize-objects-with-sql-server"></a>Usando o SSMA para sincronizar objetos com SQL Server  
Para usar o SSMA para criar SQL Server ou SQL Azure objetos de banco de dados, selecione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] os objetos no ou SQL Azure o Gerenciador de metadados e sincronize [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] os objetos com ou SQL Azure, conforme mostrado no procedimento a seguir. Por padrão, se os objetos já existirem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no ou SQL Azure, e se os metadados do SSMA tiverem algumas alterações locais ou atualizações na definição desses objetos, o SSMA alterará as definições de objeto no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou SQL Azure. Você pode alterar o comportamento padrão editando **as configurações do projeto**.  
  
> [!NOTE]  
> Você pode selecionar objetos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de banco de dados existentes ou SQL Azure que não foram convertidos de bancos de dados MySQL. No entanto, esses objetos não serão recriados ou alterados pelo SSMA.  
  
##### <a name="to-synchronize-objects-with-sql-server-or-sql-azure"></a>Para sincronizar objetos com SQL Server ou SQL Azure  
  
1.  No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou SQL Azure Gerenciador de metadados, expanda [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o nó superior ou SQL Azure e, em seguida, expanda **bancos de dados**.  
  
2.  Selecione os objetos a serem processados:  
  
    -   Para sincronizar um banco de dados completo, marque a caixa de seleção ao lado do nome do banco de dados.  
  
    -   Para sincronizar ou omitir objetos individuais ou categorias de objetos, marque ou desmarque a caixa de seleção ao lado do objeto ou da pasta.  
  
3.  Depois de selecionar os objetos a serem processados no SQL Server ou SQL Azure o Gerenciador de metadados, clique com o botão direito do mouse em **bancos**de dados e clique em **sincronizar com o Database**.  
  
    Você também pode sincronizar objetos individuais ou categorias de objetos clicando com o botão direito do mouse no objeto ou em sua pasta pai e clicando em **sincronizar com o banco de dados**.  
  
    Depois disso, o SSMA exibirá a caixa de diálogo **sincronizar com o banco de dados** , onde você poderá ver dois grupos de itens. No lado esquerdo, o SSMA mostra os objetos de banco de dados selecionados representados em uma árvore. No lado direito, você pode ver uma árvore que representa os mesmos objetos em metadados do SSMA. Você pode expandir a árvore clicando no botão à direita ou à esquerda ' + '. A direção da sincronização é mostrada na coluna ação colocada entre as duas árvores.  
  
    Um sinal de ação pode estar nos três seguintes Estados:  
  
    -   Uma seta para a esquerda significa que o conteúdo dos metadados será salvo no banco de dados (o padrão).  
  
    -   Uma seta para a direita significa que o conteúdo do banco de dados substituirá os metadados do SSMA.  
  
    -   Um sinal cruzado significa que nenhuma ação será executada.  
  
    -   Clique no sinal de ação para alterar o estado. A sincronização real será executada quando você clicar no botão **OK** da caixa de diálogo **sincronizar com Banco de dados** .  
  
## <a name="scripting-objects"></a>Objetos de script  
Para salvar [!INCLUDE[tsql](../../includes/tsql-md.md)] as definições dos objetos de banco de dados convertidos ou alterar as definições de objeto e executar scripts por conta própria, você pode salvar as [!INCLUDE[tsql](../../includes/tsql-md.md)] definições de objeto de banco de dados convertido em scripts.  
  
**Para salvar objetos como scripts**  
  
1.  Depois de selecionar os objetos a serem salvos em um script, clique com o botão direito do mouse em **bancos de dados**e clique em **salvar como script**.  
  
    Você também pode criar scripts de objetos individuais ou categorias de objetos clicando com o botão direito do mouse no objeto ou em sua pasta pai e clicando em **salvar como script**.  
  
2.  Na caixa de diálogo **salvar como** , localize a pasta onde você deseja salvar o script, insira um nome de arquivo na caixa **nome do arquivo** e, em [!INCLUDE[clickOK](../../includes/clickok-md.md)] seguida, o SSMA acrescentará a extensão de nome de arquivo. Sql.  
  
### <a name="modifying-scripts"></a>Modificando scripts  
Depois de salvar as definições de objeto SQL Server ou SQL Azure como um script, você pode usar SQL Server Management Studio para modificar o script.  
  
**Para modificar um script**  
  
1.  No menu Management Studio **arquivo** , aponte para **abrir**e clique em **arquivo**.  
  
2.  Na caixa de diálogo abrir, localize e selecione o arquivo de script e clique em **OK**.  
  
3.  Edite o arquivo de script usando o editor de consultas. Para obter mais informações sobre o editor de consultas, consulte "comandos e recursos de conveniência do editor" em Manuais Online do SQL Server.  
  
4.  Para salvar o script, no menu arquivo, selecione **salvar**.  
  
### <a name="running-scripts"></a>Executando scripts  
Você pode executar um script, ou instruções individuais, em SQL Server Management Studio.  
  
**Para executar um script**  
  
1.  No menu SQL Server Management Studio **arquivo** , aponte para **abrir** e clique em **arquivo**.  
  
2.  Na caixa de diálogo abrir, localize e selecione o arquivo de script e clique em **OK**.  
  
3.  Para executar o script completo, pressione a tecla **F5** .  
  
4.  Para executar um conjunto de instruções, selecione as instruções na janela do editor de consultas e pressione a tecla **F5** .  
  
5.  Para obter mais informações sobre como usar o editor de consultas para executar scripts, consulte "SQL Server Management Studio consulta Transact-SQL" em Manuais Online do SQL Server.  
  
6.  Você também pode executar scripts na linha de comando usando o utilitário **sqlcmd** e de SQL Server Agent. Para obter mais informações sobre o **sqlcmd**, consulte "utilitário sqlcmd" em manuais online do SQL Server. Para obter mais informações sobre SQL Server Agent, consulte "automatizando tarefas administrativas (SQL Server Agent)" em Manuais Online do SQL Server.  
  
## <a name="securing-objects-in-sql-server"></a>Protegendo objetos no SQL Server  
Depois de carregar os objetos de banco de dados convertidos em SQL Server, você pode conceder e negar permissões nesses objetos. É uma boa ideia fazer isso antes de migrar dados para SQL Server. Para obter informações sobre como ajudar a proteger objetos no SQL Server, consulte "considerações de segurança para bancos de dados e aplicativos de banco de dados" em Manuais Online do SQL Server.  
  
## <a name="next-step"></a>Próxima etapa  
A próxima etapa no processo de migração é [migrar dados do MySQL para o SQL Server-BD SQL do Azure &#40;MySQLToSQL&#41;](../../ssma/mysql/migrating-mysql-data-into-sql-server-azure-sql-db-mysqltosql.md)  
  
## <a name="see-also"></a>Consulte Também  
[Migrando bancos de dados MySQL para SQL Server-BD SQL do Azure &#40;MySQLToSql&#41;](../../ssma/mysql/migrating-mysql-databases-to-sql-server-azure-sql-db-mysqltosql.md)  
  
