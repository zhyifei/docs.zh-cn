---
title: "演练：创建自定义数据流块类型"
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
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 809b21fa6e1470890011604792d849998dd03ede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>演练：创建自定义数据流块类型
尽管 TPL 数据流库提供了启用各种功能的几个数据流块类型，你还可以创建自定义的块类型。 本文档介绍如何创建实现自定义行为的数据流块类型。  
  
## <a name="prerequisites"></a>先决条件  
 读取[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)在阅读本文档之前。  
  
> [!TIP]
>  TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。 若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。  
  
## <a name="defining-the-sliding-window-dataflow-block"></a>定义滑动窗口数据流块  
 请考虑需要进行缓冲输入的值，并已将其然后滑动窗口方式输出的数据流应用程序。 例如，对于 {0、 1、 2、 3、 4、 5} 的输入的值的三个窗口大小，滑动窗口数据流块都会产生输出数组 {0，1，2}，{1，2，3}，{2，3，4}，和 {3，4，5}。 以下各节描述了两种方法可以创建实现此自定义行为的数据流块类型。 第一种方法使用<xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A>方法，将合并的功能<xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>对象和<xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>构成一个传播器块的对象。 第二种方法定义的类派生自<xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>将合并现有功能，以执行自定义行为。  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>使用封装方法用来定义滑动窗口数据流块  
 下面的示例使用<xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A>方法来创建从目标和源的传播器块。 传播器块，可以将源块和目标块，使其作为数据的发送者和接收者。  
  
 当需要自定义数据流功能，但不是需要提供更多的方法、 属性或字段的类型时，此方法很有用。  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>派生自 IPropagatorBlock 定义滑动窗口数据流块  
 下面的示例演示`SlidingWindowBlock`类。 此类派生自<xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>，以便它可以充当源和数据的目标。 与前面的示例中，`SlidingWindowBlock`类基于现有的数据流块类型。 但是，`SlidingWindowBlock`类还可实现的方法所需的<xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>， <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>，和<xref:System.Threading.Tasks.Dataflow.IDataflowBlock>接口。 转发所有这些方法的工作原理预定义的数据流块类型的成员。 例如，`Post`方法交由工作`m_target`数据成员，也是<xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>对象。  
  
 当你需要自定义数据流功能，并且还需要提供更多的方法、 属性或字段的类型时，此方法很有用。 例如，`SlidingWindowBlock`类还派生自<xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601>以便它可以提供<xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A>和<xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A>方法。 `SlidingWindowBlock`类还通过提供演示扩展性`WindowSize`属性，用于检索的滑动窗口中的元素数。  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>完整示例  
 下面的示例显示此演练的完整代码。 它还演示了如何使用两个滑动窗口块写入块、 读取它，并将打印到控制台的结果的方法中。  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a>编译代码  
 复制代码示例并将其粘贴到 Visual Studio 项目中，或将其粘贴在文件中名为`SlidingWindowBlock.cs`(`SlidingWindowBlock.vb`为[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])，然后在 Visual Studio 命令提示符窗口中运行以下命令。  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## <a name="next-steps"></a>后续步骤  
  
## <a name="see-also"></a>另请参阅  
 [数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
