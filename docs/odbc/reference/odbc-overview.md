---
title: Visão geral do ODBC | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC [ODBC]
- ODBC [ODBC], about ODBC
ms.assetid: 233315bd-2b7f-4b20-9978-e920e1ea9a07
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0a0515a882cd7d1c97a60e9262942bd7c397b0b2
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "81298286"
---
# <a name="odbc-overview"></a>Visão geral do ODBC
ODBC (Open Database Connectivity) é uma API (interface de programação de aplicativo) amplamente aceita para acesso ao banco de dados. Ele se baseia nas especificações da CLI (interface de nível de chamada) de Open Group e ISO/IEC para APIs de banco de dados e usa linguagem SQL (SQL) como seu idioma de acesso ao banco de dados.  
  
 O ODBC foi projetado para uma *interoperabilidade* máxima, ou seja, a capacidade de um único aplicativo acessar diferentes DBMS (sistemas de gerenciamento de banco de dados) com o mesmo código-fonte. Os aplicativos de banco de dados chamam funções na interface ODBC, que são implementados em módulos específicos de banco de dados chamados *drivers*. O uso de drivers isola aplicativos de chamadas específicas de banco de dados da mesma forma que os drivers de impressora isolam os programas de processamento de texto dos comandos específicos da impressora. Como os drivers são carregados em tempo de execução, um usuário só precisa adicionar um novo driver para acessar um novo DBMS; Não é necessário recompilar ou vincular novamente o aplicativo.  
  
 Esta seção contém os seguintes tópicos.  
  
-   [Por que o ODBC foi criado?](../../odbc/reference/why-was-odbc-created.md)  
  
-   [O que é o ODBC?](../../odbc/reference/what-is-odbc.md)  
  
-   [ODBC e a CLI padrão](../../odbc/reference/odbc-and-the-standard-cli.md)
