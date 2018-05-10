---
title: 分层配置模型
ms.date: 03/30/2017
ms.assetid: 28dcc698-226c-4b77-9e51-8bf45a36216c
ms.openlocfilehash: 233a8d4ba36835ab26e0c4a8cd044cf60d497a0b
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="hierarchical-configuration-model"></a>分层配置模型
此示例演示如何实现服务配置文件的层次结构。 它还演示如何从层次结构中较高的级别继承绑定、服务行为和终结点行为。  
  
## <a name="sample-details"></a>示例详细信息  
 WCF 中的开发的功能之一[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]是分层配置模型中的改进。 分层配置模型的一个示例是通过 Machine.config -> Rootweb.config -> Web.config 定义的模型。在 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] 中，那些在配置层次结构的较高级别中定义的绑定和行为将添加到没有显式配置的服务中。 此示例演示如何通过依赖于在计算机或应用程序级别定义的配置元素来简化服务配置。  
  
 此示例包含在层次结构的三个级别中定义的九项服务。 `Service1` 位于根目录中。 `Service2` 和 `Service3` 类继承 `Service1` 中的默认元素。 `Service4`、`Service5`、 `Service6` 和 `Service7` 在层次结构的第三层定义，继承 `Service3` 中的默认元素。 最后，`Service10` 和 `Service11` 位于层次结构的第四层。  
  
 所有这些服务都实现 `IDesc` 协定。 下面是 `IDesc` 接口的定义，它显示了此接口中公开的方法。 `IDesc` 接口在 Service1.cs 中定义。  
  
```  
// Define a service contract  
[ServiceContract(Namespace="http://Microsoft.Samples.ConfigHierarchicalModel")]  
public interface IDesc  
{  
    [OperationContract]  
    List<string> ListEndpoints();  
    [OperationContract]  
    List<string> ListServiceBehaviors();  
    [OperationContract]  
    List<string> ListEndpointBehaviors();  
}  
```  
  
 这些服务对方法的实现是很简单直接的。 `ListEndpoints` 循环访问所有服务终结点，并返回该服务具有的所有终结点的列表。 `ListServiceBehaviors` 循环访问所有添加到服务的行为，并返回与服务相关联的所有服务行为的列表。 `ListEndpointBehaviors` 的行为方式类似于 `ListServiceBehaviors`，但它返回的是终结点行为的列表。  
  
 通过此实现，客户端可以知道服务公开了多少终结点，以及哪些服务行为和终结点行为已添加到该服务中。 已作为该示例的一部分实现的客户端在该解决方案中添加一个对所有服务的服务引用，并为每个服务显示这些元素。  
  
## <a name="to-use-this-sample"></a>使用此示例  
  
#### <a name="to-run-the-client"></a>运行客户端  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 ConfigHierarchicalModel.sln 文件。  
  
2.  客户端项目尚未设置为启动项目，请执行下列步骤。  
  
    1.  在**解决方案资源管理器**，右键单击该解决方案，然后选择**属性**。  
  
    2.  在**通用属性**，选择**启动项目**，然后单击**单启动项目**。  
  
    3.  从**单启动项目**下拉列表中，选择**客户端**。  
  
    4.  单击**确定**关闭对话框。  
  
3.  要生成此示例，按 Ctrl+Shift+B。  
  
4.  若要运行客户端，请按 Ctrl+F5。  
  
> [!NOTE]
>  如果这些步骤不起作用，则通过以下步骤来确保已正确设置环境。  
>   
>  1.  确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
> 2.  若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
> 3.  若要在一个或多个计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigHierarchicalModel`  
  
## <a name="see-also"></a>请参阅  
 [AppFabric 管理示例](http://go.microsoft.com/fwlink/?LinkId=193960)
