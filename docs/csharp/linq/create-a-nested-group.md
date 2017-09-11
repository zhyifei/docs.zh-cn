---
title: "创建嵌套组"
description: "如何创建嵌套组。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 361ac1f224c6eef292fcf8434c7e465c9448b19c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-nested-group"></a><span data-ttu-id="6e30e-104">创建嵌套组</span><span class="sxs-lookup"><span data-stu-id="6e30e-104">Create a nested group</span></span>

<span data-ttu-id="6e30e-105">以下示例演示如何在 LINQ 查询表达式中创建嵌套组。</span><span class="sxs-lookup"><span data-stu-id="6e30e-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="6e30e-106">首先根据学生年级创建每个组，然后根据每个人的姓名进一步细分为小组。</span><span class="sxs-lookup"><span data-stu-id="6e30e-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e30e-107">示例</span><span class="sxs-lookup"><span data-stu-id="6e30e-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="6e30e-108">此示例包含对[查询对象集合](query-a-collection-of-objects.md)内示例代码中所定义对象的引用。</span><span class="sxs-lookup"><span data-stu-id="6e30e-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 <span data-ttu-id="6e30e-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e30e-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span></span>  
  
 <span data-ttu-id="6e30e-110">请注意，需要使用 3 个嵌套的 `foreach` 循环来循环访问嵌套组的内部元素。</span><span class="sxs-lookup"><span data-stu-id="6e30e-110">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e30e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e30e-111">See also</span></span>  
 [<span data-ttu-id="6e30e-112">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="6e30e-112">LINQ Query Expressions</span></span>](index.md)

