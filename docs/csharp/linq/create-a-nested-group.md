---
title: "创建嵌套组"
description: "如何创建嵌套组。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 232aa46d975d7c338bbc776e3867f2e566601fde
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="create-a-nested-group"></a><span data-ttu-id="5c1c3-104">创建嵌套组</span><span class="sxs-lookup"><span data-stu-id="5c1c3-104">Create a nested group</span></span>

<span data-ttu-id="5c1c3-105">以下示例演示如何在 LINQ 查询表达式中创建嵌套组。</span><span class="sxs-lookup"><span data-stu-id="5c1c3-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="5c1c3-106">首先根据学生年级创建每个组，然后根据每个人的姓名进一步细分为小组。</span><span class="sxs-lookup"><span data-stu-id="5c1c3-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c1c3-107">示例</span><span class="sxs-lookup"><span data-stu-id="5c1c3-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="5c1c3-108">此示例包含对[查询对象集合](query-a-collection-of-objects.md)内示例代码中所定义对象的引用。</span><span class="sxs-lookup"><span data-stu-id="5c1c3-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 <span data-ttu-id="5c1c3-109">请注意，需要使用 3 个嵌套的 `foreach` 循环来循环访问嵌套组的内部元素。</span><span class="sxs-lookup"><span data-stu-id="5c1c3-109">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1c3-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c1c3-110">See also</span></span>  
 [<span data-ttu-id="5c1c3-111">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="5c1c3-111">LINQ Query Expressions</span></span>](index.md)
