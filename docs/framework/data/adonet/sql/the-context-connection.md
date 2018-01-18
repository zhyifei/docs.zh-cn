---
title: "上下文连接"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9a50f3d91f8de146aee602cc94a33728e5a4c738
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="the-context-connection"></a>上下文连接
内部数据访问出现问题相当普遍。 也就是说，您想要访问的服务器正是正在执行公共语言运行库 (CLR) 存储过程或函数的服务器。 一个选择是使用 <xref:System.Data.SqlClient.SqlConnection> 创建一个连接，指定指向本地服务器的连接字符串，然后打开该连接。 这要求指定用于登录的凭据。 此连接位于与存储过程或函数不同的数据库会话中，它可以具有不同的 `SET` 选项，位于不同的事务中，并且看不到您的临时表等。 如果您的托管存储过程或函数代码正在 SQL Server 进程中执行，原因可能是某人连接到了该服务器并且执行了 SQL 语句以调用它。 您可能希望存储过程或函数在该连接的上下文中与其事务、`SET` 选项等一起执行。 这称作上下文连接。  
  
 通过上下文连接，您可以在第一个位置中调用了您的代码的相同上下文中执行 Transact-SQL 语句。 有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。  
  
 **SQL Server 联机丛书**  
  
1.  [上下文连接](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a>请参阅  
 [在托管代码中创建 SQL Server 2005 对象](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
