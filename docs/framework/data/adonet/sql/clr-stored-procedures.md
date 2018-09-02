---
title: CLR 存储过程
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 1f8aa6fb9243706d07caa4527af0c4c880aa70a6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424329"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="28231-102">CLR 存储过程</span><span class="sxs-lookup"><span data-stu-id="28231-102">CLR Stored Procedures</span></span>
<span data-ttu-id="28231-103">存储过程是可以用于标量表达式的例程。</span><span class="sxs-lookup"><span data-stu-id="28231-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="28231-104">它们可以将表格形式的结果和消息返回到客户端，调用数据定义语言 (DDL) 和数据操作语言 (DML) 语句，以及返回输出参数。</span><span class="sxs-lookup"><span data-stu-id="28231-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28231-105">Microsoft Visual Basic 不支持采用与 Microsoft Visual C# 中相同的方式处理输出参数。</span><span class="sxs-lookup"><span data-stu-id="28231-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="28231-106">您必须指定通过引用传递参数并应用\<out （) > 属性以表示输出参数，如以下所示：</span><span class="sxs-lookup"><span data-stu-id="28231-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="28231-107">有关详细信息，请参阅的新版[SQL Server 文档](/sql)正在使用的 SQL Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="28231-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="28231-108">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="28231-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="28231-109">CLR 存储过程</span><span class="sxs-lookup"><span data-stu-id="28231-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="28231-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="28231-110">See Also</span></span>  
 [<span data-ttu-id="28231-111">在托管代码中创建 SQL Server 2005 对象</span><span class="sxs-lookup"><span data-stu-id="28231-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="28231-112">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="28231-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
