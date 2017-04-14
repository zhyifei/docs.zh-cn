---
title: ".NET 核心和开放源代码 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# .NET 核心和开放源代码
.NET 核心是 .NET Framework 的模块化版本，采用可进行跨平台移植的设计，以实现代码重用和代码共享的最大化。 此外，.NET 核心将是开源的，并接受来自社区的贡献。 本主题解答一些有关.NET 核心的常见问题，以及如何访问并为开源包做出贡献。  
  
<a name="BKMK_WhatisNETCore"></a>   
## .NET 核心是什么？  
 正如前面提到的，.NET 核心是 .NET framework 的模块化版本，采用可进行跨平台移植的设计。  
  
 .NET 核心可进行跨平台移植，尽管是完整 .NET Framework 的一个子集，但它提供了让你实现所需应用功能的关键功能，并可重用该代码而与你的平台目标无关。 在过去，不同平台的不同 .NET 版本缺乏关键任务（例如读取本地文件）共享功能。 利用 .NET 可面向的 Microsoft 平台包括传统桌面版 Windows，以及 Windows 设备和手机。 如果使用 Xamarin 等第三方工具，.NET 核心可移植到 IOS 和 Android 设备。 此外，.NET 核心将很快推出适用于 Mac 和 Linux 操作系统的版本，以使 Web 应用能够在这两个系统上运行。  
  
 .NET 核心为模块化，因为它通过 NuGet 以较小的程序集数据包发布。 与包含了大部分核心功能的大型程序集不同，.NET 核心作为以功能为中心的小型数据包提供。 这为我们提供了更多敏捷开发模型，并允许你选择你的应用和库所需的功能。 有关在 NuGet 上发布的 .NET 数据包的详细信息，请参阅 [.NET Framework 和带外版本](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)。  
  
 以下是一些有关 .NET 核心的常见问题。  
  
### 如何充分利用 .NET 核心？  
 对于现有的应用，使用可移植类库 \(PCL\)、通用应用项目以及将业务逻辑从平台特定代码中分离是充分利用 .NET 核心并最大化代码重用的最佳办法。 对于应用，模型\-视图\-控制器 \(MVC\) 或模型\-视图\-视图模型 \(MVVM\) 模式都是让你的应用可以轻松迁移至 .NET 核心的很好选择。  
  
### .NET 核心如何影响兼容性和部署？  
 有几个不同的部署方案，但是部署仍应简单。 .NET Framework 随 Windows 一起发行，并通过 Microsoft Update 更新，就像现在一样。 在某些情况下，你的应用将依赖于此磁盘上的 .NET Framework 部署，在其他情况下，你的应用将依赖于随该应用包一起部署的 .NET 程序集。 此外，版本之间的兼容性仍是 .NET Framework 的高优先级，因此如果应用所运行的程序集版本比编译时的版本要新，则其行为将保持一致。  
  
