---
title: WCF 分析跟踪
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: ef636a672d9384e8e3d658f0488cfaadb8d293e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183220"
---
# <a name="wcf-analytic-tracing"></a>WCF 分析跟踪
此示例演示如何将您自己的跟踪事件添加到 Windows 通信基础 （WCF） 写入 ETW 的分析跟踪流中[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]。 跟踪分析是为了便于查看服务，而不会导致较高性能损失。 此示例演示如何使用<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>API 编写与 WCF 服务集成的事件。  
  
 有关 API 的详细信息<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>，请参阅<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>。  
  
 要了解有关 Windows 中事件跟踪的更多信息，请参阅[使用 ETW 改进调试和性能调优](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)。  
  
## <a name="disposing-eventprovider"></a>释放 EventProvider  
 此示例使用 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> 类，该类实现 <xref:System.IDisposable?displayProperty=nameWithType>。 实现 WCF 服务的跟踪时，您可能会在服务的生存期内使用<xref:System.Diagnostics.Eventing.EventProvider>'的资源。 因此，为了便于阅读，此示例永远不会释放已包装的 <xref:System.Diagnostics.Eventing.EventProvider>。 如果出于某种原因，您的服务具有不同的跟踪需求，并且必须释放此资源，则应根据释放非托管资源的最佳做法来修改此示例。 有关处置非托管资源的详细信息，请参阅[实现处置方法](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose)。  
  
## <a name="self-hosting-vs-web-hosting"></a>自承载与 Web 承载  
 对于 Web 托管的服务，WCF 的分析跟踪提供了一个字段，称为"HostReference"，用于标识发出跟踪的服务。 可扩展的用户跟踪可以参与此模型，此示例演示执行该操作的最佳做法。 当管道"&#124;"字符实际出现在生成的字符串中时，Web 主机引用的格式可以是以下任一项：  
  
- 如果该应用程序不在根处。  
  
     \<站点名称>\<应用程序虚拟路径>&#124;\<服务虚拟路径>&#124;\<服务名称>  
  
- 如果该应用程序在根处。  
  
     \<站点名称>&#124;\<服务虚拟路径>&#124;\<服务名称>  
  
 对于自托管服务，WCF 的分析跟踪不会填充"主机引用"字段。 此示例中的 `WCFUserEventProvider` 类在由自承载服务使用时，其行为是一致的。  
  
## <a name="custom-event-details"></a>自定义事件详细信息  
 WCF 的 ETW 事件提供程序清单定义了三个事件，这些事件旨在由 WCF 服务作者从服务代码中发出。 下表显示了这三个事件的分类。  
  
|事件|说明|事件 ID|  
|-----------|-----------------|--------------|  
|UserDefinedInformationEventOccurred|服务中发生的说明内容不是一个问题时发出此事件。 例如，可以在对数据库成功进行调用后发出一个事件。|301|  
|UserDefinedWarningOccurred|发生的问题可能导致将来出现错误时发出此事件。 例如，如果调用数据库失败，但能够通过回退到冗余数据存储区进行恢复，则可以发出一个警告事件。|302|  
|UserDefinedErrorOccurred|服务的行为方式不符合预期时发出此事件。 例如，如果调用数据库失败且无法从其他位置检索数据，则可能会发出一个事件。|303|  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1. 使用 Visual Studio 2012，打开 WCF 分析跟踪 Extens.sln 解决方案文件。  
  
2. 要生成解决方案，按 Ctrl+Shift+B。  
  
3. 若要运行解决方案，请按 Ctrl+F5。  
  
     在 Web 浏览器中，单击**计算器.svc**。 服务的 WSDL 文档的 URI 应出现在浏览器中。 复制该 URI。  
  
4. 运行 WCF 测试客户端 （WcfTestClient.exe）。  
  
     WCF 测试客户端 （WcfTestClient.exe） 位于`\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`。 默认的 Visual Studio 2012`C:\Program Files\Microsoft Visual Studio 10.0`安装 dir 是 。  
  
5. 在 WCF 测试客户端中，通过选择**File**添加服务，然后**添加服务**。  
  
     在输入框中添加终结点地址。  
  
6. 单击 **“确定”**，关闭对话框。  
  
     I计算器服务在 **"我的服务项目**"下的左侧窗格中添加。  
  
7. 打开事件查看器应用程序。  
  
     在调用服务之前，启动事件查看器并确保事件日志侦听从 WCF 服务发出的事件。  
  
8. 在 **"开始"** 菜单中，选择 **"管理工具**"，然后选择**事件查看器**。 启用**分析和****调试**日志。  
  
9. 在事件查看器中的树视图中，导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows，** 然后是**应用程序服务器应用程序**。 右键单击**应用程序服务器应用程序**，选择 **"查看**"，然后**显示分析和调试日志**。  
  
     确保选中 **"显示分析日志"和"调试日志"** 选项。 启用**分析**日志。  
  
     在事件查看器中的树视图中，导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows、****应用程序服务器应用程序**，然后**进行分析**。 右键单击 **"分析"** 并选择**启用日志**。  
  
10. 使用 WCF 测试客户端来测试服务。  
  
    1. 在 WCF 测试客户端中，双击 I计算器服务节点下的 **"添加（"）。**  
  
         **Add（）** 方法显示在包含两个参数的右侧窗格中。  
  
    2. 为第一个参数键入 2，为第二个参数键入 3。  
  
    3. 单击 **"调用"** 以调用该方法。  
  
11. 转到已打开**的事件查看器**窗口。 导航到**事件查看器**，**应用程序和服务日志**，**微软**，**窗口**，**应用程序服务器应用程序**.  
  
12. 右键单击**分析**节点并选择 **"刷新**"。  
  
     事件将显示在右窗格中。  
  
13. 使用 ID 303 来查找事件，然后双击该事件将其打开，并检查其内容。  
  
     此事件由 I计算器`Add()`服务的方法发出，其有效负载等于"2+3=5"。  
  
#### <a name="to-clean-up-optional"></a>清理（可选）  
  
1. 打开“事件查看器”。****  
  
2. 导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows，** 然后是**应用程序-服务器应用程序**。 右键单击 **"分析"** 并选择 **"禁用日志**"。  
  
3. 导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows、****应用程序-服务器应用程序**，然后**分析**。 右键单击 **"分析"** 并选择 **"清除日志**"。  
  
4. 单击 **"清除"** 以清除事件。  
  
## <a name="known-issue"></a>已知问题  
 **事件查看器**中存在一个已知问题，它可能无法解码 ETW 事件。 您可能会看到一条错误消息，指出："找不到源 Microsoft-Windows-\<应用程序服务器应用程序的事件 ID>说明。 未在本地计算机上安装引发此事件的组件，或者安装已损坏。 您可以在本地计算机上安装或修复组件。 如果遇到此错误，请从 **"操作"** 菜单中选择 **"刷新**"。 然后，该事件应能正确解码。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a>另请参阅

- [AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
