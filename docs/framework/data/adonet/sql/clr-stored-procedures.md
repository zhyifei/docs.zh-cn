---
title: "CLR 存储过程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dfed0124c33c90427c9b888f5aa7bb191aea0400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="clr-stored-procedures"></a>CLR 存储过程
存储过程是可以用于标量表达式的例程。 它们可以将表格形式的结果和消息返回到客户端，调用数据定义语言 (DDL) 和数据操作语言 (DML) 语句，以及返回输出参数。  
  
> [!NOTE]
>  Microsoft Visual Basic 不支持采用与 Microsoft Visual C# 中相同的方式处理输出参数。 必须指定用于通过引用传递参数并应用\<out （) > 属性以表示输出参数，如以下所示：  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。  
  
 **SQL Server 联机丛书**  
  
1.  [CLR 存储过程](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>请参阅  
 [在托管代码中创建 SQL Server 2005 对象](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
