---
title: ".NET Framework 和带外版本 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# .NET Framework 和带外版本
.NET Framework 不断适应不同的平台（例如 Windows Phone 和 Windows 应用商店应用以及传统桌面和 Web 应用）以最大化代码的重复使用。  除了 .NET Framework 定期发布之外，我们还会发布处于预发布阶段 \(OOB\) 的新功能以改善跨平台开发或引入新功能。  本主题讨论 .NET Framework 及其 OOB 版本的未来方向。  
  
## OOB 版本的优点  
 将新组件或更新发送给带区之外的组件让 Microsoft 能够更频繁地提供 .NET Framework 的更新。  此外，我们可以更快地收集和回应客户反馈。  
  
 如果你在应用程序中使用了 OOB 功能，你的用户不必安装最新版 .NET Framework 即可运行你的应用程序，因为 OOB 程序集是与你的应用程序包一起部署的。  
  
## OOB 包是如何存储的  
 核心公共语言运行时 \(CLR\) 组件的 OOB 版本通过 [NuGet 程序包管理器](http://nuget.codeplex.com/)发送，此管理器为一个开放源 Visual Studio 扩展。  NuGet 让你可以轻松地通过 Visual Studio 中的解决方案资源管理器浏览并将库添加至你的 .NET Framework 项目。  从 Visual Studio 2012 开始，NuGet 随附于 Visual Studio 的所有版本。  若要查看是否已安装 NuGet，请查找 Visual Studio**“工具”**菜单上的**“库程序包管理器”**。  如果尚未安装：  
  
1.  在 Visual Studio 菜单栏中，依次选择**“工具”**、**“扩展和更新”**（在 Visual Studio 2010 中，选择**“扩展管理器”**）。  
  
     **“扩展和更新”**对话框将打开。  
  
2.  选择**“联机”**，**“NuGet 程序包管理器”**，然后选择**“下载”**。  
  
3.  在下载完毕后，重新启动 Visual Studio。  
  
 有关详细的安装说明，请参见 NuGet Docs 网站上的[安装 NuGet](http://docs.nuget.org/docs/start-here/installing-nuget)。  有关 NuGet 的详细信息，请参见 [NuGet 文档](http://docs.nuget.org/)。  
  
## 使用 NuGet OOB 程序包  
 在安装 NuGet 后，可以使用 Visual Studio 中的解决方案资源管理器浏览并添加引用到 NuGet 程序包：  
  
1.  打开你在 Visual Studio 中的项目的快捷菜单，然后选择**“管理 NuGet 程序包”**。  （可以从**“项目”**菜单中使用该此选项。）  
  
2.  在左侧窗格中，选择**“联机”**。  
  
3.  如果要使用中间窗格的下拉列表框中的预发行包，请选择**“包括预发行”**而非**“仅稳定”**。  
  
4.  在右窗格中，使用**“搜索”**框来查找你要使用的程序包。  某些 Microsoft 程序包通过 Microsoft .NET Framework 徽标进行识别，发布者均为 Microsoft。  
  
 ![NuGet Package Manager](../../../docs/framework/get-started/media/clrnugetdialog.png "clrNugetDialog")  
  
 如前所述，当你部署使用了 OOB 包的应用程序，OOB 程序集将随附你的应用程序包。  
  
## OOB 版本的类型  
 通常情况下，OOB 程序包具有一个或多个预发行版本和一个稳定的版本。  预发行附带的许可证通常不允许再发行，但可让你试用程序包并提供反馈。  任何对包的更新中都包含反馈。  最终发布版本作为稳定的包随 NuGet 分发并包含允许随应用程序重新分发 NuGet 程序包的许可证。  稳定程序包受 Microsoft 支持。  Microsoft 还提供 IntelliSense 支持以及其他文档类型（如所有程序包的博客文章和论坛答案）。  此外，只有一些程序包可使用源代码，并非所有程序包都可使用。  有关新程序包和更新程序包的公告，可订阅 [.NET Framework 博客](http://blogs.msdn.com/b/dotnet/)。  
  
 若要查找预发布和稳定程序包，请在 NuGet 程序包管理器中选择**“包括预发布”**。  
  
 如果你希望收到稳定程序包发布的通知，请订阅 [.NET Framework 源](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/)。  
  
## 请参阅  
 [入门](../../../docs/framework/get-started/index.md)