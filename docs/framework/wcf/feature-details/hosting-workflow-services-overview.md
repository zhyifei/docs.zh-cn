---
title: "承载工作流服务概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c38cd352eb860982b9b1e3aa32daa7aeeee9ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-workflow-services-overview"></a>承载工作流服务概述
工作流服务必须进行承载才能执行。 <xref:System.ServiceModel.WorkflowServiceHost> 是现成的工作流主机，可支持多个实例、配置和 WCF 消息传递（虽然工作流无需使用消息传递即可进行承载）。  它还通过一组服务行为集成了持久性、跟踪和实例控件。  正如 WCF 的 <xref:System.ServiceModel.ServiceHost> 一样，<xref:System.ServiceModel.WorkflowServiceHost> 可以在任何托管 .NET 应用程序中自承载，或是在 IIS/WAS 中进行 Web 承载（作为 .xamlx 文件）。  本节中的主题描述如何承载工作流服务。  
  
## <a name="in-this-section"></a>本节内容  
 [承载工作流服务](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 描述承载工作流服务。  
  
 [工作流服务主机内部机制](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 描述 <xref:System.ServiceModel.WorkflowServiceHost> 如何处理传入消息。  
  
 [工作流服务主机可扩展性](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 描述如何扩展工作流服务主机的功能。  
  
 [工作流控制终结点](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 描述如何定义使您可以创建工作流实例的终结点。  
  
 [如何： 承载非服务工作流在 IIS 中](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 演示在 IIS 中承载不是工作流服务的工作流。  
  
 [如何： 承载工作流服务使用 Windows Server App Fabric](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 演示如何在 Windows Server App Fabric 中承载现有工作流服务。  
  
 [配置 WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 描述如何控制持久性、跟踪、空闲和未经处理的异常行为。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a>相关章节  
 [工作流服务](../../../../docs/framework/wcf/feature-details/workflow-services.md)
