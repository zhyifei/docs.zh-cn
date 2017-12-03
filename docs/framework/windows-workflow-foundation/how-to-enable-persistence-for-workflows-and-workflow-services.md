---
title: "如何：对工作流和工作流服务启用持久性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1db45ecad833c4c05ba240569da9c85271e0b69e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>如何：对工作流和工作流服务启用持久性
本主题说明如何对工作流和工作流服务启用持久性。  
  
## <a name="enable-persistence-for-workflows"></a>对工作流启用持久性  
 您还可以将与实例存储区相关联**WorkflowApplication**使用<xref:System.Activities.WorkflowApplication.InstanceStore%2A>属性<xref:System.Activities.WorkflowApplication>类。 <xref:System.Activities.WorkflowApplication.Persist%2A> 方法将工作流保存或持久保存到与应用程序关联的实例存储中。 <xref:System.Activities.WorkflowApplication.Unload%2A> 方法将工作流保存到实例存储中，然后从内存中卸载该实例。 **负载**方法将工作流加载到内存使用实例持久性存储区中存储的工作流数据。  
  
 **保留**方法执行以下步骤：  
  
1.  暂停工作流计划程序并等待，直至工作流进入空闲状态。  
  
2.  将工作流持久保存或保存到持久性存储。  
  
3.  恢复工作流计划程序。  
  
 **卸载**方法执行以下步骤：  
  
1.  暂停工作流计划程序并等待，直至工作流进入空闲状态。  
  
2.  将工作流持久保存或保存到持久性存储。  
  
3.  在内存中释放工作流实例。  
  
 这两个**保留**和**卸载**在工作流是在非持久性区域中，直到工作流退出非持久性区域时，将阻止方法。 在完成非持久性区域之后，该方法将继续执行保存或卸载操作。 如果在完成非持久性区域之前发生超时，或者如果持久性进程的时间太长，则将引发 TimeoutException。  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a>在代码中实现工作流服务的持久性  
 **DurableInstancingOptions**的成员<xref:System.ServiceModel.WorkflowServiceHost>类有一个名为**InstanceStore** ，你可以使用关联与实例存储区**WorkflowServiceHost**.  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 当**WorkflowServiceHost**是打开，持久性将自动启用如果**DurableInstancingOptions.InstanceStore**不为 null。  
  
 通常情况下，服务行为提供要通过使用与工作流服务主机的具体实例存储区**InstanceStore**属性。 例如，SqlWorkflowInstanceStoreBehavior 创建的实例**SqlWorkflowInstanceStore**、 配置，并将它分配给**DurableInstancingOptions.InstanceStore**。  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>使用应用程序配置文件实现工作流服务的持久性  
 可以通过将以下代码添加到您 app.config 或 web.config 文件中，使用应用程序配置文件来实现持久性：  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
