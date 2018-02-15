---
title: "现代 web 应用程序的特征"
description: "设计使用 ASP.NET Core 和 Azure 的现代 Web 应用程序 |现代 web 应用程序的特征"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ecef23870ac547f4b4066628da71f8af98c91b27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="characteristics-of-modern-web-applications"></a>现代 Web 应用程序的特征

> "… 正确设计功能附带经济地。 这种方法是棘手，但会继续成功。"  
> _\- Dennis Ritchie_

## <a name="summary"></a>摘要

现代 web 应用程序具有更高版本的用户期望和比以往更高的要求。 用户期望今天的 web 应用程序要提供全天候从任意位置在世界中，且可从几乎任何设备或屏幕大小。 Web 应用程序必须是安全、 灵活且可缩放以满足的需求的高峰需求。 越来越多，应由基于客户端使用 JavaScript，并有效地通信通过 web Api 的丰富的用户体验处理复杂的方案。

ASP.NET 核心进行了优化的现代 web 应用程序和基于云的托管方案。 其模块化设计允许应用程序依赖于它们实际使用，提高应用程序安全和性能，同时减少资源的托管要求这些功能。

## <a name="reference-application-eshoponweb"></a>引用应用程序： eShopOnWeb

本指南包括一个引用应用程序中， *eShopOnWeb*，演示的一些原则和建议。 应用程序是简单的在线商店支持浏览 shirts、 coffee 杯子和其他市场营销的项的目录。 引用应用程序是有意简单以使其更易于理解。

**图 2-1。** eShopOnWeb

![](./media/image2-1.png)

> ### <a name="reference-application"></a>引用应用程序
> - **eShopOnWeb**  
> <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>云托管的和可缩放

ASP.NET 核心进行了优化的云 （公有云、 私有云、 任何云），因为它是低内存和高吞吐量。 ASP.NET 核心应用程序的较小需求量意味着可以托管多个相同的硬件上，使用支付-作为-你无法在云托管服务时为较少的资源付费。 更高吞吐量意味着你可以提供更多的客户从应用程序提供相同的硬件，进一步减少需要在服务器和承载基础结构投资。

## <a name="cross-platform"></a>跨平台

ASP.NET 核心是跨平台，可以在 Linux 和 MacOS，以及 Windows 上运行。 这将打开开发和部署的与 ASP.NET Core 构建的应用程序的许多新选项。 Docker 容器，通常目前运行 Linux，可以承载 ASP.NET Core 应用程序，允许它们充分利用的好处[容器和微服务](../microservices-architecture/index.md)。

## <a name="modular-and-loosely-coupled"></a>模块化和松散耦合

NuGet 包是在.NET 核心的极佳地处理和 ASP.NET Core 应用组成通过 NuGet 的许多库。 此粒度功能有助于确保应用仅依赖于并部署它们实际上需要，减少其占用的空间，安全漏洞外围应用的功能。

ASP.NET 核心还完全支持依赖关系注入内部和应用程序级别。 接口可具有多个可以在根据需要交换出的实现。 依赖关系注入允许到松散几到这些接口，使它们更易于扩展、 维护和测试应用程序。

## <a name="easily-tested-with-automated-tests"></a>轻松地测试的自动测试

ASP.NET 核心应用程序支持单元测试，并且其松散耦合和依赖关系注入的支持可以轻松地交换支持出于测试目的的假实现的基础结构。 ASP.NET 核心还附带可用于承载应用程序在内存中 TestServer。 功能测试然后可以向此内存中服务器，执行完整的应用程序堆栈 （包括中间件、 路由、 模型绑定，筛选器等） 发出请求，并且很短的时间内所有接收到响应时，会花来承载实际的服务器上的应用并使通过网络层的请求。 这些测试是特别容易写入，以及有价值，api 中，哪些是在现代 web 应用程序日益重要。

## <a name="traditional-and-spa-behaviors-supported"></a>传统和支持的 SPA 行为

传统 web 应用程序具有涉及很少的客户端行为，但已将其依赖于所有导航、 查询和应用程序可能需要进行的更新的服务器。 在最终用户的浏览器中完整的页面重新加载结果，用户所做的每个新操作将转换为新的 web 请求。 经典模型-视图-控制器 (MVC) 框架通常执行此方法时，对应不同的控制器操作，这反过来会使用一个模型并返回的视图的每个新请求。 给定页上的某些各个操作可能增强通过支持 AJAX （异步 JavaScript 和 XML） 功能，但应用程序的总体体系结构使用许多不同的 MVC 视图和 URL 终结点。

单页面应用程序 (Spa) 与此相反，涉及很少动态生成的服务器端页面加载 （如果有）。 许多 Spa 被初始化静态的 HTML 文件，后者将加载必需的 JavaScript 库，以启动并运行应用程序中。 这些应用使其数据需求，web Api 的使用率很高，并且可以提供许多更丰富的用户体验。

许多 web 应用程序涉及 （通常为内容） 的传统 web 应用程序行为和 （对于交互） 的 Spa 的组合。 ASP.NET 核心支持 MVC 和 web Api 在同一应用程序，使用相同的一套工具和基础 framework 库。

## <a name="simple-development-and-deployment"></a>简单开发和部署

可以使用简单文本编辑器和命令行接口或全功能的开发环境类似于 Visual Studio 编写 ASP.NET Core 应用程序。 整体应用程序通常会部署到单个终结点。 可以轻松地自动部署发生作为持续集成 (CI) 和持续交付 (CD) 管道的一部分。 除了传统的 CI/CD tools，Windows Azure 已集成的 git 存储库的支持，并且可以自动部署更新，因为它们由到指定的 git 分支或标记。

## <a name="traditional-aspnet-and-web-forms"></a>传统的 ASP.NET 和 Web 窗体

除了 ASP.NET 核心，传统 ASP.NET 4.x 仍然是一个功能强大和可靠的平台，用于构建 web 应用程序。 ASP.NET 支持 MVC 和 Web API 的开发模型，以及 Web 窗体，也不能是适合于基于页面的丰富应用程序开发功能丰富的第三方组件生态系统。 Windows Azure 具有 ASP.NET 4.x 应用程序的全力种长期存在支持，并且许多开发人员熟悉此平台。

> ### <a name="references--modern-web-applications"></a>引用 – 现代 Web 应用程序
> - **ASP.NET Core 简介**  
> <https://docs.microsoft.com/aspnet/core/>
> - **六个密钥好处的 ASP.NET Core 这使其不同和更好的**  
> <https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/>
> - **在 ASP.NET Core 中测试**  
> <https://docs.microsoft.com/aspnet/core/testing/>

>[!div class="step-by-step"]
[以前](index.md) [下一步] (choose-between-traditional-web-and-single-page-apps.md)
