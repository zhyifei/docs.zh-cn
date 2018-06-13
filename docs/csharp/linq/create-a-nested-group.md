---
title: 创建嵌套组
description: 如何创建嵌套组。
ms.date: 12/1/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: dd1158bfa1456342fe8967aed5e02ecebae591c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273138"
---
# <a name="create-a-nested-group"></a><span data-ttu-id="0f5b1-103">创建嵌套组</span><span class="sxs-lookup"><span data-stu-id="0f5b1-103">Create a nested group</span></span>

<span data-ttu-id="0f5b1-104">以下示例演示如何在 LINQ 查询表达式中创建嵌套组。</span><span class="sxs-lookup"><span data-stu-id="0f5b1-104">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="0f5b1-105">首先根据学生年级创建每个组，然后根据每个人的姓名进一步细分为小组。</span><span class="sxs-lookup"><span data-stu-id="0f5b1-105">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f5b1-106">示例</span><span class="sxs-lookup"><span data-stu-id="0f5b1-106">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="0f5b1-107">此示例包含对[查询对象集合](query-a-collection-of-objects.md)内示例代码中所定义对象的引用。</span><span class="sxs-lookup"><span data-stu-id="0f5b1-107">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 <span data-ttu-id="0f5b1-108">请注意，需要使用 3 个嵌套的 `foreach` 循环来循环访问嵌套组的内部元素。</span><span class="sxs-lookup"><span data-stu-id="0f5b1-108">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f5b1-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f5b1-109">See also</span></span>  
 [<span data-ttu-id="0f5b1-110">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="0f5b1-110">LINQ Query Expressions</span></span>](index.md)
