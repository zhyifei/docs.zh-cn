---
title: "正则表达式中的编译和重复使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET Framework regular expressions, engines
- .NET Framework regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 76acdf2d0d2f7805ec78ea44136bfc63441b9bc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>正则表达式中的编译和重复使用
通过了解正则表达式引擎编译表达式的方式以及正则表达式的缓存方式，可以优化大量使用正则表达式的应用程序的性能。 本主题介绍编译和缓存。  
  
## <a name="compiled-regular-expressions"></a>已编译的正则表达式  
 默认情况下，正则表达式引擎将正则表达式编译成内部指令序列（这些指令序列是不同于 Microsoft 中间语言 (MSIL) 的高级代码）。 当引擎执行正则表达式时，会解释内部代码。  
  
 如果<xref:System.Text.RegularExpressions.Regex>对象构造<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>选项，它将编译到显式的 MSIL 代码，而不是高级正则表达式内部说明的正则表达式。 这样，.NET 的实时 (JIT) 编译器便可以将表达式转换为本机代码以获得更高的性能。  
  
但是，生成的 MSIL 不能卸载。 卸载代码的唯一方法是卸载整个应用程序域（即，卸载应用程序的所有代码）。 实际上，正则表达式编译与后<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>选项时，永远不会释放已编译的表达式中，使用的资源，即使正则表达式由<xref:System.Text.RegularExpressions.Regex>本身发布到的垃圾回收的对象。  
  
 您必须小心地将其限制的不同使用编译的正则表达式的数目<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>选项，以避免消耗太多资源。 如果应用程序必须使用较大数量或极大数量的正则表达式，应该解释每个表达式，而不要编译它们。 但是，如果重复使用少量的正则表达式，它们应使用编译<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>以提高性能。 一种替代方法是使用预编译的正则表达式。 你可以通过编译为可重用 DLL 将表达式的所有<xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>方法。 这样就避免了需要在运行时编译并同时仍可受益的已编译的正则表达式的速度。  
  
## <a name="the-regular-expressions-cache"></a>正则表达式缓存  
 为了提高性能，正则表达式引擎为已编译的正则表达式维护了一个应用程序范围的缓存。 该缓存只存储静态方法调用中使用的正则表达式模式。 （不缓存提供给实例方法的正则表达式模式。）这样，在每次使用正则表达式时，就无需将正则表达式重新分析成高级字节代码。  
  
 值确定的缓存的正则表达式的最大数目`static`(`Shared`在 Visual Basic 中)<xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType>属性。 默认情况下，正则表达式引擎最多可缓存 15 个已编译的正则表达式。 如果已编译正则表达式的数目超过缓存大小，则丢弃最早使用的正则表达式并缓存新的正则表达式。  
  
 应用程序可通过以下两种方式之一来利用预编译的正则表达式：  
  
-   通过使用的静态方法<xref:System.Text.RegularExpressions.Regex>对象来定义正则表达式。 如果要使用的正则表达式模式已在其他静态方法调用中定义，则正则表达式引擎将从缓存中检索该模式。 如果不是这样，则引擎将编译正则表达式并将其添加到缓存中。  
  
-   通过重用现有<xref:System.Text.RegularExpressions.Regex>对象，只要需要其正则表达式模式。  
  
 由于对象实例化和正则表达式编译、 创建和快速销毁大量的系统开销<xref:System.Text.RegularExpressions.Regex>对象是一个代价很高的过程。 对于使用大量不同的正则表达式的应用程序，你可以通过使用为静态的调用来优化性能`Regex`方法并尽量增加正则表达式缓存的大小。  
  
## <a name="see-also"></a>另请参阅  
 [.NET 正则表达式](../../../docs/standard/base-types/regular-expressions.md)
