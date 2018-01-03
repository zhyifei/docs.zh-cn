---
title: "承载数据服务（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8819e8127d16b83d531dc6bdcd3af88245c695e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-the-data-service-wcf-data-services"></a>承载数据服务（WCF 数据服务）
通过使用[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]，你可以创建服务将数据公开为[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]源。 此数据服务定义为从 <xref:System.Data.Services.DataService%601> 继承的类。 此类提供的功能需要以处理请求消息，执行对数据源中，更新并生成响应消息，根据需要通过[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]。 但是，数据服务无法绑定到，并且网络套接字上侦听传入的 HTTP 请求。 对于这一必需的功能，数据服务依赖于宿主计算机。  
  
 数据服务宿主可代表数据服务执行以下任务：  
  
-   侦听请求并将这些请求路由到数据服务。  
  
-   针对每个请求创建数据服务的一个实例。  
  
-   请求数据服务处理传入的请求。  
  
-   代表数据服务发送响应。  
  
 为了简化承载数据服务时，[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]旨在与 Windows Communication Foundation (WCF) 集成。 数据服务提供一个默认 WCF 实现，充当中的数据服务主机[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序。 因此，您可以通过以下方式之一承载数据服务：  
  
-   在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序中。  
  
-   在支持自承载 WCF 服务的托管应用程序中。  
  
-   在其他某些自定义数据服务宿主中。  
  
## <a name="hosting-a-data-service-in-an-aspnet-application"></a>在 ASP.NET 应用程序中承载数据服务  
 当你使用**添加新项**对话框在 ASP.NET 应用程序，该工具中定义数据服务的 Visual Studio 中在项目中生成两个新文件。 第一个文件的扩展名为 `.svc`，并指示 WCF 运行时如何实例化数据服务。 以下是 Northwind 示例数据服务创建完成此文件的示例[快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):  
  
```  
<%@ ServiceHost Language="C#"   
    Factory="System.Data.Services.DataServiceHostFactory,   
            System.Data.Services, Version=4.0.0.0,   
            Culture=neutral, PublicKeyToken=b77a5c561934e089"   
    Service="NorthwindService.Northwind" %>   
```  
  
 此指令通知应用程序使用 <xref:System.Data.Services.DataServiceHostFactory> 类为命名数据服务类创建服务宿主。  
  
 `.svc` 文件的代码隐藏页包含作为数据服务自身的实现的类，对于 Northwind 示例数据服务，该数据服务的定义如下：  
  
 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
 由于数据服务的行为与 WCF 服务类似，因此数据服务与 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 集成并遵循 WCF Web 编程模型。 有关详细信息，请参阅[WCF 服务和 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)和[WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)。  
  
## <a name="self-hosted-wcf-services"></a>自承载 WCF 服务  
 由于它集成了 WCF 实现，[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]支持自承载作为 WCF 服务的数据服务。 一个服务可以自承载于任何 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 应用程序中，如控制台应用程序。 继承自 <xref:System.Data.Services.DataServiceHost> 的 <xref:System.ServiceModel.Web.WebServiceHost> 类用于实例化位于特定地址的数据服务。  
  
 自承载功能可用于开发和测试目的，因为通过此功能更易于部署服务和解决服务问题。 但是，这种类型的承载不会提供 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 或 Internet Information Services (IIS) 所提供的高级宿主和管理功能。 有关详细信息，请参阅[托管的应用程序中承载](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)。  
  
## <a name="defining-a-custom-data-service-host"></a>定义自定义数据服务主机  
 对于 WCF 宿主实现过于受限的情况，您还可以为数据服务定义自定义宿主。 实现 <xref:System.Data.Services.IDataServiceHost> 接口的任何类都可用作数据服务的网络宿主。 自定义宿主必须实现 <xref:System.Data.Services.IDataServiceHost> 接口，并且能够承担数据服务宿主的以下基本责任：  
  
-   向数据服务提供服务根路径。  
  
-   处理请求，并向相应的 <xref:System.Data.Services.IDataServiceHost> 成员实现响应标头信息。  
  
-   处理由数据服务引发的异常。  
  
-   验证查询字符串中的参数。  
  
## <a name="see-also"></a>请参阅  
 [定义 WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [将数据公开为服务](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)  
 [配置数据服务](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
