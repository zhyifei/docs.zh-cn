---
title: HTTP 确认通道
ms.date: 03/30/2017
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
ms.openlocfilehash: d83f3aa590471aa3d83b8f7bd1464ec1e6e106fc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43559538"
---
# <a name="http-acknowledgement-channel"></a>HTTP 确认通道
HTTP 确认通道是一个更改单向消息传递模式的分层通道示例，它允许服务确认或拒绝传入的消息，而不是在接收时自动发送确认。 HTTP 确认通道还允许服务延迟确认，直到服务可以做出将对消息进行处理的业务级别的保证。  
  
## <a name="demonstrates"></a>演示  
 <xref:System.ServiceModel.Channels.ReceiveContext>，分层通道示例（HTTP 确认通道）。  
  
## <a name="discussion"></a>讨论  
 HTTP 确认通道实现 <xref:System.ServiceModel.Channels.ReceiveContext>，通过延迟确认将 HTTP 请求-答复消息传递模式重设为单向模式。 使用此新模式，服务可以确保进行消息处理，方法是以 HTTP OK 状态代码 200 的形式发送确认而不阻止客户端，直到消息处理完成；或者可以 HTTP 内部服务器错误状态代码 500 的形式将失败消息发送到客户端。 例如，服务可在将一条消息写入队列后发送确认，然后继续以异步方式处理该消息。 在此方案中，如果客户端在收到来自服务的确认之前重新发送每条消息，则该客户端可以确信其消息已至少由该服务处理一次。 请注意，如果服务要求通过 HTTP 进行快速异步消息处理而没有任何消息处理保证，则 <xref:System.ServiceModel.Channels.OneWayBindingElement> 是更合适的选择。  
  
 <xref:System.ServiceModel.Channels.ReceiveContext> 用于在确定是否可以在服务上处理该消息时就地保存该消息。 通过在发送 HTTP OK 状态代码的 <xref:System.ServiceModel.Channels.ReceiveContext> 对象上调用 Complete，可以指示服务成功处理消息的能力；通过在 <xref:System.ServiceModel.Channels.ReceiveContext> 对象（发送 HTTP 内部服务器错误状态代码）上调用 `Abandon` 的 <xref:System.ServiceModel.Channels.ReceiveContext> 方法，可以指示服务是否能够处理该消息。  
  
 在此示例中，客户端通过发送员工 ID 来请求处理信息。 在服务端，如果收到的员工 ID 大于 50，则该服务将 HTTP 状态代码 500（内部服务器错误）发送回客户端，否则假定可以成功进行处理，并将 HTTP 状态代码 200（成功）发送到客户端。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  使用管理员权限打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
2.  打开**httpackchannel**解决方案。  
  
3.  启动的新实例**服务**通过右键单击项目中的项目**解决方案资源管理器**，然后选择**调试**，**启动新实例**上下文菜单中。  
  
4.  启动的新实例**客户端**通过右键单击项目中的项目**解决方案资源管理器**，然后选择**调试**，和**启动新实例**上下文菜单中。  
  
5.  启动服务后，在客户端窗口中按 Enter 让客户端向服务发送一条消息。  
  
6.  第一条消息在该服务上进行处理，然后它将一个 HTTP OK 状态代码发送回客户端。  
  
7.  第二条消息不成功，它将一个 HTTP 内部服务器错误代码发送回客户端，这将在客户端上引发 <xref:System.ServiceModel.CommunicationException>。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`
