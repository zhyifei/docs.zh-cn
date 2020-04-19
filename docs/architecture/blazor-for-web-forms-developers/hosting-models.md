---
title: 布拉佐应用程序托管模型
description: 了解托管 Blazor 应用的不同方式，包括在 WebAssembly 上的浏览器或服务器上。
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 77a022b01efba01038790c9601ea03f315a28fdf
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607927"
---
# <a name="blazor-app-hosting-models"></a>布拉佐应用程序托管模型

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Blazor 应用可以像 ASP.NET Web 窗体应用一样托管在 IIS 中。 Blazor 应用程序也可以以以下方式之一托管：

- WebAssembly 浏览器中的客户端。
- ASP.NET核心应用中的服务器端。

## <a name="blazor-webassembly-apps"></a>布拉佐尔网络装配应用程序

Blazor WebAssembly 应用直接在浏览器中基于 Web 大会的 .NET 运行时执行。 Blazor WebAssembly 应用程序的工作方式与前端 JavaScript 框架（如"角"或"反应"）类似。 但是，您编写 C# 时不是编写 JavaScript。 .NET 运行时随应用以及应用程序集和任何必需的依赖项一起下载。 无需浏览器插件或扩展。

下载的程序集是正常的 .NET 程序集，就像在任何其他 .NET 应用中使用一样。 由于运行时支持 .NET 标准，因此您可以将现有的 .NET 标准库与 Blazor WebAssembly 应用一起使用。 但是，这些程序集仍将在浏览器安全沙盒中执行。 某些功能可能会引发<xref:System.PlatformNotSupportedException>，例如尝试访问文件系统或打开任意网络连接。

当应用加载时，将启动 .NET 运行时并指向应用程序集。 应用启动逻辑运行，并呈现根组件。 Blazor 根据组件呈现的输出计算 UI 更新。 然后应用 DOM 更新。

![Blazor WebAssembly](media/hosting-models/blazor-webassembly.png)

Blazor WebAssembly 应用程序运行纯客户端。 此类应用可以部署到静态网站托管解决方案（如 GitHub 页面或 Azure 静态网站托管）。 服务器根本不需要 .NET。 深度链接到应用的某些部分通常需要服务器上的路由解决方案。 路由解决方案将请求重定向到应用的根目录。 例如，可以使用 IIS 中的 URL 重写规则来处理此重定向。

要获得 Blazor 和全堆栈 .NET Web 开发的所有优势，请使用 ASP.NET 核心托管 Blazor WebAssembly 应用程序。 通过在客户端和服务器上使用 .NET，可以轻松地共享代码并使用一组一致的语言、框架和工具构建应用。 Blazor 提供了方便的模板来设置包含 Blazor WebAssembly 应用和ASP.NET核心主机项目的解决方案。 生成解决方案后，Blazor 应用中生成的静态文件由已设置回退路由的ASP.NET酷睿应用托管。

## <a name="blazor-server-apps"></a>布拉佐尔服务器应用程序

