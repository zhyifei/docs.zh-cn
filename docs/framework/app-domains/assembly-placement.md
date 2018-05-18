---
title: 程序集位置
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6a10a896494304b9c3c17bc320464a8273e430d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="assembly-placement"></a>程序集位置
对于大多数 .NET Framework 应用程序而言，您可以在以下位置找到构成该应用程序的程序集，这些位置包括：该应用程序的目录中，该应用程序目录的子目录中，或全局程序集缓存中（如果该程序集是共享的话）。 可以通过在配置文件中使用 [\<codeBase> 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)替代公共语言运行时查找某一程序集的位置。 如果程序集没有强名称，则使用 [\<codeBase> 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)指定的位置限制为应用程序目录或子目录。 如果程序集具有强名称，则 [\<codeBase> 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)能够指定计算机或网络上的任意位置。  
  
 当在使用非托管代码或 COM 互操作 应用程序的过程中查找程序集的位置时，类似的规则同样适用：如果该程序集将由多个应用程序共享，则此程序集应被安装到全局程序集缓存中。 和非托管代码一起使用的程序集必须作为类型库导出并注册。 由 COM 互操作 使用的程序集必须在目录中进行注册，尽管有些情况下会自动进行此注册。  
  
## <a name="see-also"></a>请参阅  
 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [配置应用程序](../../../docs/framework/configure-apps/index.md)  
 [高级 COM 互操作性](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）
