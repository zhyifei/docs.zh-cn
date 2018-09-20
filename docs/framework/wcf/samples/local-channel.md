---
title: 本地通道
ms.date: 03/30/2017
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
ms.openlocfilehash: 731fcfde52a6b1277551f7d70f795c721fc99dd8
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002705"
---
# <a name="local-channel"></a>本地通道
本地通道是使用相同的应用程序域内进行通信的 Windows Communication Foundation (WCF) 传输通道。 对于客户端和服务在相同应用程序域内运行，并且必须避免典型 WCF 通道堆栈（消息的序列化和反序列化）开销的方案，这十分有用。  
  
## <a name="demonstrates"></a>演示  
 本地通道  
  
## <a name="discussion"></a>讨论  
 示例由两个项目文件组成：  
  
-   **LocalChannel**： 当前的应用程序域中的本地通道的编程表示形式。 在此项目中，发送组件将消息放置在内存中队列中，接收组件将消息从队列中取出以进行接收。  
  
-   **ClientAndService**： 此项目承载在控制台应用程序服务，然后运行客户端相同的应用程序域中调用中的服务。  
  
 本地通道设计跳过通道堆栈和序列化过程以提高速度。 本地传输通道使用队列实现，以将服务调用从客户端传输到服务并将值返回到客户端。 示例复制对象，而不是对参数和返回值进行序列化。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  生成并运行 LocalChannel 解决方案。  
  
2.  服务主机启动，客户端使用本地通道调用服务。 出现控制台窗口，以显示服务调用的结果。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
