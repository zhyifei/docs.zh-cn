---
title: "如何：使用并行任务遍历二叉树"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0196d82dd46a105f7cf1db0f9333a5d28afe559b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="eeff0-102">如何：使用并行任务遍历二叉树</span><span class="sxs-lookup"><span data-stu-id="eeff0-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="eeff0-103">下面的示例展示了两种使用并行任务遍历树数据结构的方式。</span><span class="sxs-lookup"><span data-stu-id="eeff0-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="eeff0-104">树创建本身是留给大家练练手的。</span><span class="sxs-lookup"><span data-stu-id="eeff0-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeff0-105">示例</span><span class="sxs-lookup"><span data-stu-id="eeff0-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="eeff0-106">上面的两种方法在功能上是相当的。</span><span class="sxs-lookup"><span data-stu-id="eeff0-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="eeff0-107">通过使用 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> 方法创建和运行任务，可以从可用于等待任务和处理异常的任务中返回句柄。</span><span class="sxs-lookup"><span data-stu-id="eeff0-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeff0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="eeff0-108">See Also</span></span>  
 [<span data-ttu-id="eeff0-109">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="eeff0-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
