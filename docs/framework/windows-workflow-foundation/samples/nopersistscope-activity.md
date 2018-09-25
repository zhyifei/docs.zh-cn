---
title: NoPersistScope 活动
ms.date: 03/30/2017
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
ms.openlocfilehash: 6543756594b6734aec39bf22c5ab6215605341b1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47088140"
---
# <a name="nopersistscope-activity"></a>NoPersistScope 活动
此示例演示如何操作工作流中的不可序列化且可释放的状态。 工作流不会尝试保留不可序列化的状态是很重要的，在工作流中使用过可释放的对象之后清除它们也是很重要的。  
  
## <a name="demonstrates"></a>演示  
 `NoPersistScope` 自定义活动和设计器。  
  
## <a name="using-the-nopersistzone-activity"></a>使用 NoPersistZone 活动  
 当示例工作流运行时，一个称为 `CreateTextWriter` 的自定义活动将创建一个 <xref:System.IO.TextWriter> 类型的对象，并将它保存到工作流变量中。 <xref:System.IO.TextWriter> 是一个 <xref:System.IDisposable> 对象。 此 <xref:System.IO.TextWriter> 被配置为写入到运行示例的目录中的一个名为“out.txt”的文件，<xref:System.Activities.Statements.WriteLine> 活动将会使用它，因为它可以在控制台中回显您键入的任何文本。  
  
 回显逻辑在 `NoPersistScope` 活动（此活动的代码也是此示例的一部分）中运行，用于防止工作流持久化。 如果您在键入`unload`在控制台中，主机将尝试保留工作流实例，但此操作超时，因为工作流保留在`NoPersistScope`。 工作流在使用完 `Dispose` 对象之后，还会利用一个名为 <xref:System.IO.TextWriter> 的自定义活动来释放该对象。 将 `Dispose` 活动放在声明 <xref:System.Activities.Statements.TryCatch.Finally%2A> 变量的 <xref:System.Activities.Statements.TryCatch> 活动的 <xref:System.IO.TextWriter> 块中，以确保：即使在执行 Try 块期间应发生异常，也会运行它。  
  
 您可以键入`exit`以完成工作流实例并退出程序。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 NoPersistZone.sln 解决方案。  
  
2.  若要生成解决方案，请按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。  
  
3.  成功生成之后，按 F5 或选择**开始调试**从**调试**菜单或者，可以按 CTRL + F5 或选择**启动但不调试**从**调试**菜单运行而不进行调试。  
  
#### <a name="to-cleanup-optional"></a>清理（可选）  
  
1.  若要移除 SQL 实例存储，请运行 Cleanup.cmd。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`