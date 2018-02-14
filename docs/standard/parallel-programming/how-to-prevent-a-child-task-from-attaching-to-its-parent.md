---
title: "如何：防止子任务附加到其父任务"
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
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2cab2fb9c26a8ddaa868cafebac718e5dfd6baa0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>如何：防止子任务附加到其父任务
本文档演示如何阻止子任务附加到父任务。 在调用由第三方编写的也使用任务的组件时，阻止子任务附加到其父级是有用的。 例如，使用 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> 选项创建 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601> 对象的第三方组件，如果长时间运行或引发未经处理的异常，可能会导致代码中出现问题。  
  
## <a name="example"></a>示例  
 下面的示例对使用默认选项的效果与阻止子任务附加到其父级的效果进行比较。 示例创建了一个 <xref:System.Threading.Tasks.Task> 对象，该对象可调入同时使用 <xref:System.Threading.Tasks.Task> 对象的第三方库。 第三方库使用 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> 选项创建 <xref:System.Threading.Tasks.Task> 对象。 应用程序使用 <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> 选项创建父任务。 该选项指示运行时移除子任务中的 <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> 规范。  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 因为父任务只有在所有子任务完成后才会完成，所以长时间运行的子任务会让整个应用程序执行得非常缓慢。 在此示例中，当应用程序使用默认选项创建父任务时，子任务必须在父任务完成之前完成。 当应用程序使用 <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> 选项时，子任务未附加到父任务。 因此，应用程序可以在父任务完成之后且必须等待子任务完成之前执行其他工作。  
  
## <a name="compiling-the-code"></a>编译代码  
 复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `DenyChildAttach.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `DenyChildAttach.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe DenyChildAttach.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe DenyChildAttach.vb**  
  
## <a name="robust-programming"></a>可靠编程  
  
## <a name="see-also"></a>请参阅  
 [基于任务的异步编程](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
