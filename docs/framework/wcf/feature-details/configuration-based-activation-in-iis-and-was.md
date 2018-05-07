---
title: IIS 和 WAS 中的基于配置的激活
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: aa4a3c682ab1d5d7ca0869fee588934b9ed2bf75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="configuration-based-activation-in-iis-and-was"></a>IIS 和 WAS 中的基于配置的激活
通常当承载于 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 的 Windows Communication Foundation (WCF) 服务时，你必须提供.svc 文件。 .svc 文件包含该服务的名称以及可选的自定义服务主机工厂。 此附加文件将增加可管理性开销。 基于配置的激活功能不要求具有 .svc 文件，因此不会有相关开销。  
  
## <a name="configuration-based-activation"></a>基于配置的激活  
 基于配置的激活接受通常放置在 .svc 文件中的元数据并将其放置在 Web.config 文件中。 在 <`serviceHostingEnvironment`> 没有的元素 <`serviceActivations`> 元素。 在 <`serviceActivations`> 元素是一个或多个 <`add`> 元素、 一个用于每个托管服务。 <`add`> 元素包含使你能够设置的服务以及服务类型或服务主机工厂的相对地址的属性。 下面的配置示例代码演示如何使用此节。  
  
> [!NOTE]
>  每个 <`add`> 元素必须指定服务或工厂特性。 允许同时指定服务特性和工厂特性。  
  
```xml  
<serviceHostingEnvironment>  
  <serviceActivations>  
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>  
  </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
 在 Web.config 文件中使用此节，您可以将服务源代码放置在应用程序的 App_Code 目录中，或者将已编译的程序集放置在应用程序的 Bin 目录中。  
  
> [!NOTE]
>  -   使用基于配置的激活时，不支持 .svc 文件中的内联代码。  
> -   `relativeAddress`属性必须设置为一个相对地址，如"\<子目录 > / service.svc"或"~ /\<子 directory/service.svc"。  
> -   如果注册的相对地址不具有与 WCF 关联的已知扩展，则会引发配置异常。  
> -   指定的相对地址相对于虚拟应用程序的根目录。  
> -   由于配置具有分层模型，因此虚拟应用程序继承计算机和站点级别的已注册相对地址。  
> -   配置文件中的注册优先于 .svc、.xamlx、.xoml 或其他文件中的设置。  
> -   发送到 IIS/WAS 的 URI 中的所有“\”（反斜杠）都会自动转换为“/”（正斜杠）。 如果添加的相对地址中含有“\”并且您向 IIS 发送的 URI 使用该相对地址，则反斜杠会转换为正斜杠，并且 IIS 无法将其与相对地址进行匹配。 IIS 会发出跟踪信息，指示未找到任何匹配项。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>  
 [托管服务](../../../../docs/framework/wcf/hosting-services.md)  
 [承载工作流服务概述](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 [\<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)  
 [Windows Server App Fabric 承载功能](http://go.microsoft.com/fwlink/?LinkId=201276)
