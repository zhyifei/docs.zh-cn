---
title: 可靠安全配置文件
ms.date: 03/30/2017
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 65523fcc1d08bd48a432e6cf599dfcb73ade8747
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="reliable-secure-profile"></a>可靠安全配置文件
此示例演示如何编写 WCF 和[可靠安全配置文件](http://go.microsoft.com/fwlink/?LinkId=178140)(RSP)。 此示例演示如何实现[建立连接](http://go.microsoft.com/fwlink/?LinkId=178141)通道以及可靠消息传递和 （可选） 可由基于 RSP 规范的创建一个可靠的安全绑定的安全通道。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>讨论  
 此示例演示可靠的异步双向消息交换方案。 该服务有双工协定，客户端实现双工回调协定。 客户端向服务发出请求，应在单独的连接上响应该请求。 会以可靠方式发送请求消息。 客户端不希望在其关闭时打开侦听终结点。 因此，它将轮询具有“建立连接”请求的服务，以使服务在此“建立连接”请求的反向通道上发送回响应。 此示例演示如何通过 HTTP 进行安全可靠的双工通信，而无需客户端公开侦听终结点（并创建防火墙例外）。  
  
## <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  打开**reliablesecureprofile**解决方案。  
  
2.  右键单击**服务**项目中**解决方案资源管理器**，选择**调试**，**启动新实例**从上下文菜单。 这会启动服务主机。  
  
3.  右键单击**客户端**项目中**解决方案资源管理器**，选择**调试**，**启动新实例**从上下文菜单。 这会启动客户端。  
  
4.  在客户端控制台窗口中出现提示时键入任意字符串，然后单击 ENTER。这会将输入字符串发送到计算此字符串的哈希的服务。  
  
5.  服务回调双工回调协定操作以在客户端控制台窗口中显示结果时，可在客户端窗口中查看结果。 服务中会进行有意的延迟，以模拟长时间运行的处理数据操作。  
  
6.  监视 HTTP 通信（通过任何联机网络监视工具，如网络监视器和 Fiddler 等）会显示按照可靠安全配置文件在客户端和服务之间建立通信序列，以及客户端如何轮询具有“建立连接”请求的服务。 服务准备好发送回经过处理的响应时，会使用上一个“建立连接”请求的反向通道来发送回结果。  
  
7.  在服务控制台窗口中按 ENTER 关闭服务。 在客户端控制台窗口中按 ENTER 关闭客户端。