|方案|部署|  
|--------|--------|  
|Windows 桌面和运行于 Windows 计算机上的 ASP.NET 应用|部署和现在相同。 依赖于在服务器或用户计算机上安装的 .NET Framework 的应用。 如果未安装 .NET Framework，则将提示用户安装。 或者，你也可以链接应用与 .NET 安装。 从没有包括在 .NET Framework 的 .NET 核心中使用程序集时，这些程序集会包括在应用包中。 同时，如果同一应用同时引用了相同程序集的两个版本，则应用将重定向至较新的程序集。 有关更多信息，请参见[在应用级别重定向程序集版本](../../../docs/framework/configure-apps/redirect-assembly-versions.md#BKMK_Redirectingassemblyversionsattheapplevel)和[如何：启用和禁用自动绑定重定向](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)。<br /><br /> 有关 .NET 部署的详细信息，请参阅 [部署指南（针对开发人员）](../../../docs/framework/deployment/deployment-guide-for-developers.md)。|  
|Windows 和 Windows Phone 应用可通过 Windows 和 Windows Phone 应用商店提供|部署与现在相同，应用使用已包括在操作系统中的 .NET Framework 程序集。 如果应用使用发布于 .NET 核心程序集而不包括在 .NET Framework 中的功能，程序集将包括在应用包中。 如果应用引用了同一程序集的多个版本，则应用将自动使用较新的程序集版本。|  
|ASP.NET 核心 5.0 应用|.NET 核心程序集是本地应用，这就意味着需要随应用包一起部署。 有关 ASP.NET 核心 5.0 的详细信息，请参阅 [ASP.NET 5 概述](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview)。|  
|采用运行于其他平台的 Xamarin 工具生成的应用。|目前，这些应用采用随应用包一起提供的简化 Mono 程序集进行部署。 随着更多 .NET 核心程序开放源代码，这种情况可能会发生改变。|  
  
<a name="BKMK_NETCoreOpenSourcePackages"></a>   
## .NET 核心开源包  
 除了 .NET Framework 的模块化以外，Microsoft 正在 [GitHub](https://github.com/) 上利用 [MIT](https://github.com/dotnet/corefx/blob/master/LICENSE) 许可开放 .NET 核心包的源代码。 这意味着你可以像在 GitHub 上找到的其他开源包一样克隆 Git 存储库、阅读和编译代码以及提交拉取请求。 由于我们对质量和兼容性所做出的承诺，每个拉取请求都将在接受前仔细评估。 以下是一些常见问题。  
  
### 如何获得代码并生成代码？  
 .NET 核心源包存储在使用 `Git` 作为源代码管理系统的 `GitHub` 上。 若要访问和生成代码，你应该已基本熟悉 [Git](http://git-scm.com/)、[GitHub](https://github.com/dotnet/corefx) 和 [Visual Studio](http://msdn.microsoft.com/vstudio/aa718325.aspx)，但是以下步骤为你提供了一些信息和链接，以帮助你入门。  
  
 若要设置 Git 和 GitHub，请参阅 GitHub 站点上的[设置 Git](https://help.github.com/articles/set-up-git/)。  
  
 若要访问.NET Framework 代码，你需要将包含它的 Git 存储库分叉，并将其克隆到你的开发计算机上。 你可以通过导航到存储卡并单击浏览器右上角的**分叉**来为代码分叉。 你可以使用 GitHub 应用或在 GitHub Shell 中的命令行上克隆分叉。 若要在 GitHub Shell 中克隆存储库，运行以下命令：  
  
```  
git clone https://github.com/dotnet/corefx  
```  
  
 若要生成代码，必须安装 Visual Studio 2013。 你既可以使用 Visual Studio 2013 并按 F5 来打开和生成解决方案，也可以使用“开发人员命令提示”在命令行上生成代码。 若要使用命令提示，打开“开发人员命令提示”并导航至你克隆了源代码的文件夹。 然后键入：  
  
```  
build.cmd  
  
```  
  
 有关如何访问“开发人员命令提示”的详细信息，请参阅 [命令提示符](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。  
  
### 提交代码的准则有哪些？  
 在我们将你的工作合并到主分支之前，你需要签署一份[参与者许可协议 \(CLA\)](https://cla.dotnetfoundation.org/)。  
  
 我们接受来自使用“分叉”和“拉取”模型的社区的贡献。 你应该对这些代码分叉并克隆，然后向 .NET Framework 主分支提交拉取请求。 有关拉取请求的详细信息，请参阅[使用拉取请求](https://help.github.com/articles/using-pull-requests/)。 有关提交拉取请求的指南的详细信息，请参阅 [.NET 核心贡献指南](https://github.com/dotnet/corefx/wiki/Contributing)。  
  
### 为什么不接受我的拉取请求？  
 如果我们拒绝了你的请求，我们将向你提供拒绝的原因，但一般来说，Microsoft 要维护对代码质量和兼容性所做出的有力承诺。 如果你的拉取请求未被接受，可能是你没有遵守我们的编码原则、提交的代码所做的测试不够或破坏了 API 兼容性。 此外，你的代码更改应与我们的 .NET Framework 路线图保持一致。 有关编码原则和详细信息，请参阅 [.NET 核心贡献指南](https://github.com/dotnet/corefx/wiki/Contributing)。  
  
## 请参阅  
 [.NET 为开放源](http://blogs.msdn.com/b/dotnet/archive/2014/11/12/net-core-is-open-source.aspx)   
 [.NET 开放源 Curah](https://curah.microsoft.com/254870/net-core-open-source)   
 [ASP.NET 5 概述](http://www.asp.net/vnext/overview/aspnet-vnext/aspnet-5-overview)