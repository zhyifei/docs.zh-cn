---
title: 如何：使用并行任务遍历二叉树
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: b79337e6ee8057506ff87c696cecd6b038eeebfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141641"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="b10a8-102">如何：使用并行任务遍历二叉树</span><span class="sxs-lookup"><span data-stu-id="b10a8-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="b10a8-103">下面的示例展示了两种使用并行任务遍历树数据结构的方式。</span><span class="sxs-lookup"><span data-stu-id="b10a8-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="b10a8-104">树创建本身是留给大家练练手的。</span><span class="sxs-lookup"><span data-stu-id="b10a8-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b10a8-105">示例</span><span class="sxs-lookup"><span data-stu-id="b10a8-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="b10a8-106">上面的两种方法在功能上是相当的。</span><span class="sxs-lookup"><span data-stu-id="b10a8-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="b10a8-107">通过使用 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> 方法创建和运行任务，可以从可用于等待任务和处理异常的任务中返回句柄。</span><span class="sxs-lookup"><span data-stu-id="b10a8-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b10a8-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b10a8-108">See also</span></span>

- [<span data-ttu-id="b10a8-109">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="b10a8-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
