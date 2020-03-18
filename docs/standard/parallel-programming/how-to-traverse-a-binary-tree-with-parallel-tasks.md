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
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>如何：使用并行任务遍历二叉树
下面的示例展示了两种使用并行任务遍历树数据结构的方式。 树创建本身是留给大家练练手的。  
  
## <a name="example"></a>示例  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 上面的两种方法在功能上是相当的。 通过使用 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> 方法创建和运行任务，可以从可用于等待任务和处理异常的任务中返回句柄。  
  
## <a name="see-also"></a>另请参阅

- [任务并行库 (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
