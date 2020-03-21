---
title: 使用性能计数器
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143572"
---
# <a name="using-performance-counters"></a>使用性能计数器
此示例演示如何访问 Windows 通信基础 （WCF） 性能计数器以及如何创建用户定义的性能计数器。 此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)。  
  
> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。  
  
 在此示例中，客户端调用 `ICalculator` 服务的四个方法。 客户端一直执行该操作，直到被用户中断。 该服务保持不变。  
  
 性能计数器在该服务的 Web.config 文件的诊断节中启用，如下面的示例配置所示。  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 此任务也可以使用[配置编辑器工具 （SvcConfigEditor.exe）](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)完成。  
  
 启用性能计数器后，将为服务启用整个 WCF 性能计数器套件。 .NET Framework 自动在三个级别维护性能数据：`ServiceModelService`、`ServiceModelEndpoint` 和 `ServiceModelOperation`。 其中每个级别都有“Calls”（调用）、“Calls per Second”（每秒调用次数）和“Security Calls Not Authorized”（未授权的安全调用次数）等性能计数器。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 要在单计算机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。  
  
### <a name="to-view-performance-data"></a>查看性能数据  
  
1. 通过单击"**开始**、**运行..."、** 输入`perfmon`并单击"**确定"** 或"从控制面板"启动性能监视器工具，选择 **"管理工具**"并双击 **"性能**"。  
  
    > [!NOTE]
    > 在示例代码运行之前无法添加计数器。  
  
2. 选择列出的性能计数器并按 Delete 键以移除它们。  
  
3. 通过右键单击图形窗格并选择 **"添加计数器**"来添加 WCF 计数器。 在 **"添加计数器"** 对话框中，在"性能"对象下拉列表框中选择 **"服务模型操作 3.0.0.0"、服务模型终结点 3.0.0.0 或"服务模型服务 3.0.0.0"。"** 下拉列表框中。 从列表中选择要查看的计数器。  
  
    > [!NOTE]
    > 如果计算机上没有运行 WCF 服务，则服务没有 WCF 性能计数器。  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>使用配置编辑器来启用计数器  
  
1. 打开 SvcConfigEditor.exe 的一个实例。  
  
2. 在"文件"菜单上，单击 **"打开"，** 然后单击"**配置文件..."。**  
  
3. 导航到示例应用程序的服务文件夹并打开 Web.config 文件。  
  
4. 单击"配置树上的**诊断**"。  
  
5. 在 **"诊断"** 窗口中切换**性能计数器**以显示"全部"。  
  
6. 保存该配置文件并退出编辑器。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>另请参阅

- [AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
