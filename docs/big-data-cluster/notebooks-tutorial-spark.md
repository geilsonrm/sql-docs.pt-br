---
title: Executar um notebook de exemplo usando o Spark
titleSuffix: SQL Server big data clusters
description: Este tutorial mostra como você pode carregar e executar um notebook Spark de exemplo em um cluster de Big Data do SQL Server 2019.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 03/30/2020
ms.topic: tutorial
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 7f42b454ebfc1b9b4ea8e841cba6fe2a4b209ebc
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85660372"
---
# <a name="run-a-sample-notebook-using-spark"></a>Executar um notebook de exemplo usando o Spark

[!INCLUDE[SQL Server 2019](../includes/applies-to-version/sqlserver2019.md)]

Este tutorial demonstra como carregar e executar um notebook no Azure Data Studio em um [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]. Isso permite que os cientistas e os engenheiros de dados executem código Python, R ou Scala no cluster.

> [!TIP]
> Se preferir, você poderá baixar e executar um script para os comandos neste tutorial. Para obter instruções, confira os [Exemplos do Spark](https://github.com/Microsoft/sql-server-samples/tree/master/samples/features/sql-big-data-cluster/spark) no GitHub.

## <a name="prerequisites"></a><a id="prereqs"></a> Pré-requisitos

- [Ferramentas de Big Data](deploy-big-data-tools.md)
   - **kubectl**
   - **Azure Data Studio**
   - **Extensão do SQL Server 2019**
- [Carregar dados de exemplo em seu cluster de Big Data](tutorial-load-sample-data.md)

## <a name="download-the-sample-notebook-file"></a>Baixar o arquivo de notebook de exemplo

Use as instruções a seguir para carregar o arquivo de notebook de exemplo **spark-sql.ipynb** no Azure Data Studio.

1. Abra um prompt de comando do bash (Linux) ou o Windows PowerShell.

1. Navegue até um diretório no qual você deseja baixar o arquivo de notebook de exemplo.

1. Execute o seguinte comando de **rotação** para baixar o arquivo do notebook do GitHub:

   ```bash
   curl 'https://raw.githubusercontent.com/Microsoft/sql-server-samples/master/samples/features/sql-big-data-cluster/spark/data-loading/transform-csv-files.ipynb' -o transform-csv-files.ipynb
   ```

## <a name="open-the-notebook"></a>Abrir o notebook

As etapas a seguir mostram como abrir o arquivo do notebook no Azure Data Studio:

1. No Azure Data Studio, conecte-se à instância mestre do cluster de Big Data. Para obter mais informações, confira [Conectar-se a um cluster de Big Data](connect-to-big-data-cluster.md).

1. Clique duas vezes na conexão do gateway HDFS/Spark na janela **Servidores**. Em seguida, selecione **Abrir Notebook**.

   ![Abrir notebook](media/notebook-tutorial-spark/azure-data-studio-open-notebook.png)

1. Aguarde até que o **Kernel** e o contexto de destino (**Anexar a**) sejam preenchidos. Defina o **Kernel** como **PySpark3** e defina **Anexar a** como o endereço IP do seu ponto de extremidade do cluster de Big Data.

   ![Definir o kernel e Anexar a](media/notebook-tutorial-spark/set-kernel-and-attach-to.png)

## <a name="run-the-notebook-cells"></a>Executar as células do notebook

Você pode executar cada célula do notebook pressionando o botão Reproduzir à esquerda da célula. Os resultados são mostrados no notebook após a conclusão da execução da célula.

![Executar célula do notebook](media/notebook-tutorial-spark/run-notebook-cell.png)

Execute cada uma das células no notebook de exemplo sucessivamente. Para obter mais informações sobre como usar notebooks com [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)], confira os seguintes recursos:

- [Como usar notebooks](../azure-data-studio/notebooks-guidance.md)
- [Como gerenciar notebooks no Azure Data Studio](notebooks-manage-bdc.md)

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre os notebooks:
> [!div class="nextstepaction"]
> [Como usar notebooks](../azure-data-studio/notebooks-guidance.md)
