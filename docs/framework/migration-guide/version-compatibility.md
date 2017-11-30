---
title: ".NET Framework 的版本兼容性"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 166d61339d2b74f378b50ade4b78fd41e9692f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="version-compatibility-in-the-net-framework"></a>.NET Framework 的版本兼容性
向后兼容性表示为某个平台的特定版本开发的应用程序将在该平台的更高版本上运行。 .NET Framework 尝试最大程度地支持向后兼容性：为某个版本的 .NET Framework 编写的源代码应在更高版本的 .NET Framework 上编译，而在某个版本的 .NET Framework 上运行的二进制文件的行为方式应与其在更高版本的 .NET Framework 上的行为方式相同。  
  
<a name="Apps"></a>   
## <a name="version-compatibility-for-apps"></a>应用程序的版本兼容性  
 默认情况下，应用将在其目标 .NET Framework 版本上运行。 如果该版本不存在且应用程序配置文件未定义支持的版本，则可能出现 .NET Framework 初始化错误。 在此情况下，尝试运行应用程序将失败。  
  
 若要定义运行应用的特定版本，请将一个或多个 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 元素添加到应用的配置文件中。 每个 `<supportedRuntime>` 元素都列出了支持的运行时版本，第一个元素指定了优先级最高的版本，最后一个元素指定了优先级最低的版本。  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v2.0.50727" />  
      <supportedRuntime version="v4.0" />  
   </startup>  
</configuration>  
```  
  
 有关详细信息，请参阅[如何：配置应用以支持 .NET Framework 4 或 4.x](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)。  
  
## <a name="version-compatibility-for-components"></a>组件的版本兼容性  
 应用程序可控制运行它的 .NET Framework 版本，但组件不能。 由于组件和类库在特定应用的上下文中加载，因此它们会自动在运行应用的 .NET Framework 版本上运行。  
  
 由于存在此限制，因此兼容性保证对组件特别重要。 从 .NET Framework 4 开始，你可以通过将 <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> 特性应用于某个组件，来指定希望该组件与多个版本的兼容程度。 工具可使用此特性来检测组件的将来版本中的兼容性保证的潜在冲突。  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a>向后兼容性和 .NET Framework 4.5  
 .NET Framework 4.5 和更高版本是向后兼容.NET Framework 的早期版本生成的应用程序使用。 换而言之，应用程序和组件以前的版本生成的将而无需修改在处理.NET Framework 4.5 和更高版本。 但是，默认情况下，应用版本上运行公共语言运行时为其开发，因此你可能必须提供要启用您的应用程序的.NET Framework 4.5 或更高版本上运行的配置文件。 有关详细信息，请参阅本文前面的[应用的版本兼容性](#Apps)一节。  
  
 实际上，.NET Framework 中看似无关紧要的更改和编程技术上的更改会损坏此兼容性。 例如，.NET Framework 4.5 中的性能改进会公开早期版本中未出现的争用条件。 同样，使用 .NET Framework 程序集的硬编码路径，执行与特定版本的 .NET Framework 的相等比较，以及使用反射获取私有字段的值都不是向后兼容的做法。 此外，每个版本的 .NET Framework 都包含 Bug 修复和可能影响某些应用程序和组件的兼容性的安全相关更改。  
  
 如果你的应用或组件不能按预期显示在.NET Framework 4.5 上 (包括其单点发行版中， [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]，4.5.2、 4.6、 4.6.1、 4.6.2、 4.7 或 4.7.1，使用以下清单：  
  
-  如果你的应用程序开发的目的是从.NET Framework 4.0 的.NET framework 的任何版本上运行，请参阅[.NET Framework 中的应用程序兼容性](application-compatibility.md)生成目标的.NET Framework 版本之间的更改列表和在其运行你的应用程序的版本。  

- 如果你有.NET Framework 3.5 应用程序，另请参阅[.NET Framework 4 迁移问题](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)。

- 如果你有.NET Framework 2.0 应用程序，另请参阅[.NET Framework 3.5 SP1 中的更改](http://go.microsoft.com/fwlink/?LinkId=186989)。

- 如果你有.NET Framework 1.1 应用程序，另请参阅[.NET Framework 2.0 中的更改](http://go.microsoft.com/fwlink/?LinkID=125263)。  
  
-   如果要重新编译现有源代码以在.NET Framework 4.5 或其单点上运行的版本中，或者如果你正在开发的应用或目标的组件的新版本[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]或其单点版本从现有的源代码基，检查[什么是类库中的过时](../../../docs/framework/whats-new/whats-obsolete.md)了解过时类型和成员，并采用描述的解决方法。 （以前编译的代码将继续针对已标记为过时的类型和成员运行。）  
  
-   如果确定 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中的更改损坏了应用，请检查[运行时设置架构](../../../docs/framework/configure-apps/file-schema/runtime/index.md)，确定是否能在应用的配置文件中使用运行时设置来还原以前的行为。  
  
-   如果遇到未记录的问题，请记录 [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815) Bug，然后以电子邮件的形式将 Bug 号发送到 [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com)。  
  
## <a name="compatibility-and-side-by-side-execution"></a>兼容性和并行执行  
 如果找不到解决问题的适当方法，请记住，.NET Framework 4.5（或其中一个单点版本）是与版本 1.1、2.0 和 3.5 并行运行的，并且是取代版本 4 的就地更新。 对于以版本 1.1、2.0 和 3.5 为目标的应用程序，你可以在目标计算机上安装适当的 .NET Framework 版本以在其最佳环境中运行该应用程序。 有关并行执行的详细信息，请参阅[并行执行](../../../docs/framework/deployment/side-by-side-execution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [新增功能](../../../docs/framework/whats-new/index.md)  
 [类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)  
 [应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Microsoft .NET Framework 支持生命周期策略](http://go.microsoft.com/fwlink/p/?LinkId=248212)  
 [.NET Framework 4 迁移问题](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)
