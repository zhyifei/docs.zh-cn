---
title: "桌面应用程序中的资源 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "应用程序资源"
  - "部署应用程序 [.NET Framework], 资源"
  - "本地化"
  - "本地化资源"
  - "打包应用程序资源"
  - "资源文件"
  - "附属程序集"
ms.assetid: 8ad495d4-2941-40cf-bf64-e82e85825890
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# 桌面应用程序中的资源
几乎每一个生产性应用程序都需要使用资源。  资源是在逻辑上由应用程序部署的任何非可执行的数据。  资源可以在应用程序中作为错误消息显示，或者作为用户界面的一部分显示。  资源可以包含多种形式的数据，包括字符串、图像和持久的对象。（为了将持久对象写入资源文件，这些对象必须是可序列化的。）通过在资源文件中存储您的数据，您无需重新编译整个应用程序即可更改数据。  还可以在一个位置存储数据，而无需依赖于多个位置存储硬编码的数据。  
  
 在桌面app中.NET Framework 对本地应用程序资源的创建和本地化提供全面的支持。  此外，.NET Framework 还支持一个在桌面app中用于打包和部署这些本地化资源的简单模型。  
  
 有关 ASP.NET 中的资源的信息，请参见 [ASP.NET Web Page Resources Overview](../Topic/ASP.NET%20Web%20Page%20Resources%20Overview.md) 在 Internet Explorer 开发人员中心。  
  
 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps 使用来自桌面 app 的不同资源模型并将它们的资源存储到单个程序包资源索引 \(PRI\) 文件中。  有关 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app 资源的信息，请参见 [创建和检索资源在 Windows 应用商店应用](http://go.microsoft.com/fwlink/p/?LinkId=241674) Windows Dev 中心。  
  
## 创建和本地化资源  
 在一个非本地化的应用程序中，可以使用资源文件作为app 数据储存库，特别是为本来可能在源代码中的多个位置为硬编码的字符串。  通常，您创建文本 \(.txt\) 或 XML \(.resx\) 文件资源并且使用 [Resgen.exe（资源文件生成器）](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) 将其编译为二进制 .resources 文件。  这些文件可由语言编译器将其嵌入到应用程序的可执行文件中。  有关创建资源的详细信息，请参阅[创建资源文件](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)。  
  
 您还可以将应用程序的资源本地化为用于特定的区域性。  这使您可以生成应用程序的本地化（翻译的）版本。  在开发使用本地化资源的应用程序时，可以指定一个区域性作为非特定或回退区域，当没有合适的资源可用时启用他们的资源。  通常，非特定区域性的资源存储在可执行文件的 app 。  其余的各个本地化区域性资源存储在单独附属程序集中。  有关详细信息，请参阅[创建附属程序集](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)。  
  
## 打包和部署资源  
 您在 [附属程序集](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)中部署本地化 app 资源。  附属程序集包含单个区域性的资源；它不包含任何应用程序代码。  在附属程序集部署模型中，您将创建应用程序（通常是主程序集\) 的一个默认值程序集，以及该应用程序支持的每一区域性的一个附属程序集。  因为附属程序集不是主程序集的一部分，所以您不必替换该应用程序的主程序集，即可很容易地替换或更新与特定区域性相关的资源。  
  
 确定哪些资源将构成应用程序的默认资源程序集时要谨慎。  因为默认资源程序集是主程序集的一部分，对它做任何更改都将要求您替换主程序集。  如果您没有提供默认资源，则在[资源后备进程](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)尝试查找默认资源时，将会引发异常。  在设计良好的应用程序中，使用资源应永远不会引发异常。  
  
 有关更多信息，请参阅[打包和部署资源](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) 文章。  
  
## 检索资源  
 运行时，应用程序在每个线程基础上加载相应的本地化资源，具体取决于 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 属性指定的区域性。  此属性值派生如下所示：  
  
-   通过直接分配一个表现本地化区域性为 <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=fullName> 属性的 <xref:System.Globalization.CultureInfo> 对象。  
  
-   如果区域性不明确赋值，通过从 <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=fullName> 属性检索默认值线程 UI 区域性。  
  
-   如果默认值线程 UI 区域性不明确赋值，通过调用 Windows `GetUserDefaultUILanguage`函数来检索在本地计算机上的当前用户的区域性。  
  
 有关如何设置当前的 UI 区域性的详细信息，请参见 <xref:System.Globalization.CultureInfo> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 参考页。  
  
 通过使用 <xref:System.Resources.ResourceManager?displayProperty=fullName> 类，您可以为当前的 UI 区域性或特定区域性检索资源。  虽然 <xref:System.Resources.ResourceManager> 类最常用于检索桌面 app 资源，<xref:System.Resources?displayProperty=fullName> 命名空间包含可用于检索资源的其他类型。  这些元素包括：  
  
-   <xref:System.Resources.ResourceReader> 类，可以枚举嵌入在程序集或存储于独立二进制 .resources 文件中的资源。  当您不知道运行时可用资源的准确名称时这将会很有用。  
  
-   <xref:System.Resources.ResXResourceReader> 类，使您能够从 XML \(.resx\) 文件中检索资源。  
  
-   <xref:System.Resources.ResourceSet> 类，使您可以检索特定区域性资源，而不遵循回退规则。  资源可以存储在程序集或独立的二进制 .resources 文件中。  您还可以开发可以使用 <xref:System.Resources.ResourceSet> 选件类从某个其他源中检索资源的 <xref:System.Resources.IResourceReader> 实现。  
  
-   <xref:System.Resources.ResXResourceSet> 类，使您可以检索在 XML 资源文件中的所有项目到内存中。  
  
## 请参阅  
 <xref:System.Globalization.CultureInfo>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 [应用程序要点](../../../docs/standard/application-essentials.md)   
 [创建资源文件](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [打包和部署资源](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)   
 [创建附属程序集](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)   
 [检索资源](../../../docs/framework/resources/retrieving-resources-in-desktop-apps.md)