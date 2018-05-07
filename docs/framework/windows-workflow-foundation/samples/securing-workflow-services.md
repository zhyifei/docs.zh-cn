---
title: 保护工作流服务
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: ac02b5ffcfc14ea4aab9e8aafd5f6a4cbcdef3b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="securing-workflow-services"></a>保护工作流服务
安全工作流服务示例演示以下过程：  
  
-   使用 <xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply> 活动创建基本工作流服务。  
  
-   使用 Windows Communication Foundation (WCF) 配置定义安全终结点，以供工作流服务。  
  
-   创建自定义策略内的声明并使用 <xref:System.ServiceModel.ServiceAuthorizationManager> 验证声明。  
  
## <a name="demonstrates"></a>演示  
 使用 WCF 安全保护客户端和工作流服务（基于声明的授权）之间的通信  
  
## <a name="discussion"></a>讨论  
 此示例演示如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全基础结构来像保护正常的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务一样保护工作流服务。 具体来说，它使用自定义声明进行授权。 在此例中，它将 <xref:System.ServiceModel.WSHttpBinding> 和消息模式安全与 Windows 凭据一起使用。  
  
 自定义 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) 检查客户端的 Windows 用户名中是否存在特定的字符。 如果存在该字符，则它创建声明并将其添加到 <xref:System.IdentityModel.Policy.EvaluationContext>。 通过执行此操作，自定义策略将声明，客户端在用户名中包含该字符。 可以在整个调用的生存期查询此声明。 可以在 `Constants.cs` 中查找该字符。  
  
 授权策略在 `SecureWorkFlowAuthZManager` 内查找此声明。 如果它找到此声明，则返回 `true` 并允许工作流继续。 否则，它返回 `false`，这将导致将“访问被拒绝”消息返回给客户端。 其他声明存在于上下文中并且也可以在 `SecureWorkFlowAuthZManager` 内部进行检查。  
  
#### <a name="to-run-this-sample"></a>运行此示例  
  
1.  使用管理员权限运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。  
  
2.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载 SecuringWorkflowServices.sln。  
  
3.  按 CTRL+SHIFT+B 编译解决方案。  
  
4.  将 Service 项目设置为解决方案的启动项目。  
  
5.  按 Ctrl+F5 启动服务而不进行调试。  
  
6.  将 Client 项目设置为解决方案的启动项目。  
  
7.  按 Ctrl+F5 启动客户端而不进行调试。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
