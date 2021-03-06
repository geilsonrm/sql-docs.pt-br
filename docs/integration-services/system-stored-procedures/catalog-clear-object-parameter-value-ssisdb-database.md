---
title: catalog.clear_object_parameter_value (Banco de dados SSISDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: dcbbb714-a051-4805-9e2b-2c2fb647c890
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3f9da77639358fbf154057789f8840cdefc1350d
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86904425"
---
# <a name="catalogclear_object_parameter_value-ssisdb-database"></a>catalog.clear_object_parameter_value (Banco de dados SSISDB)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Limpa o valor de um parâmetro para um projeto ou pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] existente armazenado no servidor.  
  
## <a name="syntax"></a>Sintaxe  
  
```sql  
catalog.clear_object_parameter [ @folder_name = ] folder_name   
    , [ @project_name = ] project_name   
    , [ @object_type = ] object_type   
    , [ @object_name = ] object_name   
    , [ @parameter_ name = ] parameter_name  
```  
  
## <a name="arguments"></a>Argumentos  
 [ \@folder_name = ] *folder_name*  
 O nome da pasta que contém o projeto. O *folder_name* é **nvarchar(128)** .  
  
 [ \@project_name = ] *project_name*  
 O nome do projeto. O *project_name* é **nvarchar(128)** .  
  
 [ \@object_type = ] *object_type*  
 O tipo do objeto. Os valores válidos incluem `20` para um projeto e `30` para um pacote. O *object_type* é **smallInt**.  
  
 [ \@ object _name = ] *object _name*  
 O nome do pacote. O *object _name* é **nvarchar(260)** .  
  
 [ \@parameter_ name = ] *parameter_name*  
 O nome do parâmetro. O *parameter_ name* é **nvarchar(128)** .  
  
## <a name="return-code-value"></a>Valor do código de retorno  
 0 (êxito)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Nenhum  
  
## <a name="permissions"></a>Permissões  
 Este procedimento armazenado exige uma das seguintes permissões:  
  
-   Permissões READ e MODIFY no projeto  
  
-   Associação à função de banco de dados **ssis_admin**  
  
-   Associação à função de servidor **sysadmin**  
  
## <a name="errors-and-warnings"></a>Erros e avisos  
 A lista a seguir descreve algumas condições que podem fazer com que o procedimento armazenado clear_object_parameter gere um erro:  
  
-   Um tipo de objeto inválido é especificado ou o nome do objeto não pode ser localizado no projeto.  
  
-   O projeto não existe, o projeto não está acessível ou o nome do projeto é inválido.  
  
-   Um nome de parâmetro inválido é especificado.  
  
-   O usuário não tem as permissões apropriadas.  
  
  
