---
title: 可靠安全配置文件
ms.date: 03/30/2017
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
ms.openlocfilehash: 9ddd0d78396bba6712650620e6b46c62f13337e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144209"
---
# <a name="reliable-secure-profile"></a>可靠安全配置文件

此示例演示如何组合 WCF 和[可靠安全配置文件 （RSP）。](http://www.ws-i.org/Profiles/ReliableSecureProfile-1.0.html) 此示例演示了["使连接](http://docs.oasis-open.org/ws-rx/wsmc/200702/wsmc-1.0-spec-cs-01.pdf)通道"的实现，该通道可以与可靠消息一起组合，并选择性地组成安全通道，以基于 RSP 规范创建可靠的安全绑定。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a>讨论区  
 此示例演示可靠的异步双向消息交换方案。 该服务有双工协定，客户端实现双工回调协定。 客户端向服务发出请求，应在单独的连接上响应该请求。 会以可靠方式发送请求消息。 客户端不希望在其关闭时打开侦听终结点。 因此，它将轮询具有“建立连接”请求的服务，以使服务在此“建立连接”请求的反向通道上发送回响应。 此示例演示如何通过 HTTP 进行安全可靠的双工通信，而无需客户端公开侦听终结点（并创建防火墙例外）。  
  
## <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 打开**可靠的安全配置文件**解决方案。  
  
2. 右键单击**解决方案资源管理器**中的**服务**项目 ，从上下文菜单中选择 **"调试****"，从上下文菜单中启动新实例**。 这会启动服务主机。  
  
3. 右键单击**解决方案资源管理器**中的**客户端**项目 ，从上下文菜单中选择**调试**，**从上下文菜单中启动新实例**。 这会启动客户端。  
  
4. 在客户端控制台窗口中出现提示时键入任意字符串，然后单击 ENTER。这会将输入字符串发送到计算此字符串的哈希的服务。  
  
5. 服务回调双工回调协定操作以在客户端控制台窗口中显示结果时，可在客户端窗口中查看结果。 服务中会进行有意的延迟，以模拟长时间运行的处理数据操作。  
  
6. 监视 HTTP 通信（通过任何联机网络监视工具，如网络监视器和 Fiddler 等）会显示按照可靠安全配置文件在客户端和服务之间建立通信序列，以及客户端如何轮询具有“建立连接”请求的服务。 服务准备好发送回经过处理的响应时，会使用上一个“建立连接”请求的反向通道来发送回结果。  
  
7. 在服务控制台窗口中按 ENTER 关闭服务。 在客户端控制台窗口中按 ENTER 关闭客户端。
