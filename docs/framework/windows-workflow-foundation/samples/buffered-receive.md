---
title: 缓冲接收
ms.date: 03/30/2017
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
ms.openlocfilehash: ee53edafc94fd5efd4e412b1b9198a8763b79462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518706"
---
# <a name="buffered-receive"></a>缓冲接收
此示例演示如何设置和配置缓冲的接收功能在 Windows Workflow Foundation (WF)。 利用缓冲接收功能，工作流作者可创建工作流，而无需担心接收消息的顺序。 当工作流准备接收消息时，缓冲接收功能将本地缓冲并传递这些消息。  
  
## <a name="demonstrates"></a>演示  
 将缓冲接收与消息传递活动一起使用的无序消息处理。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a>讨论  
 在此示例中，使用实现 Windows Communication Foundation (WCF) 服务[!INCLUDE[wf1](../../../../includes/wf1-md.md)]和都有一个序列的<xref:System.ServiceModel.Activities.Receive>活动。 此工作流建立了一个简单的贷款审批过程模型，在此模型中，工作流应会收到与贷款审批相关的三个通知。 Windows Communication Foundation (WCF) 客户端应用程序的服务的期望的相反顺序发送三个关联的通知。 由于已在服务上启用缓冲接收功能，因此在工作流准备好接收消息时，将在服务上对每条无序消息进行缓冲和处理。  
  
 缓冲接收功能需要来自绑定的 <xref:System.ServiceModel.Activities.ReceiveContent> 支持，因此服务将使用 <xref:System.ServiceModel.NetMsmqBinding>。 由于绑定不需要任何特殊配置，因此将使用默认值。  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 此服务还公开使用 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 的服务的元数据。  
  
 同样，也将使用 <xref:System.ServiceModel.NetMsmqBinding> 配置客户端终结点。 通过使用生成的客户端代码和配置**添加服务引用**Visual Studio 功能。 下面的示例是在 App.config 文件中生成的客户端终结点。  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 此示例要求启用以下 Windows 组件：  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)] 管理功能、元数据库和配置兼容性  
  
3.  万维网服务、应用程序开发功能和 ASP.NET  
  
4.  Microsoft Message Queues (MSMQ) Server  
  
#### <a name="to-set-up-and-build-the-sample"></a>设置和生成示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符下，通过键入 `aspnet_regiis –I` 并按 Enter 来注册 ASP.NET。  
  
2.  以管理员身份运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。  
  
3.  打开 LoanService.sln。  
  
4.  当系统询问你是否要创建的虚拟目录为 LoanService 项目，选择**是**。  
  
#### <a name="to-set-up-the-service-queues"></a>设置服务队列  
  
1.  按 F5 运行 LoanClient 应用程序，这将创建队列并激活 Service1.xamlx 中定义的服务。  
  
2.  打开**计算机管理**通过在命令提示符下运行 Compmgmt.msc 的控制台。  
  
3.  在**计算机管理**控制台中，展开**服务**，**应用程序**，**消息队列**，**专用队列**.  
  
4.  右击 loanservice/service1.xamlx 队列并选择**属性**。  
  
5.  选择**安全**选项卡，并添加**每个人接收邮件**，**扫视消息**和**发送消息**权限。  
  
6.  打开 [!INCLUDE[iis60](../../../../includes/iis60-md.md)] 管理器。  
  
7.  浏览到**服务器**，**站点**， **Default Web site**，**私有**， **LoanService**和选择**高级的选项**  
  
8.  更改**启用的协议**要**http**， **net.msmq**。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  浏览到http://localhost/private/loanservice/service1.xamlx以确保服务正在运行。  
  
2.  按 F5 运行 LoanClient 应用程序。 在工作流完成后，应会将一个 out.txt 文件保存到包含消息交换结果的 C:\Inbox 中。  
  
#### <a name="to-clean-up"></a>清理  
  
1.  打开**计算机管理**通过在命令提示符下运行 Compmgmt.msc 的控制台。  
  
2.  展开**服务**和**应用程序**，**消息队列**，**专用队列**。  
  
3.  删除 loanservice/service1.xamlx 队列。  
  
4.  移除 C:\Inbox 目录。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
