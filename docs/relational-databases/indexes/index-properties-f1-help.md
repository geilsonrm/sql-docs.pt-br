---
title: Ajuda de F1 de propriedades do índice | Microsoft Docs
ms.custom: ''
ms.date: 02/17/2017
ms.prod: sql
ms.prod_service: table-view-index, sql-database
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: reference
f1_keywords:
- sql13.swb.indexproperties.filter.f1
- sql13.swb.indexproperties.partitions.f1
- sql13.swb.indexproperties.general.f1
- sql13.swb.indexproperties.storage.f1
- sql13.swb.indexproperties.columns.f1
- sql13.swb.indexproperties.options.f1
- sql13.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
author: MikeRayMSFT
ms.author: mikeray
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: f9ca6fc85701a0056074d4ce3a1ff76abfe1cfb4
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85760805"
---
# <a name="index-properties-f1-help"></a>Ajuda de F1 de Propriedades do Índice
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  As seções neste tópico referem-se a várias propriedades de índice que estão disponíveis usando caixas de diálogo do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .  
  
 **Neste tópico:**  
  
 [Página geral das propriedades do índice](#General)  
  
 [Caixa de diálogo Selecionar Colunas (Índice)](#Columns)  
  
 [Página de armazenamento das propriedades do índice](#Storage)  
  
 [Página Espacial das propriedades do índice](#Spatial)  
  
 [Página Filtrar das propriedades do índice](#Filter)  
  
##  <a name="index-properties-general-page"></a><a name="General"></a> Página geral das propriedades do índice  
 Use a página Geral para exibir ou modificar propriedades de índice para a tabela ou exibição selecionada. As opções para cada página podem mudar de acordo com o tipo de índice selecionado.  
  
 **Nome da tabela**  
 Exibe o nome da tabela ou exibição na qual o índice foi criado. Esse campo é somente leitura. Para selecionar uma tabela diferente, feche a página Propriedades do Índice, selecione a tabela correta e, em seguida, abra a página Propriedades do Índice novamente.  
  
 Não é possível especificar índices espaciais em exibições indexadas. Os índices espaciais podem ser definidos apenas em uma tabela com uma chave primária. O número máximo de colunas de chave primária na tabela é 15. O tamanho por linha combinado das colunas de chave primária é limitado a um máximo de 895 bytes.  
  
 **Nome do índice**  
 Exibe o nome do índice. Este campo é somente leitura para um índice existente. Ao criar um novo índice, digite o nome do índice.  
  
 **Tipo de índice**  
 Indica o tipo de índice. Para novos índices, indica o tipo de índice selecionado ao abrir a caixa de diálogo. Os índices podem ser: **Clusterizado**, **Não clusterizado**, **XML primário**, **XML secundário**, **Espacial**, **Columnstore clusterizado** ou **Columnstore não clusterizado**.  
  
 **Observação** É permitido somente um índice clusterizado para cada tabela. É permitido somente um índice columnstore xVelocity de memória otimizada para cada tabela.  
  
 **Exclusivo**  
 A marcação desta caixa de seleção torna o índice exclusivo. Não é permitido que duas linhas tenham o mesmo valor de índice. Por padrão, essa caixa de seleção é desmarcada. Ao modificar um índice existente, haverá falha na criação do índice se duas linhas tiverem o mesmo valor. Para colunas onde NULL é permitido, um índice exclusivo permite um valor NULL.  
  
 Se você selecionar **Espacial** no campo **Tipo de índice** , a caixa de seleção **Exclusiva** ficará esmaecida.  
  
 **Colunas de chave de índice**  
 Adicione as colunas desejadas à grade **Colunas de chave de índice** . Quando mais de uma coluna é adicionada, as colunas devem ser listadas na ordem desejada. A ordem de coluna em um índice pode ter um grande impacto no desempenho do índice.  
  
 Não é permitido que mais de 16 colunas participem de um único índice composto. Para mais de 16 colunas, consulte as colunas incluídas no final deste tópico.  
  
 É possível definir um índice espacial apenas em uma coluna que contenha um tipo de dados espaciais (uma *coluna espacial*).  
  
 **Nome**  
 Exibe o nome da coluna que participa da chave de índice.  
  
 **Sort Order**  
 Especifica a direção da classificação da coluna de índice selecionada, **Crescente** ou **Decrescente**.  
  
> [!NOTE]  
>  Se o tipo de índice for **XML primário** ou **Espacial**, esta coluna não aparecerá na tabela.  
  
 **Tipo de Dados**  
 Exibe a informações de tipo de dados.  
  
> [!NOTE]  
>  Se a coluna de tabela for uma coluna computada, **Tipo de dados** exibirá "coluna computada".  
  
 **Tamanho**  
 Exibe o número máximo de bytes necessários para armazenar o tipo de dados de coluna. Exibe zero (0) para uma coluna espacial ou XML.  
  
 **Identidade**  
 Exibe se a coluna que participa da chave de índice é uma coluna de identidade.  
  
 **Permitir Nulos**  
 Exibe se a coluna que participa da chave de índice permite armazenar valores NULL na tabela ou coluna de exibição.  
  
 **Adicionar**  
 Adiciona uma coluna à chave de índice. Selecione colunas de tabela na caixa de diálogo **Selecionar Colunas de** *\<table name>* que aparece quando você clica em **Adicionar**. No caso de um índice espacial, depois que você seleciona uma coluna, este botão fica esmaecido.  
  
 **Remover**  
 Remove a coluna selecionada da participação na chave de índice.  
  
 **Mover para Cima**  
 Move a coluna selecionada para cima na grade de chave de índice.  
  
 **Mover para Baixo**  
 Move a coluna selecionada para baixo na grade de chave de índice.  
  
 **Colunas Columnstore**  
 Clique em **Adicionar** para selecionar colunas para o índice columnstore. Para limitações em um índice columnstore, consulte [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-columnstore-index-transact-sql.md).  
  
 **Colunas incluídas**  
 Inclua colunas não chave no índice não clusterizado. Essa opção permite ignorar os limites de índices atuais no tamanho total de uma chave de índice e o número máximo de colunas que participam de uma chave de índice, adicionando colunas como colunas não chave no nível folha do índice não clusterizado. Para obter mais informações, consulte [Criar índices com colunas incluídas](../../relational-databases/indexes/create-indexes-with-included-columns.md)  
  
##  <a name="select-index-columns-dialog-box"></a><a name="Columns"></a> Caixa de diálogo Selecionar Colunas (Índice)  
 Use esta página para adicionar colunas à página **Propriedades Gerais do Índice** ao criar ou modificar um índice.  
  
 **Caixa de seleção**  
 Selecione para adicionar colunas.  
  
 **Nome**  
 Nome da coluna.  
  
 **Tipo de Dados**  
 O tipo de dados da coluna.  
  
 **Bytes**  
 Tamanho da coluna em bytes.  
  
 **Identidade**  
 Exibe **Sim** para colunas de identidade e **Não** quando a coluna não é uma coluna de identidade.  
  
 **Permitir Nulos**  
 Exibe **Sim** quando a definição da tabela permitir valores nulos para a coluna. Exibe **Não** quando a definição da tabela não permite nulos para a coluna.  

##  <a name="options-page-options"></a><a name="Options"></a> Opções da página Opções
 Use essa página para exibir ou modificar as várias opções de índice.

### <a name="general-options"></a>Opções gerais
**Recomputar estatísticas automaticamente**<br>
Especifica se as estatísticas de distribuição são recomputadas automaticamente. O padrão é **True**, que equivale a definir STATISTICS_NORECOMPUTE como OFF. Configurar como **False** define STATISTICS_NORECOMPUTE como ON.

**Ignorar valores duplicados** <br>
Especifica a resposta de erro quando uma operação de inserção tenta inserir valores da chave duplicada em um índice exclusivo.

True<br>
Uma mensagem de aviso será exibida quando valores de chave duplicados forem inseridos em um índice exclusivo. Ocorrerá falha somente nas linhas que violarem a restrição de exclusividade.

Falso<br>
Ocorrerá uma mensagem de erro quando os valores de chave duplicados forem inseridos em um índice exclusivo. Toda a operação INSERT será revertida.

### <a name="locks-options"></a>Opções de Bloqueios

**Permitir bloqueios de linha**<br>
Especifica se bloqueios de linha são permitidos.

**Permitir bloqueios de página**<br>
Especifica se bloqueios de página são permitidos.

### <a name="operation-options"></a>Opções de Operação

 **Permitir processamento DML online**  
 Permite aos usuários acessar a tabela subjacente ou dados de índice clusterizado associados a quaisquer índices não clusterizados durante a operação de índice, como CREATE ou ALTER. Para obter mais informações, consulte [Perform Index Operations Online](../../relational-databases/indexes/perform-index-operations-online.md).  
  
> [!NOTE]  
>  Esta opção não está disponível para índices XML ou se o índice for um índice clusterizadoF desabilitado.  
  
 **Grau máximo de paralelismo**  
 Limita o número de processadores a serem usados durante execução do plano paralelo. O valor padrão, 0, usa o número real de CPUs disponíveis. A definição do valor como 1 elimina a geração em plano paralelo; a definição do valor como um número maior que 1 restringe o número máximo de processadores usados por uma única execução da consulta. Esta opção ficará disponível apenas se a caixa de diálogo estiver no estado **Recriar** ou **Recriar** . Para obter mais informações, consulte [definir o Max Degree of Parallelism opção para otimizar o desempenho](../../relational-databases/policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).  
  
> [!NOTE]  
>  Se um valor maior que o número de CPUs disponíveis for especificado, será usado o número real de CPUs disponíveis.  


**Otimizar para chave sequencial**<br>
Especifica se a contenção de inserção de última página será ou não otimizada. Para saber mais, confira as [Chaves sequenciais](../../t-sql/statements/create-index-transact-sql.md#sequential-keys).

### <a name="storage-options"></a>Opções de armazenamento

**Classificar em tempdb**<br>
Especifica se os resultados de classificação temporários devem ser armazenados em tempdb.

True<br>
Os resultados de classificação intermediários usados para criar o índice são armazenados em tempdb. Isso pode reduzir o tempo necessário para criar um índice se tempdb estiver em um conjunto de discos diferente do banco de dados de usuário. Entretanto, isso aumenta o espaço em disco usado durante a criação do índice.

Falso<br>
Os resultados intermediários de classificação são armazenados no mesmo banco de dados que o índice. Para obter mais informações, consulte a [Opção SORT_IN_TEMPDB para índices](./sort-in-tempdb-option-for-indexes.md).

**Fator de preenchimento**<br>
Especifica uma porcentagem que indica até que ponto o Mecanismo de Banco de Dados deve preencher o nível folha de cada página de índice durante a criação ou recompilação do índice. fillfactor deve ser um valor inteiro de 1 a 100. Se fillfactor for 100, o Mecanismo de Banco de Dados criará índices com páginas de folhas preenchidas até a capacidade total.
A configuração FILLFACTOR se aplica somente quando o índice é criado ou recriado. O Mecanismo de Banco de Dados não mantém dinamicamente a porcentagem especificada de espaço vazio nas páginas.

Para obter mais informações, veja [Especificar fator de preenchimento para um índice](./specify-fill-factor-for-an-index.md).

**Preenchimento de índice**<br>
Especifica o preenchimento do índice.

True<br>
A porcentagem de espaço livre especificada por fillfactor é aplicada às páginas de nível intermediário do índice.

False ou fillfactor não está especificado<br>
As páginas de nível intermediário são preenchidas até próximo de sua capacidade, deixando espaço suficiente para pelo menos uma linha do tamanho máximo que o índice pode ter, considerando o conjunto de chaves em páginas intermediárias.


##  <a name="storage-page-options"></a><a name="Storage"></a> Opções da página de armazenamento  
 Use essa página para exibir ou modificar grupo de arquivos ou propriedades de esquema de partição para o índice selecionado. Mostra apenas opções relacionadas ao tipo de índice.  
  
 **Grupo de arquivos**  
 Armazena o índice no grupo de arquivos especificado. A lista exibe apenas grupos de arquivos padrão (linha). A seleção de lista padrão é o grupo de arquivos PRIMARY do banco de dados. Para obter mais informações, consulte [Database Files and Filegroups](../../relational-databases/databases/database-files-and-filegroups.md).  
  
 **Grupos de Arquivos do Fluxo de Arquivos**  
 Especifica o grupo de arquivos para obter dados de FILESTREAM. Essa lista exibe apenas grupos de arquivos FILESTREAM. A seleção de lista padrão é o grupo de arquivos PRIMARY FILESTREAM. Para obter mais informações, veja [FILESTREAM &#40;SQL Server&#41;](../../relational-databases/blob/filestream-sql-server.md).  
  
 **Esquema de partição**  
 Armazena o índice em um esquema de partição. Clicando em **Esquema de Partição** a grade abaixo é habilitada. A seleção de lista padrão é o esquema de partição usado para armazenar os dados de tabela. Ao selecionar um esquema de partição diferente na lista, a informações na grade é atualizada. Para saber mais, confira [Partitioned Tables and Indexes](../../relational-databases/partitions/partitioned-tables-and-indexes.md).  
  
 A opção de esquema de partição fica indisponível se não houver nenhum esquema de partição no banco de dados.  
  
 **Esquema de Partição do Fluxo de Arquivos**  
 Especifica o esquema de partição para dados FILESTREAM. O esquema de partição deve ser simétrico com o esquema especificado na opção **Esquema de partição** .  
  
 Se a tabela não for particionada, o campo fica em branco.  
  
 **Parâmetro do Esquema de Partição**  
 Exibe o nome da coluna que participa do esquema de partição.  
  
 **Coluna de tabela**  
 Selecione a tabela ou exiba para mapear para o esquema de partição.  
  
 **Tipo de dados da coluna**  
 Exibe informações de tipo de dados sobre a coluna.  
  
> [!NOTE]  
>  Se a coluna de tabela for uma coluna computada, **Tipo de Dados da Coluna** exibirá "coluna computada."  
  
##  <a name="spatial-page-index-options"></a><a name="Spatial"></a> Opções de índice da página Espacial  
 Use a página **Espacial** para exibir ou especificar os valores das propriedades espaciais. Para obter mais informações, veja [Dados espaciais &#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md).  
  
### <a name="bounding-box"></a>Caixa delimitadora  
 A *caixa delimitadora* é o perímetro da grade de alto nível de um plano geométrico. Os parâmetros da caixa delimitadora só existem no mosaico de grade geométrica. Esses parâmetros ficarão indisponíveis se o **Esquema de Mosaico** for **Grade geográfica**.  
  
 O painel exibe as coordenadas **(** _X mín._ **,** _Y mín._ **)** e **(** _X máx._ **,** _Y máx._ **)** da caixa delimitadora. Não há valores de coordenada padrão. Portanto, ao criar um novo índice espacial em uma **geometry** coluna de tipo, será necessário especificar os valores de coordenada.  
  
 **X-min**  
 A coordenada X do canto inferior esquerdo da caixa delimitadora.  
  
 **Y-min**  
 A coordenada Y do canto inferior esquerdo da caixa delimitadora.  
  
 **X-max**  
 Coordenada X do canto superior direito da caixa delimitadora.  
  
 **Y-max**  
 Coordenada Y do canto superior direito da caixa delimitadora.  
  
### <a name="general"></a>Geral  
 **Esquema de Mosaico**  
 Indica o esquema de mosaico do índice. Os esquemas de mosaico com suporte são os seguintes:  
  
 **Grade geométrica**  
 Especifica o esquema de mosaico de grade geométrica, que se aplica a uma coluna do tipo de dados **geometria** .  
  
 **Grade Automática de Geometria**  
 Esta opção é habilitada para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando o nível de compatibilidade de banco de dados é definido como 110 ou superior.  
  
 **Grade geográfica**  
 Especifica o esquema de mosaico de grade de geografia, que se aplica a uma coluna do tipo de dados **geografia** .  
  
 **Grade Automática de Geografia**  
 Esta opção é habilitada para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando o nível de compatibilidade de banco de dados é definido como 110 ou superior.  
  
 Para obter informações sobre como o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementa o mosaico, consulte [Dados espaciais &#40;SQL Server&#41;](../../relational-databases/spatial/spatial-data-sql-server.md).  
  
 **Células por Objeto**  
 Indica o número de células por objeto do mosaico que pode ser usado para um único objeto espacial no índice. Esse número pode ser qualquer inteiro entre 1 e 8.192, inclusive. O padrão é 16, e 8 para versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quando o nível de compatibilidade de banco de dados é definido como 110 ou superior.  
  
 No nível superior, se um objeto abranger mais células que o especificado por *n*, a indexação usará o número de células necessário para fornecer um mosaico de nível superior completo. Nesses casos, um objeto poderia receber mais que o número de células especificado. Nesse caso, o número máximo de células geradas pela grade de nível superior, que depende da densidade **Nível 1** .  
  
### <a name="grids"></a>Grades  
 Este painel mostra a densidade da grade a cada nível do esquema de mosaico. A densidade é especificada como **Baixa**, **Média**ou **Alta**. O padrão **Média**. **Baixa** representa uma grade de 4x4 (16 células), **Média** representa uma grade de 8x8 (64 células) e **Alta** representa uma grade de 16x16 (256 células). Essas opções não estão disponíveis quando as opções de mosaico **Grade Automática de Geometria** ou **Grade Automática de Geografia** são escolhidas.  
  
 **Nível 1**  
 A densidade da grade de primeiro nível (superior).  
  
 **Nível 2**  
 A densidade da grade de segundo nível.  
  
 **Nível 3**  
 A densidade da grade de terceiro nível.  
  
 **Nível 4**  
 A densidade da grade de quarto nível.  
  
##  <a name="filter-page"></a><a name="Filter"></a> Página de filtros  
 Use esta página para inserir o predicado do filtro para um índice filtrado. Para saber mais, confira [Create Filtered Indexes](../../relational-databases/indexes/create-filtered-indexes.md).  
  
 **Expressão de filtro**  
 Define quais linhas de dados devem ser incluídas no índice filtrado. Por exemplo, `StartDate > '20000101' AND EndDate IS NOT NULL'.`  
  
## <a name="see-also"></a>Consulte Também  
 [Opções Set Index](../../relational-databases/indexes/set-index-options.md)   
 [INDEXPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/indexproperty-transact-sql.md)   
 [sys.indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)  
  
  
