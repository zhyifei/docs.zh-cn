---
title: "如何：取消链接数据流块"
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
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41f1b83fab6ff44e69ac2f010f70e6e254341f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-unlink-dataflow-blocks"></a>如何：取消链接数据流块
本文档介绍如何取消目标数据流块与其源的链接。  
  
> [!TIP]
>  TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。 若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。  
  
## <a name="example"></a>示例  
 下面的示例创建了三个 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象，每个对象调用 `TrySolution` 方法来计算值。 此示例只需使用第一次调用 `TrySolution` 的结果即可完成。  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 为了接收完成的第一个 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 对象的值，该示例定义了 `ReceiveFromAny(T)` 方法。 `ReceiveFromAny(T)` 方法接受一个 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> 对象的数组，并将其中每个对象链接到 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象。 当使用 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 方法将源数据流块链接到目标块时，源会在数据可用时将消息传播到目标。 因为 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 类只接受为其提供的第一条消息，`ReceiveFromAny(T)` 方法通过调用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> 方法来生成其结果。 这将生成提供给 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象的第一条消息。 <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> 方法有一个采用 <xref:System.Boolean> 参数的重载版本 `unlinkAfterOne`，当其设置为 `True` 时，则指示源块在目标收到来自源的一条消息后取消与目标的链接。 取消 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象与其源的链接非常重要，因为当 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象收到一条消息后，便不再需要源数组与 <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> 对象之间的关系。  
  
 为了使 `TrySolution` 的剩余调用能够在其中一个调用计算了一个值后结束，`TrySolution` 方法采用一个 <xref:System.Threading.CancellationToken> 对象，该对象在对 `ReceiveFromAny(T)` 的调用返回后将被取消。 当此 <xref:System.Threading.SpinWait.SpinUntil%2A> 对象取消时，<xref:System.Threading.CancellationToken> 方法将返回。  
  
## <a name="compiling-the-code"></a>编译代码  
 复制示例代码并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为 `DataflowReceiveAny.cs`（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，则为 `DataflowReceiveAny.vb`）的文件中，然后在 Visual Studio 命令提示符窗口中运行以下命令。  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  
  
## <a name="robust-programming"></a>可靠编程  
  
## <a name="see-also"></a>另请参阅  
 [数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
