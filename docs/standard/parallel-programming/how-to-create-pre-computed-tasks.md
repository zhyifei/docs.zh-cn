---
title: "如何：创建预先计算的任务"
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
- tasks, creating pre-computed
ms.assetid: a73eafa2-1f49-4106-a19e-997186029b58
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 262aa626e9e426da94de0d2ad5f2ef04a5bbc5f3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-pre-computed-tasks"></a>如何：创建预先计算的任务
本文档介绍如何使用 <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> 方法检索缓存中包含的异步下载操作的结果。 <xref:System.Threading.Tasks.Task.FromResult%2A> 方法返回一个将所提供的值作为其 <xref:System.Threading.Tasks.Task%601> 属性的已完成的 <xref:System.Threading.Tasks.Task%601.Result%2A> 对象。 执行返回 <xref:System.Threading.Tasks.Task%601> 对象的异步运算，且已计算该 <xref:System.Threading.Tasks.Task%601> 对象的结果时，此方法将十分有用。  
  
## <a name="example"></a>示例  
 下面的示例从 Web 下载字符串。 它定义了 `DownloadStringAsync` 方法。 此方法从 Web 异步下载字符串。 此示例还使用 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 对象来缓存先前操作的结果。 如果此缓存中包含输入的地址，`DownloadStringAsync` 会使用 <xref:System.Threading.Tasks.Task.FromResult%2A> 方法来生成包含位于该地址的内容的 <xref:System.Threading.Tasks.Task%601> 对象。 否则，`DownloadStringAsync` 从 Web 下载文件并将结果添加到缓存中。  
  
 [!code-csharp[TPL_CachedDownloads#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cacheddownloads/cs/cacheddownloads.cs#1)]
 [!code-vb[TPL_CachedDownloads#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cacheddownloads/vb/cacheddownloads.vb#1)]  
  
 此示例计算两次下载多个字符串需要的时间。 与第一组下载操作相比，第二组下载操作应该会花费较少的时间，因为结果已包含在缓存中。 <xref:System.Threading.Tasks.Task.FromResult%2A> 方法可以使 `DownloadStringAsync` 方法创建包含这些预计算结果的 <xref:System.Threading.Tasks.Task%601> 对象。  
  
## <a name="compiling-the-code"></a>编译代码  
 复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `CachedDownloads.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `CachedDownloads.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe CachedDownloads.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe CachedDownloads.vb**  
  
## <a name="robust-programming"></a>可靠编程  
  
## <a name="see-also"></a>请参阅  
 [基于任务的异步编程](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
