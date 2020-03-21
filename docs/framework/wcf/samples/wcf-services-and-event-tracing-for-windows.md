---
title: 针对 Windows 的 WCF 服务和事件跟踪
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183203"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>针对 Windows 的 WCF 服务和事件跟踪
此示例演示如何使用 Windows 通信基础 （WCF） 中的分析跟踪在 Windows 事件跟踪 （ETW） 中发出事件。 分析跟踪是在 WCF 堆栈中的关键点发出的事件，允许在生产环境中对 WCF 服务进行故障排除。

 WCF 服务中的分析跟踪是可在生产环境中打开的跟踪，对性能的影响最小。 这些跟踪都以事件的形式向 ETW 会话发出。

 此示例包括一个基本的 WCF 服务，其中事件从服务发送到事件日志，可以使用事件查看器查看。 还可以启动专用 ETW 会话，该会话侦听来自 WCF 服务的事件。 该示例包括一个用于创建专用 ETW 会话的脚本，该会话将事件存储在可以使用事件查看器读取的二进制文件中。

#### <a name="to-use-this-sample"></a>使用此示例

1. 使用 Visual Studio 2012，打开 EtwAnalyticTraceSample.sln 解决方案文件。

2. 要生成解决方案，按 Ctrl+Shift+B。

3. 若要运行解决方案，请按 Ctrl+F5。

     在 Web 浏览器中，单击**计算器.svc**。 服务的 WSDL 文档的 URI 应出现在浏览器中。 复制该 URI。

     默认情况下，服务开始侦听端口 1378`http://localhost:1378/Calculator.svc`上的请求。

4. 运行 WCF 测试客户端 （WcfTestClient.exe）。

     WCF 测试客户端 （WcfTestClient.exe） 位于`\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`。  默认的 Visual Studio 2012`C:\Program Files\Microsoft Visual Studio 10.0`安装 dir 是 。

5. 在 WCF 测试客户端中，通过选择**File**添加服务，然后**添加服务**。

     在输入框中添加终结点地址。 默认为 `http://localhost:1378/Calculator.svc`。

6. 打开事件查看器应用程序。

     在调用服务之前，启动事件查看器并确保事件日志侦听从 WCF 服务发出的事件。

7. 在 **"开始"** 菜单中，选择 **"管理工具**"，然后选择**事件查看器**。  启用**分析和****调试**日志。

8. 在事件查看器中的树视图中，导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows，** 然后是**应用程序服务器应用程序**。 右键单击**应用程序服务器应用程序**，选择 **"查看**"，然后**显示分析和调试日志**。

     确保选中 **"显示分析日志"和"调试日志"** 选项。

9. 启用**分析**日志。

     在事件查看器中的树视图中，导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows，** 然后是**应用程序服务器应用程序**。 右键单击 **"分析"** 并选择**启用日志**。

#### <a name="to-test-the-service"></a>测试服务

1. 切换回 WCF 测试客户端并双击`Divide`并保留默认值，其中指定分母 0。

     如果分母为 0，则服务引发错误。

2. 观察从服务发出的事件。

     切换回事件查看器，并导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows，** 然后是**应用程序服务器应用程序**。 右键单击 **"分析"** 并选择 **"刷新**"。

     WCF 分析跟踪事件显示在事件查看器中。 请注意，因为服务引发了错误，所以事件查看器中会显示错误跟踪事件。

3. 重复步骤 1 和 2，但是使用有效的输入。 `N2` 参数的值可以为 0 之外的任何数。

     刷新分析通道以查看 WCF 事件，可以看到不包含任何错误事件。

 该示例演示从 WCF 服务发出的分析跟踪事件。

#### <a name="to-cleanup-optional"></a>清理（可选）

1. 打开事件查看器。

2. 导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows，** 然后是**应用程序-服务器应用程序**。 右键单击 **"分析"** 并选择 **"禁用日志**"。

3. 导航到**事件查看器**、**应用程序和服务日志**、**微软****、Windows，** 然后是**应用程序-服务器应用程序**。 右键单击 **"分析"** 并选择 **"清除日志**"。

4. 选择 **"清除"** 选项以清除事件。

> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>另请参阅

- [AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
