---
title: ".NET Framework 入门 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, getting started
- getting started [.NET Framework]
ms.assetid: c693fd34-88fe-4d90-b332-19eeadf3b7e7
caps.latest.revision: 35
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: adb9c30b6dc52ea17410423fd76c938e258549eb
ms.openlocfilehash: 6c069db2e6138f73935a4bdd458fbe94ef57d968
ms.lasthandoff: 05/02/2017

---
# <a name="getting-started-with-the-net-framework"></a>.NET Framework 入门
.NET Framework 是管理面向 .NET Framework 的应用程序的运行时执行环境。 它包括公共语言运行时（提供了内存管理和其他系统服务）和一个全面的类库（它使程序员能利用应用程序开发的所有主要区域的强大且可靠的代码）。  
  
<a name="Introducing"></a>   
## <a name="what-is-the-net-framework"></a>什么是 .NET Framework？  
 .NET Framework 是为其运行的应用程序提供各种服务的托管执行环境。 它包括两个主要组件：作为处理运行的应用程序的执行引擎的公共语言运行时 (CLR)；以及 .NET Framework 类库，此类库提供开发人员可从其自己的应用程序中调用的已测试的可重用代码库。 .NET Framework 提供的用于运行应用程序的服务包括：  
  
-   内存管理。 在许多编程语言中，程序员负责分配和释放内存并处理对象生存期。 在 .NET Framework 应用程序中，CLR 代表应用程序提供这些服务。  
  
-   常规类型系统。 在传统编程语言中，基本类型由编译器定义，这将使跨语言互操作性复杂化。 在 .NET Framework 中，基本类型由 .NET Framework 类型系统定义，并且是面向 .NET Framework 的所有语言所共有的。  
  
-   一个全面的类库。 程序员可以从 .NET Framework 类库中使用类型及其成员的易于访问的库，而不必编写大量代码来处理常见的低级编程操作。  
  
-   开发框架和技术。 .NET Framework 包括应用程序开发的特定区域的库，如 Web 应用程序的 ASP.NET，数据访问的 ADO.NET 和面向服务的应用程序的 Windows Communication Foundation。  
  
-   语言互操作性。 面向 .NET Framework 的语言编译器发出名为公共中间语言 (CIL) 的中间代码，反过来，通过公共语言运行时在运行时进行编译。 使用此功能，以一种语言编写的例程可由另一种语言访问，并且程序员可以将精力集中在使用其首选语言创建应用程序上。  
  
-   版本兼容性。 除少数例外，通过使用 .NET Framework 的特定版本开发的应用程序可以运行，而无需在更高版本中进行修改。  
  
-   并行执行。 通过允许同一台计算机上存在公共语言运行时的多个版本，.NET Framework 可帮助解决版本冲突。 这意味着应用程序的多个版本也可以共存，并且应用程序可在构建它的 .NET Framework 版本上运行。  
  
-   多定向。 通过定向 .NET Framework 可移植类库，开发人员可创建在多个 .NET Framework 平台（例如，Windows 7、Windows 8、Windows 8.1、Windows 10、Windows Phone 和 Xbox 360）上工作的程序集。 有关详细信息，请参阅[可移植类库](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)。  
  
<a name="ForUsers"></a>   
## <a name="the-net-framework-for-users"></a>面向用户的 .NET Framework  
 如果你不开发 .NET Framework 应用程序，但需要使用它们，你不需要掌握有关 .NET Framework 或其操作的任何特定知识。 大多数情况下，.NET Framework 对用户是完全透明的。  
  
 如果你使用的是 Windows 操作系统，则你的计算机上可能已安装 .NET Framework。 此外，如果你安装需要 .NET Framework 的应用程序，则应用程序的安装程序可能会在你的计算机上安装特定版本的 .NET Framework。 在某些情况下，可能会显示一个要求你安装 .NET Framework 的对话框。 如果在该对话框出现时仅尝试运行应用程序，且如果计算机可以访问 Internet，则可以转到一个可让你安装缺少的 .NET Framework 版本的网页。  
  
 总之，你不应卸载安装在计算机上的任何版本的 .NET Framework。 主要有两个原因：  
  
