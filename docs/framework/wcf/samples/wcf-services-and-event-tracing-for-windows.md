---
title: 针对 Windows 的 WCF 服务和事件跟踪
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: ea917ee87b598fc3ad01df70d9aedfadfd1396a4
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>针对 Windows 的 WCF 服务和事件跟踪
此示例演示如何使用 Windows Communication Foundation (WCF) 中的分析跟踪，将发出事件事件跟踪的 Windows (ETW) 中。 分析跟踪是 WCF 堆栈中允许的生产环境中的 WCF 服务故障排除的关键点处发出的事件。  
  
 WCF 服务中的分析跟踪跟踪，可以打开在生产环境中对性能的影响非常小。 这些跟踪都以事件的形式向 ETW 会话发出。  
  
 此示例包括在其中发出的事件从服务到事件日志，可以使用事件查看器查看基本的 WCF 服务。 还有可能以启动侦听从 WCF 服务的事件的专用的 ETW 会话。 该示例包括一个用于创建专用 ETW 会话的脚本，该会话将事件存储在可以使用事件查看器读取的二进制文件中。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 EtwAnalyticTraceSample.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
     在 Web 浏览器中，单击**Calculator.svc**。 服务的 WSDL 文档的 URI 应出现在浏览器中。 复制该 URI。  
  
     默认情况下，在服务启动侦听端口 1378年上的请求 (http://localhost:1378/Calculator.svc)。  
  
4.  运行 WCF 测试客户端 (WcfTestClient.exe)。  
  
     WCF 测试客户端 (WcfTestClient.exe) 位于\<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录 > \Common7\IDE\ WcfTestClient.exe (默认[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]安装目录为 C:\Program Files\Microsoft Visual Studio 10.0)。  
  
5.  在 WCF 测试客户端，通过选择添加服务**文件**，，然后**添加服务**。  
  
     在输入框中添加终结点地址。 默认值为 http://localhost:1378/Calculator.svc。  
  
6.  打开事件查看器应用程序。  
  
     然后再调用服务，启动事件查看器，并确保事件日志正在侦听从 WCF 服务发出的跟踪事件。  
  
7.  从**启动**菜单上，选择**管理工具**，，然后**事件查看器**。  启用**分析**和**调试**日志。  
  
8.  在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。 右键单击**应用程序服务器-应用程序**，选择**视图**，，然后**显示分析和调试日志**。  
  
     确保**显示分析和调试日志**选项处于选中状态。  
  
9. 启用**分析**日志。  
  
     在事件查看器中的树视图中，导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。 右键单击**分析**和选择**启用日志**。  
  
#### <a name="to-test-the-service"></a>测试服务  
  
1.  切换回 WCF 测试客户端并双击`Divide`并保留默认值，指定分母为 0。  
  
     如果分母为 0，则服务引发错误。  
  
2.  观察从服务发出的事件。  
  
     切换回事件查看器并导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。 右键单击**分析**和选择**刷新**。  
  
     WCF 分析跟踪事件显示在事件查看器中。 请注意，因为服务引发了错误，所以事件查看器中会显示错误跟踪事件。  
  
3.  重复步骤 1 和 2，但是使用有效的输入。 `N2` 参数的值可以为 0 之外的任何数。  
  
     刷新分析通道以查看 WCF 事件，可以看到不包含任何错误事件。  
  
 该示例演示从 WCF 服务发出的分析跟踪事件。  
  
#### <a name="to-cleanup-optional"></a>清理（可选）  
  
1.  打开事件查看器。  
  
2.  导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。 右键单击**分析**和选择**禁用日志**。  
  
3.  导航到**事件查看器**， **Applications and Services Logs**， **Microsoft**， **Windows**，，然后**应用程序服务器-应用程序**。 右键单击**分析**和选择**清除日志**。  
  
4.  选择**清除**选项以清除事件。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>请参阅  
 [AppFabric 监视示例](http://go.microsoft.com/fwlink/?LinkId=193959)
