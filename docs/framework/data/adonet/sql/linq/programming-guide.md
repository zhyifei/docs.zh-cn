---
title: 编程指南
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 32e62899c13be3f2f08bef7e882d5b9c4d11fda2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794441"
---
# <a name="programming-guide"></a><span data-ttu-id="92c5a-102">编程指南</span><span class="sxs-lookup"><span data-stu-id="92c5a-102">Programming Guide</span></span>
<span data-ttu-id="92c5a-103">本节包含有关如何创建和使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象模型的信息。</span><span class="sxs-lookup"><span data-stu-id="92c5a-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="92c5a-104">如果使用的 Visual Studio，还可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来执行许多上述相同的任务。</span><span class="sxs-lookup"><span data-stu-id="92c5a-104">If you are using Visual Studio, you can also use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="92c5a-105">您还可以搜索 Microsoft Docs 特定问题，并且可以参与[LINQ 论坛](https://go.microsoft.com/fwlink/?LinkId=76488)，可以与专家们讨论更复杂的主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="92c5a-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="92c5a-106">最后， [LINQ to SQL： 关系数据的.net 语言集成查询](https://go.microsoft.com/fwlink/?LinkId=93205)白皮书详细介绍[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]技术并包含 Visual Basic 和 C# 代码示例。</span><span class="sxs-lookup"><span data-stu-id="92c5a-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92c5a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="92c5a-107">In This Section</span></span>  
 [<span data-ttu-id="92c5a-108">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="92c5a-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="92c5a-109">说明如何生成对象模型。</span><span class="sxs-lookup"><span data-stu-id="92c5a-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="92c5a-110">与数据库通信</span><span class="sxs-lookup"><span data-stu-id="92c5a-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="92c5a-111">说明如何将 <xref:System.Data.Linq.DataContext> 对象用作与数据库交互的媒介。</span><span class="sxs-lookup"><span data-stu-id="92c5a-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="92c5a-112">查询数据库</span><span class="sxs-lookup"><span data-stu-id="92c5a-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="92c5a-113">说明如何在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中执行查询，并提供了许多示例。</span><span class="sxs-lookup"><span data-stu-id="92c5a-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="92c5a-114">进行和提交数据更改</span><span class="sxs-lookup"><span data-stu-id="92c5a-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="92c5a-115">说明如何更改数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="92c5a-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="92c5a-116">调试支持</span><span class="sxs-lookup"><span data-stu-id="92c5a-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="92c5a-117">说明可用于调试 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 项目的支持。</span><span class="sxs-lookup"><span data-stu-id="92c5a-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="92c5a-118">背景信息</span><span class="sxs-lookup"><span data-stu-id="92c5a-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="92c5a-119">包括针对更高级用户的附加项，如并发冲突解决方法、创建新数据库等。</span><span class="sxs-lookup"><span data-stu-id="92c5a-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="92c5a-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="92c5a-120">Related Sections</span></span>  
 [<span data-ttu-id="92c5a-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="92c5a-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="92c5a-122">提供指向一些主题的链接，这些主题阐释了 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 技术并演示了一些功能。</span><span class="sxs-lookup"><span data-stu-id="92c5a-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="92c5a-123">存储过程</span><span class="sxs-lookup"><span data-stu-id="92c5a-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="92c5a-124">包含指向一些主题的链接，这些主题演示了如何使用存储过程。</span><span class="sxs-lookup"><span data-stu-id="92c5a-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="92c5a-125">LINQ 简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="92c5a-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="92c5a-126">提供了一些资源可帮助您开始了解到 SQL 使用 LINQ C#。</span><span class="sxs-lookup"><span data-stu-id="92c5a-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="92c5a-127">LINQ 简介 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92c5a-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="92c5a-128">提供的资源可帮助您开始了解有关 LINQ to SQL 使用 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="92c5a-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
