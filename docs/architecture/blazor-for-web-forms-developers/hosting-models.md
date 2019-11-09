---
title: Blazor 应用托管模型
description: 了解托管 Blazor 应用程序的不同方式，其中包括 WebAssembly 上的浏览器或服务器上的。
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 5bf55fa686691acc25508d3d9a6dfaf8aca321ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841947"
---
# <a name="blazor-app-hosting-models"></a>Blazor 应用托管模型

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Blazor 应用程序可以在 IIS 中托管，就像 ASP.NET Web 窗体应用一样。 还可以通过以下方式之一承载 Blazor 应用：

- WebAssembly 上浏览器中的客户端。
- ASP.NET Core 应用中的服务器端。

## <a name="blazor-webassembly-apps"></a>Blazor WebAssembly apps

Blazor WebAssembly apps 直接在基于 WebAssembly 的 .NET 运行时上的浏览器中执行。 Blazor WebAssembly apps 的工作方式类似于前端 JavaScript 框架，如角度或反应。 但是，不是编写你编写C#的 JavaScript。 .NET 运行时随应用程序一起下载，并随应用程序集和任何所需的依赖项一起下载。 不需要浏览器插件或扩展。

下载的程序集是普通的 .NET 程序集，就像在任何其他 .NET 应用程序中使用一样。 由于运行时支持 .NET Standard，因此你可以将现有的 .NET Standard 库用于 Blazor WebAssembly 应用程序。 但是，这些程序集仍将在浏览器安全沙箱中执行。 某些功能可能会引发 <xref:System.PlatformNotSupportedException>，如尝试访问文件系统或打开任意网络连接。

当应用程序加载时，.NET 运行时将启动并指向应用程序集。 应用启动逻辑运行，并呈现根组件。 Blazor 根据组件的呈现输出来计算 UI 更新。 然后应用 DOM 更新。

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

Blazor WebAssembly apps 纯粹运行客户端。 此类应用可部署到静态站点托管解决方案，如 GitHub 页面或 Azure 静态网站托管。 服务器上根本不需要 .NET。 深层链接到应用程序通常需要服务器上的路由解决方案。 路由解决方案将请求重定向到应用程序的根。 例如，可以在 IIS 中使用 URL 重写规则来处理此重定向。

若要获取 Blazor 和完整 stack .NET web 开发的所有优点，请将 Blazor WebAssembly 应用程序与 ASP.NET Core 托管在一起。 通过在客户端和服务器上使用 .NET，可以轻松地共享代码，并使用一组一致的语言、框架和工具来生成应用程序。 Blazor 提供了方便的模板，用于设置包含 Blazor WebAssembly 应用和 ASP.NET Core 主机项目的解决方案。 构建解决方案时，Blazor 应用中的生成静态文件由已设置了回退路由的 ASP.NET Core 应用程序托管。

## <a name="blazor-server-apps"></a>Blazor 服务器应用

