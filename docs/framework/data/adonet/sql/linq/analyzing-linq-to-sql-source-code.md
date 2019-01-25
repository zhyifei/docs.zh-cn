---
title: 分析 LINQ to SQL 源代码
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 4b1d2d2c54ae99a65f60c96b6330e3f94db6beb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696849"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="dfd46-102">分析 LINQ to SQL 源代码</span><span class="sxs-lookup"><span data-stu-id="dfd46-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="dfd46-103">通过按以下步骤操作，你可以用 Northwind 示例数据库生成 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 源代码。</span><span class="sxs-lookup"><span data-stu-id="dfd46-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="dfd46-104">您可以将对象模型的元素与数据库的元素作一个比较，以便更好地了解不同项的映射方式。</span><span class="sxs-lookup"><span data-stu-id="dfd46-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfd46-105">使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]来生成此代码。</span><span class="sxs-lookup"><span data-stu-id="dfd46-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1.  <span data-ttu-id="dfd46-106">如果您的开发计算机上还没有 Northwind 示例数据库，您可以免费下载它。</span><span class="sxs-lookup"><span data-stu-id="dfd46-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="dfd46-107">有关详细信息，请参阅[下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd46-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2.  <span data-ttu-id="dfd46-108">使用 SqlMetal 命令行工具生成 Visual Basic 或 C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="dfd46-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="dfd46-109">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd46-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="dfd46-110">通过在命令提示符处键入以下命令，您可以生成包含存储过程和函数的 Visual Basic 和 C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="dfd46-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="dfd46-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfd46-111">See also</span></span>
- [<span data-ttu-id="dfd46-112">引用</span><span class="sxs-lookup"><span data-stu-id="dfd46-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="dfd46-113">背景信息</span><span class="sxs-lookup"><span data-stu-id="dfd46-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
