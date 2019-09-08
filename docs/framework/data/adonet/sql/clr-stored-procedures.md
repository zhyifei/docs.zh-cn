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
# <a name="clr-stored-procedures"></a><span data-ttu-id="da865-102">CLR 存储过程</span><span class="sxs-lookup"><span data-stu-id="da865-102">CLR Stored Procedures</span></span>
<span data-ttu-id="da865-103">存储过程是可以用于标量表达式的例程。</span><span class="sxs-lookup"><span data-stu-id="da865-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="da865-104">它们可以将表格形式的结果和消息返回到客户端，调用数据定义语言 (DDL) 和数据操作语言 (DML) 语句，以及返回输出参数。</span><span class="sxs-lookup"><span data-stu-id="da865-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da865-105">Microsoft Visual Basic 不支持采用与 Microsoft Visual C# 中相同的方式处理输出参数。</span><span class="sxs-lookup"><span data-stu-id="da865-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="da865-106">您必须指定以通过引用传递参数并应用\<Out （） > 特性来表示 output 参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da865-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="da865-107">有关更多详细信息，请参阅所使用 SQL Server 版本的[SQL Server 文档](/sql)版本。</span><span class="sxs-lookup"><span data-stu-id="da865-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="da865-108">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="da865-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="da865-109">CLR 存储过程</span><span class="sxs-lookup"><span data-stu-id="da865-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="da865-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="da865-110">See also</span></span>

- <span data-ttu-id="da865-111">[在托管代码中创建 SQL Server 2005 对象](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="da865-111">[Creating SQL Server 2005 Objects In Managed Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))</span></span>
- [<span data-ttu-id="da865-112">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="da865-112">ADO.NET Overview</span></span>](../ado-net-overview.md)
