---
title: CLR 存储过程
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: d2fde4fdcd5ab63906256d814256578b9baa9ecd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782496"
---
# <a name="clr-stored-procedures"></a>CLR 存储过程
存储过程是可以用于标量表达式的例程。 它们可以将表格形式的结果和消息返回到客户端，调用数据定义语言 (DDL) 和数据操作语言 (DML) 语句，以及返回输出参数。  
  
> [!NOTE]
> Microsoft Visual Basic 不支持采用与 Microsoft Visual C# 中相同的方式处理输出参数。 您必须指定以通过引用传递参数并应用\<Out （） > 特性来表示 output 参数，如下所示：  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
有关更多详细信息，请参阅所使用 SQL Server 版本的[SQL Server 文档](/sql)版本。
  
 **SQL Server 文档**

1. [CLR 存储过程](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>请参阅

- [在托管代码中创建 SQL Server 2005 对象](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [ADO.NET 概述](../ado-net-overview.md)
