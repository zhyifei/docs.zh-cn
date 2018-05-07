---
title: 支持的部署方案
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: d0afd12b1c17f9356146aa13c90f8db65ed9ec0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="supported-deployment-scenarios"></a>支持的部署方案
支持在部分受信任的应用程序中使用的 Windows Communication Foundation (WCF) 功能的子集旨在满足某些，而不是所有方案使用 WCF 的要求。 在服务器上，WCF 满足 Internet 规模的要求共享宿主提供运行第三方应用程序中[!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]中等信任权限集出于安全原因。 在客户端，WCF 部分信任支持旨在满足的要求的部署技术如[ClickOnce 部署](http://go.microsoft.com/fwlink/?LinkId=83712)或[!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]的 XAML 浏览器应用程序技术，允许无缝和安全从受信任的网站的桌面应用程序的部署。  
  
## <a name="minimum-permission-requirements"></a>最低权限要求  
 WCF 下任一以下标准命名的权限集运行的应用程序中支持功能的子集：  
  
-   “中等信任”权限  
  
-   “Internet 区域”权限  
  
 尝试使用 WCF 具有限制性更强的权限的部分受信任应用程序可能会导致在运行时的安全异常。  
  
 有关这些权限集支持的功能的详细信息，请参阅 [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)。  
  
## <a name="partial-trust-on-the-server"></a>服务器上的部分信任  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web 应用程序宿主服务的许多商业提供程序要求在其服务器上的应用程序以 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 中等信任权限集来运行。 WCF 服务可以在这些环境中运行，前提是它们使用<xref:System.ServiceModel.BasicHttpBinding>、 <xref:System.ServiceModel.WebHttpBinding>，或 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 使用传输级安全。  
  
 在中等信任宿主环境中运行的 WCF 服务可以还充当中间层服务，将消息发送到其他服务器以响应客户端请求。 如果宿主环境已授予应用程序适当的 <xref:System.Net.WebPermission> 以向所需服务器发出出站请求，则支持服务器上的中间层方案。  
  
 除了使用支持的 SOAP 绑定之一时，SOAP 消息传递，WCF 支持<xref:System.ServiceModel.WebHttpBinding>为部分受信任的应用程序在生成 Web 样式服务。 [WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)， [WCF 联合](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)，和[AJAX 集成和 JSON 支持](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)WCF 功能都支持在部分信任环境中。  
  
 工作流服务需要完全信任权限并且不能在部分受信任的应用程序中使用。  
  
 有关详细信息，请参阅[如何： 在 ASP.NET 2.0 中的使用中等信任](http://go.microsoft.com/fwlink/?LinkId=84603)。  
  
## <a name="partial-trust-on-the-client"></a>客户端上的部分信任  
 在从不受信任的 Internet 网站上下载和运行代码时必须采用某些安全预防措施。 [ClickOnce Deployment](http://go.microsoft.com/fwlink/?LinkId=83712) （ClickOnce 部署）和 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]的 XAML 浏览器应用程序 (XBAP) 技术都可以使用部分信任以对不受信任的代码授予受限权限（Internet 区域）。  
  
 可以使用 WCF 与从部分受信任的应用程序通过以下任一方式部署中的远程服务器通信[ClickOnce 部署](http://go.microsoft.com/fwlink/?LinkId=83712)或 xbap 技术。 Internet 区域权限集包括<xref:System.Net.WebPermission>发起的主机，允许这些应用程序与使用任何支持的 WCF 绑定中所述源服务器进行通信[部分信任功能兼容性](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>请参阅  
 [代码访问安全性](http://go.microsoft.com/fwlink/?LinkId=83717)  
 [Windows Presentation Foundation 浏览器承载的应用程序概述](http://go.microsoft.com/fwlink/?LinkId=98397)  
 [部分信任](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [ASP.Net 中等信任](http://go.microsoft.com/fwlink/?LinkId=69328)
