---
title: "本地方法调用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d652072d5f2e0e0cfc74d627b573389864bca9dc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="local-method-calls"></a><span data-ttu-id="63d02-102">本地方法调用</span><span class="sxs-lookup"><span data-stu-id="63d02-102">Local Method Calls</span></span>
<span data-ttu-id="63d02-103">本地方法调用是在对象模型中执行的方法调用。</span><span class="sxs-lookup"><span data-stu-id="63d02-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="63d02-104">远程方法调用是 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 转换成 SQL 并传输至数据库引擎进行执行的方法调用。</span><span class="sxs-lookup"><span data-stu-id="63d02-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="63d02-105">当 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 无法将调用转换成 SQL 时，将需要本地方法调用。</span><span class="sxs-lookup"><span data-stu-id="63d02-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="63d02-106">否则会引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="63d02-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="63d02-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="63d02-107">Example 1</span></span>  
 <span data-ttu-id="63d02-108">在下面的示例中，`Order` 类将映射到 Northwind 示例数据库中的 Orders 表。</span><span class="sxs-lookup"><span data-stu-id="63d02-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="63d02-109">将一个本地实例方法添加到了此类。</span><span class="sxs-lookup"><span data-stu-id="63d02-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="63d02-110">在查询 1 中，`Order` 类的构造函数是在本地执行的。</span><span class="sxs-lookup"><span data-stu-id="63d02-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="63d02-111">在查询 2 中，如果 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 尝试将 `LocalInstanceMethod()` 转换成 SQL，此尝试将失败并且将引发 <xref:System.InvalidOperationException> 异常。</span><span class="sxs-lookup"><span data-stu-id="63d02-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="63d02-112">但由于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 为本地方法调用提供了支持，查询 2 将不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="63d02-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="63d02-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="63d02-113">See Also</span></span>  
 [<span data-ttu-id="63d02-114">背景信息</span><span class="sxs-lookup"><span data-stu-id="63d02-114">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
