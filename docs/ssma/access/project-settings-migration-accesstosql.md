---
title: Configurações do projeto (migração) (AccessToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Migration settings
- Project Settings dialog box, Migration
ms.assetid: 4caebc9c-8680-4b99-a8fa-89c43161c95d
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 3e3d979b6f3c5943723fb5dd8f37831adfbc1305
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "67929391"
---
# <a name="project-settings-migration-accesstosql"></a>Configurações do projeto (migração) (AccessToSQL)
As configurações do projeto de migração permitem que você configure como os dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são migrados para o ou SQL Azure.  
  
O painel migração está disponível nas caixas de diálogo **configurações do projeto** e **configurações padrão do projeto** .  
  
-   Use a caixa de diálogo **configurações do projeto** para definir opções de configuração para o projeto atual. Para acessar as configurações de migração, no menu **ferramentas** , selecione **configurações do projeto**, clique em **geral** na parte inferior do painel esquerdo e clique em **migração**.  
  
-   Use a caixa de diálogo **configurações de projeto padrão** para definir opções de configuração para todos os projetos. Para acessar as configurações de migração, no menu **ferramentas** , selecione **configurações de projeto padrão**, selecione o tipo de projeto na caixa de combinação **versão de destino de migração** da qual você deseja acessar as configurações, clique em **geral** na parte inferior do painel esquerdo e clique em **migração**.  
  
## <a name="options"></a>Opções  
**Verificar restrições**  
Especifica se o SSMA deve verificar as restrições ao adicionar dados às tabelas.  
  
-   **Modo padrão**: false  
  
-   **Modo otimista**: verdadeiro  
  
-   **Modo completo**: falso  
  
**Acionadores**  
Especifica se o SSMA deve acionar gatilhos de inserção ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adicionar dados a tabelas.  
  
-   **Modo padrão**: false  
  
-   **Modo otimista**: verdadeiro  
  
-   **Modo completo**: falso  
  
**Manter identidade**  
Especifica se o SSMA preserva os valores de identidade de acesso ao adicionar dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ao. Se esse valor for false, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o atribuirá valores de identidade.  
  
-   **Modo padrão**: verdadeiro  
  
-   **Modo otimista**: verdadeiro  
  
-   **Modo completo**: falso  
  
**Manter nulos**  
Especifica se o SSMA preserva valores nulos nos dados de origem quando adiciona dados a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], independentemente dos valores padrão especificados em. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
  
-   **Modo padrão**: verdadeiro  
  
-   **Modo otimista**: false  
  
-   **Modo completo**: verdadeiro  
  
**Bloqueios de tabela**  
Especifica se o SSMA bloqueia as tabelas quando adiciona dados a tabelas durante a migração de dados. Se o valor for false, o SSMA usará bloqueios de linha.  
  
-   **Modo padrão**: verdadeiro  
  
-   **Modo otimista**: verdadeiro  
  
-   **Modo completo**: verdadeiro  
  
**Substituir datas sem suporte**  
Especifica se o SSMA deve corrigir as datas de acesso anteriores à data de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DateTime mais antiga (01 de janeiro de 1753).  
  
-   Para manter os valores de data atuais, selecione **não fazer nada**. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]não aceitará datas antes de 1º de janeiro de 1753 em uma coluna DateTime. Se você usar datas mais antigas, deverá converter os valores DateTime em valores de caracteres.  
  
-   Para converter datas antes de 1º de janeiro de 1753 a NULL, selecione **substituir por NULL**.  
  
-   Para substituir datas antes de 1º de janeiro de 1753 com uma data com suporte, selecione **substituir pela data com suporte mais próxima**. Se você selecionar esse valor, por padrão, a data mais próxima com suporte será selecionada como 01 de janeiro de 1753.  
  
**Tamanho do lote**  
Tamanho do lote usado durante a migração de dados. Uma transação é registrada após cada lote. Por padrão, o tamanho do lote para todos os esquemas é 10000.  
  
## <a name="see-also"></a>Consulte Também  
[Referência da interface do usuário (Access)](https://msdn.microsoft.com/af24c303-4a41-449b-9c86-d6558a97e839)  
  