-   如果你使用的应用程序依赖于特定版本的 .NET Framework，则该版本一旦遭删除，应用程序就会暂停。  
  
-   一些 .NET Framework 版本是早期版本的就地更新版。 例如，[!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] 是版本 2.0 的就地更新版，而 .NET Framework 4.6 是版本 4、4.5 和 4.5.1 和 4.5.2 的就地更新版。 有关详细信息，请参见 [.NET Framework 版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)。  
  
 如果选择删除 .NET Framework，请始终通过“控制面板”的“程序及功能”进行卸载。 请勿手动删除某个版本的 .NET Framework。  
  
 请注意，可在一台计算机上同时加载 .NET Framework 的多个版本。 这意味着，你不必卸载旧版本即可安装更新版本。  
  
<a name="ForDevelopers"></a>   
## <a name="the-net-framework-for-developers"></a>面向开发人员的 .NET Framework  
 如果你是开发人员，则可以选择任何支持 .NET Framework 的编程语言来创建应用程序。 由于 .NET Framework 提供了语言独立性和互操作性，因此无论使用何种语言开发，你都可以与其他 .NET Framework 应用程序和组件进行交互。  
  
 若要开发 .NET Framework 应用程序或组件，请执行以下操作：  
  
1.  如果未在操作系统上预安装 .NET Framework，请安装应用程序所面向的 .NET Framework 版本。 最新的生产版本是 .NET Framework 4.7，此版本预安装在 Windows 10 创意者更新上，并可下载到旧版 Windows 操作系统上。 有关 .NET Framework 系统要求，请参阅[系统要求](../../../docs/framework/get-started/system-requirements.md)。 有关安装其他版本的 .NET Framework 的信息，请参阅[安装指南](../../../docs/framework/install/guide-for-developers.md)。 提供了带外版本的其他 .NET Framework 程序包。 有关这些包的信息，请参阅 [.NET Framework 和带外版本](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)。  
  
2.  选择用于开发应用程序的 .NET Framework 语言。 有大量可用的语言，包括 Microsoft 中的 Visual Basic、C#、Visual F# 和 C++。 （一种用于开发 .NET Framework 应用程序的编程语言，它遵循[公共语言基础结构 (CLI) 规范](http://go.microsoft.com/fwlink/?LinkId=199862)。）  
  
3.  选择并安装你将用于创建应用程序并支持所选程序语言的开发环境。 适用于 .NET Framework 应用程序的 Microsoft 集成开发环境是 [Visual Studio](http://go.microsoft.com/fwlink/?LinkId=325532)。 它提供了多种零售版和免费版本。  
  
 有关开发面向.NET Framework 的应用的详细信息，请参阅[开发指南](../../../docs/framework/development-guide.md)。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|说明|  
|-----------|-----------------|  
|[概述](../../../docs/framework/get-started/overview.md)|为生成面向 .NET Framework 的应用程序的开发人员提供详细信息。|  
|[.NET Framework 和带外版本](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)|描述 .NET Framework 带外版本以及如何在应用程序中使用它们。|  
|[系统要求](../../../docs/framework/get-started/system-requirements.md)|列出运行 .NET Framework 的硬件和软件要求。|  
|[.NET 核心和开放源代码](../../../docs/framework/get-started/net-core-and-open-source.md)|介绍 .NET 核心与 .NET Framework 的关系，以及如何访问开放源代码 .NET 核心项目。|  
|[.NET 核心文档](https://docs.microsoft.com/dotnet/)|.NET 核心的概念和 API 参考文档。|  
|[安装指南](../../../docs/framework/install/guide-for-developers.md)|提供有关安装 .NET Framework 的信息。|  
  
## <a name="see-also"></a>另请参阅  
 [.NET Framework 4.6 和 4.5](../../../docs/framework/index.md)   
 [新增功能](../../../docs/framework/whats-new/index.md)   
 [.NET Framework 类库](http://go.microsoft.com/fwlink/?LinkId=227195)   
 [开发指南](../../../docs/framework/development-guide.md)
