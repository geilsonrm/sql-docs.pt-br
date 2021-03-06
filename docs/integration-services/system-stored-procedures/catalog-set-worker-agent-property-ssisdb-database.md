---
title: catalog.set_worker_agent_property (banco de dados SSISDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ddd2a534-6925-4d66-90e7-541c14f41de7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 121c39ddc217cbdc178ca8ea8221081ce33eee4b
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86912771"
---
# <a name="catalogset_worker_agent_property-ssisdb-database"></a>catalog.set_worker_agent_property (banco de dados SSISDB)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Define a propriedade de um Trabalho do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Scale Out.

## <a name="syntax"></a>Sintaxe

```sql
catalog.set_worker_agent_property [ @WorkerAgentId = ] WorkerAgentId
    , [ @PropertyName = ] PropertyName
    , [ @PropertyValue = ] PropertyValue 
```

## <a name="arguments"></a>Argumentos
[@WorkerAgentId =] *WorkerAgentId*  
A ID do agente de trabalho do Trabalhador do Scale Out. O *WorkerAgentId* é **uniqueidentifier**.

[@PropertyName =] *PropertyName*  
O nome da propriedade. O *PropertyName* é **nvarchar(256)** .

[@PropertyValue =] *PropertyValue*  
O valor da propriedade. O *PropertyValue* é **nvarchar(max)** .

## <a name="remarks"></a>Comentários
Os nomes de propriedade válidos são **DisplayName**, **Description** e **Tags**.

## <a name="return-code-value"></a>Valor do código de retorno  
 0 (êxito)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Nenhum  

## <a name="permissions"></a>Permissões  
 Este procedimento armazenado exige uma das seguintes permissões:  
  
-   Associação à função de banco de dados **ssis_admin**  
  
-   Associação à função de servidor **sysadmin**

## <a name="errors-and-warnings"></a>Erros e avisos
  A lista a seguir descreve algumas condições que podem gerar um erro ou um aviso:  
  
-   O usuário não tem as permissões apropriadas 

-   A ID do agente de trabalho não é válida.

-   O nome da propriedade não é válido.

-   O valor da propriedade não é válido.  
