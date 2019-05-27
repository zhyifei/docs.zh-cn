---
title: 使用 .NET Native 编译引用
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28b09bf07d831747be0006ffe1f1d8c5ac5171ce
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052645"
---
# <a name="compiling-apps-with-net-native"></a>使用 .NET Native 编译引用
.NET native 是 Visual Studio 2015 或更高版本包含了用于构建和部署 Windows 应用的预编译技术。 它自动将以托管代码（C# 或 Visual Basic）编写并面向 .NET Framework 和 Windows 10 的发布版本的应用编译为本机代码。  
  
 通常，定位于 .NET Framework 的应用会被编译到中间语言 (IL) 中。 在运行时间，及时生成 (JIT) 编译器将 IL 翻译为本机代码。 与此相反，.NET Native 编译为本机代码直接的 Windows 应用。 对于开发者，这意味着：  
  
- 您的应用程序功能的本机代码的性能。 通常情况下，性能将优于第一次编译到 IL，然后编译为本机代码的 JIT 编译器的代码。 
  
- 你可以继续用 C# 或 Visual Basic 进行编程。  
  
- 你可以继续使用 .NET Framework 提供的资源，包括类库、自动内存管理、垃圾回收和异常处理。  
  
 对于您的应用程序的用户，.NET Native 提供以下优势：  
  
- 对于大多数应用程序和方案的更快地执行时间。
  
- 对于大多数应用程序和方案更快的启动时间。 
  
- 部署和更新的低成本。  
  
- 优化应用内存使用情况。  

> [!IMPORTANT]
> 对于绝大多数应用程序和方案，.NET Native 提供明显更快的启动时间和优异的性能与应用程序编译为 IL 或 NGEN 映像相比。 但是，您的结果可能会有所不同。 若要确保您的应用程序具有受益的.NET Native 的性能增强功能，应将与您的应用程序的非.NET Native 版本其性能进行比较。 有关详细信息，请参阅[性能会话概述](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview)。
 
但.NET Native 涉及多个编译为本机代码。 它会改变 .NET Framework 应用的创建和执行方式。 具体而言：  
  
- 在预编译期间，所需的 .NET Framework 部分会静态连接到你的应用。 这允许应用同 .NET Framework 的应用本地库一起运行，并且允许编译器执行全局分析，从而提供性能优势。 因此，应用甚至在 .NET Framework 更新后会启动得更快。  
  
- .NET Native 运行时优化来动态预编程，并且在大多数情况下提供优异的性能。 同时，它保留了开发者认为非常高效的核心反射特性。  
  
- .NET native 使用相同的后端为C++编译器，针对静态预编译方案进行了优化。  
  
 .NET native 是带来的性能优势C++给托管代码开发人员，因为它使用与相同或类似的工具C++实质上，此表中所示。  
  
||.NET Native|C++|  
|-|----------------------------------------------------------------|-----------|  
|库|.NET Framework + Windows 运行时|Win32 + Windows 运行时|  
|编译器|UTC 优化编译器|UTC 优化编译器|  
|已部署|随时可以运行的二进制代码|随时可以运行的二进制代码 (ASM)|  
|运行时|MRT.dll（最短 CLR 运行时）|CRT.dll（C 运行时）|  
  
 对于适用于 Windows 10 的 Windows 应用，可将应用程序包（.appx 文件）中的 .NET 本机代码编译二进制文件上载到 Windows 应用商店。  
  
## <a name="in-this-section"></a>本节内容  
 要查看有关带有 .NET Native 代码编译的应用开发的信息，请参阅以下主题：  
  
- [开始使用.NET Native 代码编译：开发者经验介绍](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- [.NET native 和编译：](../../../docs/framework/net-native/net-native-and-compilation.md)如何.NET Native 编译为本机代码项目。  
  
- [反射和 .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [依赖反射的 API](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [反射 API 引用](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [运行时指令 (rd.xml) 配置文件参考](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [Serialization and Metadata（序列化和元数据）](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [将 Windows 应用商店应用迁移到 .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [.NET Native 一般疑难解答](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
