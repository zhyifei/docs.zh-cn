---
title: "Null 语义"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3820b1282dda4155946ff22784e5ebe18525b45c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="null-semantics"></a><span data-ttu-id="d7769-102">Null 语义</span><span class="sxs-lookup"><span data-stu-id="d7769-102">Null Semantics</span></span>
<span data-ttu-id="d7769-103">下表提供了指向 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 文档中讨论 `null` （在`Nothing` 中为 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]）问题的各个部分的链接。</span><span class="sxs-lookup"><span data-stu-id="d7769-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) issues are discussed.</span></span>  
  
|<span data-ttu-id="d7769-104">主题</span><span class="sxs-lookup"><span data-stu-id="d7769-104">Topic</span></span>|<span data-ttu-id="d7769-105">描述</span><span class="sxs-lookup"><span data-stu-id="d7769-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d7769-106">SQL CLR 类型不匹配</span><span class="sxs-lookup"><span data-stu-id="d7769-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="d7769-107">本主题的“Null 语义”部分包括以下方面的讨论：三态 SQL Boolean 与两态公共语言运行库 (CLR) <xref:System.Boolean>的比较、文本 `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) 与 `null` (C#) 以及其他类似问题。</span><span class="sxs-lookup"><span data-stu-id="d7769-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="d7769-108">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="d7769-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="d7769-109">本主题的“Null 语义”部分介绍 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]中的 null 比较语义。</span><span class="sxs-lookup"><span data-stu-id="d7769-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="d7769-110">System.String 方法</span><span class="sxs-lookup"><span data-stu-id="d7769-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="d7769-111">本主题的“与 .NET 的差异”部分说明从 <xref:System.String.LastIndexOf%2A> 返回 0 为何意味着字符串为 null 或找到的位置为 0。</span><span class="sxs-lookup"><span data-stu-id="d7769-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="d7769-112">计算数值序列中的值的总和</span><span class="sxs-lookup"><span data-stu-id="d7769-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="d7769-113">说明使用 <xref:System.Linq.Enumerable.Sum%2A> 运算符计算只包含 null 的序列或空序列时，所得结果为何为 `null` （在`Nothing` 中为 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]）。</span><span class="sxs-lookup"><span data-stu-id="d7769-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7769-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7769-114">See Also</span></span>  
 [<span data-ttu-id="d7769-115">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="d7769-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