回想一下[Blazor架构](architecture-comparison.md#blazor)讨论，Blazor组件将其输出呈现为称为`RenderTree`的中间抽象。 然后，Blazor 框架将呈现的内容与以前呈现的内容进行比较。 差异应用于 DOM。 Blazor 组件与其呈现输出的应用方式分离。 因此，组件本身不必在更新 UI 的进程相同的进程中运行。 事实上，他们甚至不必在同一台计算机上运行。

在 Blazor Server 应用中，组件在服务器上运行，而不是在浏览器中客户端运行。 浏览器中发生的 UI 事件通过实时连接发送到服务器。 事件将发送到正确的组件实例。 组件渲染和计算的 UI 差异被序列化并发送到浏览器，并将其应用于 DOM。

![Blazor 服务器](media/hosting-models/blazor-server.png)

如果您使用了ASP.NETAJAX和控制，Blazor<xref:System.Web.UI.UpdatePanel>服务器托管模型听起来可能很熟悉。 控件`UpdatePanel`处理应用部分页面更新以响应以触发页面上的事件。 触发时，请求`UpdatePanel`部分更新，然后应用它，而无需刷新页面。 使用 管理 UI 的状态`ViewState`。 Blazor Server 应用略有不同，因为应用需要与客户端建立活动连接。 此外，服务器上维护所有 UI 状态。 除了这些差异之外，这两个模型在概念上是相似的。

## <a name="how-to-choose-the-right-blazor-hosting-model"></a>如何选择正确的布拉佐托管模式

如[Blazor 托管模型文档](/aspnet/core/blazor/hosting-models)中所述，不同的 Blazor 托管模型有不同的权衡。

Blazor WebAssembly 托管模型具有以下优点：

- 没有 .NET 服务器端依赖项。 应用程序在下载到客户端后已完全正常运行。
- 充分利用客户端资源和功能。
- 工作从服务器卸载到客户端。
- ASP.NET 酷网络服务器不需要托管应用。 可以使用无服务器部署方案（例如，从 CDN 为应用提供服务）。

Blazor WebAssembly 托管模型的缺点有：

- 浏览器功能限制应用。
- 需要有能力的客户端硬件和软件（例如，Web 组装支持）。
- 下载大小较大，并且加载应用需要更长的时间。
- .NET 运行时和工具支持不太成熟。 例如[，.NET 标准](../../standard/net-standard.md)支持和调试存在限制。

相反，Blazor 服务器托管模型具有以下优点：

- 下载大小比客户端应用小得多，并且应用程序的加载速度也快得多。
- 该应用程序充分利用了服务器功能，包括使用任何 .NET 核心兼容 API。
- 服务器上的 .NET Core 用于运行应用，因此现有的 .NET 工具（如调试）按预期工作。
- 支持精简客户端。 例如，服务器端应用适用于不支持 WebAssembly 和资源受限的设备上的浏览器。
- 应用程序的 .NET/C++ 代码库（包括应用的组件代码）不提供给客户端。

Blazor 服务器托管模型的缺点有：

- 更高的 UI 延迟。 每个用户交互都涉及网络跃点。
- 没有脱机支持。 如果客户端连接失败，应用将停止工作。
- 对于许多用户的应用来说，可扩展性具有挑战性。 服务器必须管理多个客户端连接并处理客户端状态。
- 需要ASP.NET核心服务器才能为应用提供服务。 无法使用无服务器部署方案。 例如，不能从 CDN 为应用提供服务。

前面的权衡列表可能很吓人，但您的托管模型可以在以后更改。 无论选择了何种 Blazor 托管模型，组件模型都是*相同的*。 原则上，相同的组件可用于任一托管模型。 你的应用代码不会更改;但是，你的应用代码不会更改。但是，引入抽象是一个很好的做法，这样您的组件将保持与模型无关的托管。 这些抽象允许你的应用更容易采用不同的托管模型。

## <a name="deploy-your-app"></a>部署应用

ASP.NET Web 窗体应用通常托管在 Windows 服务器计算机或群集上的 IIS 上。 Blazor 应用程序还可以：

- 托管在 IIS 上，作为静态文件或作为ASP.NET核心应用。
- 利用 ASP.NET Core 的灵活性，托管在各种平台和服务器基础架构上。 例如，您可以在 Linux 上使用[Nginx](/aspnet/core/host-and-deploy/linux-nginx)或[Apache](/aspnet/core/host-and-deploy/linux-apache)托管 Blazor 应用程序。 有关如何发布和部署 Blazor 应用的详细信息，请参阅 Blazor[托管和部署](/aspnet/core/host-and-deploy/blazor/)文档。

在下一节中，我们将介绍如何设置 Blazor WebAssembly 和 Blazor Server 应用的项目。

>[!div class="step-by-step"]
>[上一页](architecture-comparison.md)
>[下一页](project-structure.md)