从[Blazor 体系结构](architecture-comparison.md#blazor)的讨论中，Blazor 组件会将其输出呈现为名为 `RenderTree`的中间抽象。 然后，Blazor 框架将呈现的内容与之前呈现的内容进行比较。 这些差异应用于 DOM。 Blazor 组件与应用呈现输出的方式保持分离。 因此，组件本身不必在更新 UI 的过程中运行。 事实上，它们甚至不需要在同一台计算机上运行。

在 Blazor 服务器应用程序中，组件在服务器上运行，而不是在浏览器中运行。 浏览器中发生的 UI 事件通过实时连接发送到服务器。 事件将分派给正确的组件实例。 组件将呈现，并将计算的 UI 差异序列化并发送到浏览器，并将其应用于 DOM。

![Blazor 服务器](media/hosting-models/blazor-server.png)

如果使用了 ASP.NET AJAX 和 <xref:System.Web.UI.UpdatePanel> 控件，则 Blazor Server 宿主模型可能听起来非常熟悉。 `UpdatePanel` 控件处理应用部分页面更新以响应页面上的触发器事件。 触发时，`UpdatePanel` 会请求部分更新，然后应用该更新，而无需刷新页面。 UI 的状态使用 `ViewState`进行管理。 Blazor Server apps 略有不同，因为应用需要与客户端建立活动连接。 此外，还会在服务器上维护所有 UI 状态。 除了这些差异以外，这两个模型在概念上类似。

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>如何选择正确的 Blazor 托管模型

如[Blazor 托管模型文档](https://docs.microsoft.com/aspnet/core/blazor/hosting-models#server-side)中所述，不同的 Blazor 托管模型具有不同的折衷方式。

Blazor WebAssembly 托管模型具有以下优势：

- 没有 .NET 服务器端依赖项。 应用在下载到客户端之后完全正常运行。
- 完全利用客户端资源和功能。
- 工作从服务器卸载到客户端。
- 不需要 ASP.NET Core web 服务器来托管应用程序。 无服务器部署方案可能（例如，通过 CDN 提供应用）。

Blazor WebAssembly 托管模型的缺点是：

- 浏览器功能限制了应用程序。
- 需要支持的客户端硬件和软件（例如，WebAssembly 支持）。
- 下载大小较大，应用需要较长时间才能加载。
- .NET 运行时和工具支持不太成熟。 例如， [.NET Standard](../../standard/net-standard.md)支持和调试存在一些限制。

相反，Blazor 服务器托管模型具有以下优势：

- 下载大小要比客户端应用小得多，并且应用的加载速度要快得多。
- 应用充分利用服务器功能，包括使用任何与 .NET Core 兼容的 Api。
- 服务器上的 .NET Core 用于运行应用程序，因此现有的 .NET 工具（如调试）可按预期方式工作。
- 支持瘦客户端。 例如，服务器端应用程序适用于不支持 WebAssembly 的浏览器和资源限制的设备。
- 应用程序的 .NET/C#代码库（包括应用程序的组件代码）不会提供给客户端。

Blazor 服务器托管模型的缺点是：

- UI 延迟更高。 每个用户交互都涉及网络跃点。
- 无脱机支持。 如果客户端连接失败，应用将停止工作。
- 对于包含多个用户的应用而言，可伸缩性非常困难。 服务器必须管理多个客户端连接并处理客户端状态。
- 为应用提供服务需要 ASP.NET Core 服务器。 无法进行无服务器部署方案。 例如，你不能从 CDN 服务应用。

前面的权衡列表可能是造成威胁，但你的托管模型可在以后更改。 无论选择 Blazor 托管模型，组件模型都是*相同*的。 原则上，同一组件可用于任一宿主模型。 你的应用程序代码不会更改;不过，最好的做法是引入抽象，使组件保持与模型无关。 抽象使你的应用能够更轻松地采用不同的承载模型。

## <a name="deploy-your-app"></a>部署应用

ASP.NET Web 窗体应用通常在 Windows Server 计算机或群集上的 IIS 上托管。 Blazor 应用还可以：

- 作为静态文件或作为 ASP.NET Core 应用托管在 IIS 上。
- 利用 ASP.NET Core 在各种平台和服务器基础结构上的灵活性。 例如，可以在 Linux 上使用[Nginx](/aspnet/core/host-and-deploy/linux-nginx)或[Apache](/aspnet/core/host-and-deploy/linux-apache)来托管 Blazor 应用。 有关如何发布和部署 Blazor 应用的详细信息，请参阅 Blazor[托管和部署](/aspnet/core/host-and-deploy/blazor/)文档。

在下一部分中，我们将介绍如何设置 Blazor WebAssembly 和 Blazor 服务器应用的项目。

>[!div class="step-by-step"]
>[上一页](architecture-comparison.md)
>[下一页](project-structure.md)
