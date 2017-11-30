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
helpviewer_keywords: tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c029a763faaa0b4d6ea5612efe079e47415b6fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="fd9aa-102">如何：使用并行任务遍历二叉树</span><span class="sxs-lookup"><span data-stu-id="fd9aa-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="fd9aa-103">下面的示例演示两种方式在其中可以使用并行任务遍历树数据结构。</span><span class="sxs-lookup"><span data-stu-id="fd9aa-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="fd9aa-104">作为练习保留创建树本身。</span><span class="sxs-lookup"><span data-stu-id="fd9aa-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd9aa-105">示例</span><span class="sxs-lookup"><span data-stu-id="fd9aa-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="fd9aa-106">显示的两个方法在功能上等效。</span><span class="sxs-lookup"><span data-stu-id="fd9aa-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="fd9aa-107">通过使用<xref:System.Threading.Tasks.TaskFactory.StartNew%2A>方法来创建和运行任务，你收到一个句柄可以用于等待任务和处理异常的任务。</span><span class="sxs-lookup"><span data-stu-id="fd9aa-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd9aa-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9aa-108">See Also</span></span>  
 [<span data-ttu-id="fd9aa-109">任务并行库 (TPL)</span><span class="sxs-lookup"><span data-stu-id="fd9aa-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
