---
title: 支持的部署方案
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 6898ec33564a526d0e444502ebb6ed7f142f1856
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347984"
---
# <a name="supported-deployment-scenarios"></a>支持的部署方案

支持在部分受信任的应用程序中使用的 Windows Communication Foundation （WCF）功能子集旨在满足使用 WCF 的某些（但不是全部）方案的要求。 在服务器上，WCF 满足 Internet 规模的共享宿主提供程序（出于安全原因，这些提供程序在 ASP.NET 2.0 Medium 信任权限集中运行第三方应用程序）的要求。 在客户端上，WCF 部分信任支持旨在满足部署技术（例如[ClickOnce 部署](/visualstudio/deployment/clickonce-security-and-deployment)或 WPF 的 XAML 浏览器应用程序技术）的要求，这允许无缝和安全地从不受信任的站点部署桌面应用程序。

## <a name="minimum-permission-requirements"></a>最低权限要求

WCF 支持在以下任一标准命名权限集下运行的应用程序中的功能子集：

- “中等信任”权限

- “Internet 区域”权限

如果尝试在部分受信任的应用程序中使用 WCF 并且具有更严格的权限，则可能会在运行时导致安全异常。

有关这些权限集支持的功能的详细信息，请参阅 [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md)。

## <a name="partial-trust-on-the-server"></a>服务器上的部分信任

ASP.NET Web 应用程序宿主服务的许多商业提供程序要求在其服务器上运行的应用程序在 ASP.NET 2.0 中等信任权限集中运行。 WCF 服务可以在这些环境中运行，前提是它们使用 <xref:System.ServiceModel.BasicHttpBinding>、<xref:System.ServiceModel.WebHttpBinding>或使用传输级安全的 <xref:System.ServiceModel.WSHttpBinding>。

在中等信任宿主环境中运行的 WCF 服务还可以通过将消息发送到其他服务器以响应客户端请求，充当中间层服务。 如果宿主环境已授予应用程序适当的 <xref:System.Net.WebPermission> 以向所需服务器发出出站请求，则支持服务器上的中间层方案。

除了使用支持的 SOAP 绑定之一的 SOAP 消息传递之外，WCF 还支持用于在部分受信任的应用程序中生成 Web 样式服务的 <xref:System.ServiceModel.WebHttpBinding>。 在部分信任环境中，wcf [WEB HTTP 编程模型](wcf-web-http-programming-model.md)、 [Wcf 联合](wcf-syndication.md)以及[AJAX 集成和 JSON 支持](ajax-integration-and-json-support.md)功能都受支持。

工作流服务需要完全信任权限并且不能在部分受信任的应用程序中使用。

有关详细信息，请参阅[如何：在 ASP.NET 2.0 中使用中等信任](https://go.microsoft.com/fwlink/?LinkId=84603)。

## <a name="partial-trust-on-the-client"></a>客户端上的部分信任

在从不受信任的 Internet 网站上下载和运行代码时必须采用某些安全预防措施。 [ClickOnce 部署](/visualstudio/deployment/clickonce-security-and-deployment)和 WPF 的 XAML 浏览器应用程序（XBAP）技术都使用部分信任向不受信任的代码授予有限权限（Internet 区域）。

WCF 可用于与远程服务器进行通信，这些应用程序由[ClickOnce 部署](/visualstudio/deployment/clickonce-security-and-deployment)或 XBAP 部署的部分受信任的应用程序内部。 Internet 区域权限集包括发起主机的 <xref:System.Net.WebPermission>，这允许这些应用程序使用[部分信任功能兼容性](partial-trust-feature-compatibility.md)中所述的任何受支持的 WCF 绑定来与其源服务器进行通信。

## <a name="see-also"></a>另请参阅

- [代码访问安全性](../../misc/code-access-security.md)
- [Windows Presentation Foundation 浏览器承载的应用程序概述](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [部分信任](partial-trust.md)
- [ASP.NET 信任级别和策略文件](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))
