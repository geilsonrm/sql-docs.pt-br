---
title: Diretrizes e limitações de Updategrams (SQLXML)
description: Saiba mais sobre as diretrizes e limitações do uso de Updategrams XML no SQLXML 4,0.
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updategrams [SQLXML], about updategrams
ms.assetid: b5231859-14e2-4276-bc17-db2817b6f235
author: MightyPen
ms.author: genemi
ms.custom: seo-lt-2019
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: fb774fd8dbb05b52e4f57fcf78d4ecd4c923ccb8
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85790649"
---
# <a name="guidelines-and-limitations-of-xml-updategrams-sqlxml-40"></a>Diretrizes e limitações dos diagramas de atualização XML (SQLXML 4.0)
[!INCLUDE [SQL Server Azure SQL Database](../../../includes/applies-to-version/sql-asdb.md)]
  Lembre-se das recomendações a seguir ao usar diagramas de atualização XML:  
  
-   Se você estiver usando um updategram para uma operação de inserção com apenas um único par **\<before>** de **\<after>** blocos e, o **\<before>** bloco poderá ser omitido. Por outro lado, no caso de uma operação de exclusão, o **\<after>** bloco pode ser omitido.  
  
-   Se você estiver usando um updategram com vários **\<before>** **\<after>** blocos e na **\<sync>** marca, os **\<before>** blocos e blocos **\<after>** deverão ser especificados para formar **\<before>** e **\<after>** emparelhar.  
  
-   As atualizações em um diagrama de atualização são aplicadas à exibição XML fornecida pelo esquema XML. Portanto, para o mapeamento padrão obter êxito em qualquer uma das situações, você precisará especificar o nome do arquivo de esquema no diagrama de atualização ou, se o nome do arquivo não for fornecido, os nomes de elemento e atributo precisarão corresponder aos nomes de tabela e coluna no banco de dados.  
  
-   O SQLXML 4.0 exige que todos os valores de coluna de um diagrama de atualização sejam mapeados explicitamente no esquema (XDR ou XSD) fornecido para compor a exibição XML de seus elementos filho. Esse comportamento é diferente de versões anteriores do SQLXML, que permitia um valor para uma coluna não mapeada no esquema se ele estava implícito como parte da chave estrangeira em uma anotação **SQL: relationship** . (Observe que essa alteração não influencia na propagação dos valores de chave primária para os elementos filho, que ainda ocorrerá para o SQLXML 4.0 se nenhum valor for especificado explicitamente para o elemento filho.  
  
-   Se você estiver usando um updategram para modificar dados em uma coluna binária (como o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tipo de dados **Image** ), deverá fornecer um esquema de mapeamento no qual o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tipo de dados (por exemplo, **SQL: datatype = "Image"**) e o tipo de dados XML (por exemplo, **dt: Type = "BinHex"** ou **dt: Type = "binbase64**) devem ser especificados. Os dados da coluna binária devem ser especificados no updategram; a anotação **SQL: url-encode** especificada no esquema de mapeamento é ignorada pelo updategram.  
  
-   Quando você estiver gravando um esquema XSD, se o valor especificado para a anotação **SQL: relation** ou **SQL: Field** incluir um caractere especial, como um caractere de espaço (por exemplo, no nome da tabela "detalhes do pedido"), esse valor deverá ser colocado entre colchetes (por exemplo, "[detalhes do pedido]").  
  
-   Ao usar diagramas de atualização, não são suportadas relações de cadeia. Por exemplo, se as tabelas A e C tiverem uma relação de cadeia que use a tabela B, ocorrerá o erro a seguir ao tentar executar o diagrama de atualização:  
  
    ```  
    There is an inconsistency in the schema provided.  
    ```  
  
     Mesmo se o esquema e o diagrama de atualização estiverem corretos e devidamente formados, esse erro ocorrerá se houver uma relação de cadeia.  
  
-   Os Updategrams não permitem a passagem de dados de tipo de **imagem** como parâmetros durante atualizações.  
  
-   Tipos BLOB (objeto binário grande) como **Text/ntext** e images não devem ser usados no **\<before>** bloco in ao trabalhar com Updategrams, pois isso os incluirá para uso no controle de simultaneidade. Isso pode causar problemas com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] devido às limitações de comparação para tipos BLOB. Por exemplo, a palavra-chave LIKE é usada na cláusula WHERE para comparar entre colunas do tipo de dados **Text** ; no entanto, as comparações falharão no caso de tipos de BLOB em que o tamanho dos dados seja maior que 8K.  
  
-   Caracteres especiais em dados **ntext** podem causar problemas com o SQLXML 4,0 devido às limitações de comparação para tipos de BLOB. Por exemplo, o uso de "[Serializable]" no **\<before>** bloco de Updategrams quando usado na verificação de simultaneidade de uma coluna de tipo **ntext** falhará com a seguinte descrição de erro SQLOLEDB:  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
## <a name="see-also"></a>Consulte Também  
 [Considerações de segurança do updategram &#40;SQLXML 4,0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
