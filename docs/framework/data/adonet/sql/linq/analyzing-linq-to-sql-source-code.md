---
title: "分析 LINQ to SQL 源代码"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 730ecffc9543c8a1184bc41ab77d9aec9b53b5a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="f686a-102">分析 LINQ to SQL 源代码</span><span class="sxs-lookup"><span data-stu-id="f686a-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="f686a-103">通过按以下步骤操作，您可以用 Northwind 示例数据库生成 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 源代码。</span><span class="sxs-lookup"><span data-stu-id="f686a-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="f686a-104">您可以将对象模型的元素与数据库的元素作一个比较，以便更好地了解不同项的映射方式。</span><span class="sxs-lookup"><span data-stu-id="f686a-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f686a-105">使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 的开发人员可以使用 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 来生成此代码。</span><span class="sxs-lookup"><span data-stu-id="f686a-105">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1.  <span data-ttu-id="f686a-106">如果您的开发计算机上还没有 Northwind 示例数据库，您可以免费下载它。</span><span class="sxs-lookup"><span data-stu-id="f686a-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="f686a-107">有关详细信息，请参阅[下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="f686a-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2.  <span data-ttu-id="f686a-108">使用 SqlMetal 命令行工具生成 Visual Basic 或 C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="f686a-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="f686a-109">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="f686a-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="f686a-110">通过在命令提示符处键入以下命令，您可以生成包含存储过程和函数的 Visual Basic 和 C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="f686a-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="f686a-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f686a-111">See Also</span></span>  
 [<span data-ttu-id="f686a-112">参考</span><span class="sxs-lookup"><span data-stu-id="f686a-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="f686a-113">背景信息</span><span class="sxs-lookup"><span data-stu-id="f686a-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
