---
title: ".NET Framework 4.5.1 中的重定目标更改 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- retargeting changes
- .NET Framework 4.5.1
- retargeting changes, .NET Framework 4.5.1
- retargeting changes, .NET Framework
ms.assetid: 8087326d-77e9-4804-ba33-ff1bb1bec2b8
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0c497561254c0f97f22ac05c7d44224b30ef74d0
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-451"></a>.NET Framework 4.5.1 中的重定目标更改
在极少数情况下，重定目标更改可能影响那些编译为面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 的应用。 它们不会影响面向以前版本的 .NET Framework 但在版本 4.5.1 下运行的二进制文件。 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 包括以下方面的重定目标更改：  
  
-   [核心](#Core)  
  
-   [ADO.NET](#ADO)  
  
-   [MSBuild](#MSBuild)  
  
 下表中的“范围”列指定每个更改的基数：  
  
-   主要。 显著的更改，可影响大量应用或需要修改大量代码。 请注意，没有重定目标更改归入此类别。  
  
-   次要。 影响少量应用或需要修改少量代码的更改。  
  
-   边缘。 仅在少数非常特定的情况下影响应用的更改。  
  
-   透明。 对应用的开发人员或用户没有明显影响的更改。 不需要由于此更改而修改应用。  
  
<a name="Core"></a>   
## <a name="core-retargeting-changes"></a>核心重定目标更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.ObsoleteAttribute?displayProperty=fullName> 特性|创建 Windows 元数据库（.winmd 文件）时，<xref:System.ObsoleteAttribute> 特性导出为 <xref:System.ObsoleteAttribute> 和 [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx)。|重新编译使用 <xref:System.ObsoleteAttribute> 特性的现有源代码后，可能会在通过 C++/CX 或 JavaScript 使用此代码时生成警告。<br /><br /> 不建议同时将 <xref:System.ObsoleteAttribute> 和 [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) 应用于托管程序集中的代码；这样做可能会导致生成警告出现。<br /><br /> 有关详细信息，请参阅 <xref:System.ObsoleteAttribute> 参考主题。|边缘|  
  
<a name="ADO"></a>   
## <a name="adonet-retargeting-changes"></a>ADO.NET 重定目标更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Data.Common.DbParameter?displayProperty=fullName> 类|<xref:System.Data.Common.DbParameter.Precision%2A?displayProperty=fullName> 和 <xref:System.Data.Common.DbParameter.Scale%2A?displayProperty=fullName> 作为公共虚属性实现。 它们替换相应的显式接口实现代码 <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision%2A?displayProperty=fullName> 和 <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale%2A?displayProperty=fullName>。|此更改仅影响构建 ADO.NET 数据库提供程序的开发人员。|边缘|  
  
<a name="MSBuild"></a>   
## <a name="msbuild-retargeting-changes"></a>MSBuild 重定目标更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|`ResolveAssemblyReference` 任务|此任务发出警告 MSB3270，它表示引用或任何依赖项不匹配应用程序的体系结构。 例如，如果使用 `anycpu` 选项编译的应用程序包括 x86 引用，则会发生此情况。 这样的情况可能导致运行时应用失败（在本例中为，如果应用部署为 x64 过程）。|有两方面的影响：<br /><br /> - 重新编译会生成警告，而当应用程序是在旧版 MSBuild 控制下进行编译时，此类警告不显示。 但是，由于该警告可标识运行时失败可能的来源，所以应该调查并处理它。<br />- 如果警告被视为错误，将无法编译应用程序。|次要|  
  
## <a name="see-also"></a>另请参阅  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)   
 [4.5 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.2 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
