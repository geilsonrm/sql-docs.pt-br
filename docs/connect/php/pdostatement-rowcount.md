---
title: PDOStatement::rowCount | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 0569f26a-2376-4c20-8813-bd3c87d0ae9f
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 68acc6ddb3a5c42562dbbdb787770b76a22b50da
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80925282"
---
# <a name="pdostatementrowcount"></a>PDOStatement::rowCount
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Retorna o número de linhas adicionadas, excluídas ou alteradas pela última instrução.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
int PDOStatement::rowCount ();  
```  
  
## <a name="return-value"></a>Valor retornado  
O número de linhas adicionadas, excluídas ou alteradas.  
  
## <a name="remarks"></a>Comentários  
Se a última instrução SQL executada pelo PDOStatement associado foi uma instrução SELECT, um cursor PDO::CURSOR_FWDONLY retornará -1. Um cursor PDO::CURSOR_SCROLLABLE retorna o número de linhas no conjunto de resultados.  
  
O suporte para PDO foi adicionado na versão 2.0 dos [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Exemplo  
Este exemplo mostra dois usos do rowCount. O primeiro uso retorna o número de linhas que foram adicionadas à tabela. O segundo uso mostra que o rowCount pode retornar o número de linhas em um conjunto de resultados quando você especificar um cursor rolável.  
  
```  
<?php  
$database = "Test";  
$server = "(local)";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
$col1 = 'a';  
$col2 = 'b';  
  
$query = "insert into Table2(col1, col2) values(?, ?)";  
$stmt = $conn->prepare( $query );  
$stmt->execute( array( $col1, $col2 ) );  
print $stmt->rowCount();  
  
echo "\n\n";  
  
$con = null;  
$database = "AdventureWorks";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
$query = "select * from Person.ContactType";  
$stmt = $conn->prepare( $query, array(PDO::ATTR_CURSOR => PDO::CURSOR_SCROLL));  
$stmt->execute();  
print $stmt->rowCount();  
?>  
```  
  
## <a name="see-also"></a>Consulte Também  
[PDOStatement Class](../../connect/php/pdostatement-class.md)

[PDO](https://php.net/manual/book.pdo.php)  
  
