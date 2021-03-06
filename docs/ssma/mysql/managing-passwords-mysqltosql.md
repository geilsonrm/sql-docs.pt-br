---
title: Gerenciando senhas (MySQLToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 07/06/2020
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Password management, importing or exporting encrypted password
- Password management, securing password
ms.assetid: 4ffbc587-ea3f-49ad-bc42-a654f672325e
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: fc06af58a8e669b836a88490ebcbc7c971ca2f4f
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86053552"
---
# <a name="managing-passwords-mysqltosql"></a>Gerenciamento de senhas (MySQLToSQL)
Este artigo trata da proteção de senhas de banco de dados e do procedimento para importá-las ou exportá-las entre servidores.
  
## <a name="securing-password"></a>Protegendo a senha  
O SSMA permite que você proteja sua senha de um banco de dados.  
  
Use o procedimento a seguir para implementar uma conexão segura:  
  
Especifique uma senha válida usando um dos três métodos a seguir:  
  
1.  **Texto não criptografado:** Digite a senha do banco de dados no atributo Value do nó ' password '. Ele é encontrado no nó definição do servidor na seção servidor do arquivo de script ou arquivo de conexão do servidor.  
  
    As senhas em texto não criptografado não são seguras. Portanto, você encontrará a seguinte mensagem de aviso na saída do console: *"servidor Server &lt; -ID &gt; da senha é fornecido em formato de texto não seguro, o aplicativo do console do SSMA fornece uma opção para proteger a senha por meio de criptografia, consulte a opção-SecurePassword no arquivo de ajuda do SSMA para obter mais informações".*  
  
    **Senhas criptografadas:** A senha especificada, nesse caso, é armazenada em um formato criptografado no computador local no ProtectedStorage. SSMA.  
  
    -   **Protegendo senhas**  
  
        -   Execute o `SSMAforMySQLConsole.exe` com o `-securepassword` e adicione a opção na linha de comando passando a conexão do servidor ou o arquivo de script que contém o nó senha na seção definição do servidor.  
  
        -   No prompt, o usuário será solicitado a inserir a senha do banco de dados e confirmá-la.  
  
            As IDs de definição de servidor e suas senhas criptografadas correspondentes são armazenadas em um arquivo no computador local  
            
            **Exemplo 1:**
            
            1. Especificar senha
            
            2. `C:\SSMA\SSMAforMySQLConsole.EXE -securepassword -add all -s "D:\Program Files\Microsoft SQL Server Migration Assistant for MySQL\Sample Console Scripts\AssessmentReportGenerationSample.xml" -v "D:\Program Files\Microsoft SQL Server Migration Assistant for MySQL\Sample Console Scripts\ VariableValueFileSample.xml"`
            
            3. Insira a senha para o server_id ' XXX_1 ': xxxxxxx
            
            4. Digite a senha novamente para server_id ' XXX_1 ': xxxxxxx
            
            **Exemplo 2:**
            
            1. `C:\SSMA\SSMAforMySQLConsole.EXE -securepassword -add "source_1,target_1" -c "D:\Program Files\Microsoft SQL Server Migration Assistant for MySQL\Sample Console Scripts\ServersConnectionFileSample.xml" - v "D:\Program Files\Microsoft SQL Server Migration Assistant for MySQL\Sample Console Scripts\ VariableValueFileSample.xml" -o`
            
            2. Insira a senha para o server_id ' source_1 ': xxxxxxx
            
            3. Digite a senha novamente para server_id ' source_1 ': xxxxxxx
            
            4. Insira a senha para o server_id ' target_1 ': xxxxxxx
            
            5. Digite a senha novamente para server_id ' target _1 ': xxxxxxx
            
    -   **Removendo senhas criptografadas**  
  
        Execute o `SSMAforMySQLConsole.exe` com a `-securepassword` `-remove` opção e na linha de comando passando as IDs do servidor, para remover as senhas criptografadas do arquivo de armazenamento protegido presente no computador local.  
  
        Exemplo:  

        ```console
        C:\SSMA\SSMAforMySQLConsole.EXE -securepassword -remove all
        C:\SSMA\SSMAforMySQLConsole.EXE -securepassword -remove "source_1,target_1"  
        ```
  
    -   **Listando IDs de servidor cujas senhas são criptografadas**  
  
        Execute o `SSMAforMySQLConsole.exe` com a `-securepassword` `-list` opção e na linha de comando para listar todas as IDs de servidor cujas senhas foram criptografadas.  
  
        Exemplo:  
        
        ```console
        C:\SSMA\SSMAforMySQLConsole.EXE -securepassword -list  
        ```
  
    > [!NOTE]  
    > 1.  A senha em texto não criptografado mencionado no arquivo de conexão de script ou servidor tem precedência sobre a senha criptografada no arquivo protegido.  
    > 2.  Quando não houver nenhuma senha na seção do servidor do arquivo de conexão do servidor ou do arquivo de script ou se não tiver sido protegida no computador local, o console do solicitará que você insira a senha.  
  
## <a name="exporting-or-importing-encrypted-passwords"></a>Exportando ou importando senhas criptografadas  
O aplicativo de console do SSMA permite exportar senhas de banco de dados criptografadas presentes em um arquivo no computador local para um arquivo protegido e vice-versa. Ele ajuda a tornar o computador com senhas criptografadas independente.

A funcionalidade de exportação lê a ID do servidor e a senha do armazenamento protegido local e salva as informações em um arquivo criptografado. O usuário é solicitado a inserir a senha para o arquivo protegido. Certifique-se de que a senha inserida tenha um comprimento de 8 caracteres ou mais. Esse arquivo protegido é portável em computadores diferentes.

A funcionalidade de importação lê a ID do servidor e as informações de senha do arquivo protegido. O usuário é solicitado a inserir a senha para o arquivo protegido e acrescenta as informações ao armazenamento protegido local.  
  
### <a name="export-example"></a>Exemplo de exportação:  

1. Exportar senha

2. Insira a senha para proteger o arquivo exportado

3. C:\SSMA\SSMAforMySQLConsole.EXE-SecurePassword-exportar todos os "machine1passwords. File"

4. Insira a senha para proteger o arquivo exportado: xxxxxxxx

5. Confirme a senha: xxxxxxxx

6. C:\SSMA\SSMAforMySQLConsole.EXE-p-e "MySQLDB_1_1, Sql_1" "machine2passwords. File"

7. Insira a senha para proteger o arquivo exportado: xxxxxxxx

8. Confirme a senha: xxxxxxxx  
  
### <a name="import-example"></a>Exemplo de importação:  

1. Importar uma senha criptografada

2. Insira a senha para proteger o arquivo importado

3. C:\SSMA\SSMAforMySQLConsole.EXE-SecurePassword-importar todos os "machine1passwords. File"

4. Insira a senha para importar os servidores do arquivo criptografado: xxxxxxxx

5. Confirme a senha: xxxxxxxx

6. C:\SSMA\SSMAforMySQLConsole.EXE-p-i "MySQLDB_1, Sql_1" "machine2passwords. File"

7. Insira a senha para importar os servidores do arquivo criptografado: xxxxxxxx

8. Confirme a senha: xxxxxxxx  
  
## <a name="see-also"></a>Consulte Também  
[Executando o console do SSMA (MySQL)](https://msdn.microsoft.com/e3e9f7e4-0619-4861-a202-3d5d39953b26)  
  
