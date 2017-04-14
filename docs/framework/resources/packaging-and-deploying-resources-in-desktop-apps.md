---
title: "打包和部署桌面应用程序中的资源 | Microsoft Docs"
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
  - "部署应用程序 [.NET Framework]，资源"
  - "资源文件，部署"
  - "轮毂和辐条资源部署模型"
  - "资源文件，打包"
  - "应用程序资源，打包"
  - "单个资源程序集"
  - "附属程序集"
  - "应用程序的默认区域性"
  - "名称 [.NET Framework]，资源"
  - "资源的回调过程"
  - "分组区域性"
  - "应用程序资源，部署"
  - "应用程序资源，命名约定"
  - "区域性，打包和部署资源"
  - "资源文件，命名约定"
  - "打包应用程序资源"
  - "应用程序资源，回退进程"
  - "资源文件，回退进程"
  - "本地化资源"
  - "非特定区域性"
ms.assetid: b224d7c0-35f8-4e82-a705-dd76795e8d16
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# 打包和部署桌面应用程序中的资源
应用程序依赖于 .NET Framework 资源管理器，由 <xref:System.Resources.ResourceManager> 类表示，来检索本地化的资源。  资源管理器假设轮辐式模型来打包和部署资源。  集中式模型是主程序集，它包含不可本地化的可执行代码以及用于单个区域性（称作非特定区域性或默认区域性）的资源。  默认区域性是应用程序的后备区域性；如果本地化的资源未能找到，它是使用其资源的区域性。  每一辐条均连接到一个附属程序集，该附属程序集包含单个区域性的资源，但不包含任何代码。  
  
 此模型具有以下几项优点：  
  
-   您可以在应用程序开发结束后为新区域性逐渐添加资源。  因为以后的特定于区域性的资源的开发可能需要耗费大量的时间，所以这一优点使您可以首先发布您的主应用程序，并在以后提供特定于区域性的资源。  
  
-   您无需重新编译应用程序，即可更新和更改应用程序的附属程序集。  
  
-   应用程序只需加载那些包含特定区域性所需的资源的附属程序集。  这可以显著减少对系统资源的占用。  
  
 但是，此模型也存在一些不足：  
  
-   您必须管理多个资源组。  
  
-   测试应用程序的初始成本将增加，因为您必须测试几个配置。  请注意，从长远角度来看，同测试及维护几个并行的国际版本相比较，测试具有几个附属程序集的核心应用程序更简便、成本更低。  
  
## 资源命名规则  
 在打包您的应用程序的资源时，您必须使用适合于公共语言运行时的资源命名规则命名这些资源。  运行时通过资源的区域性签名标识一个资源。  将为每个区域性给定一个唯一的名称，该名称通常由与语言相关的两个小写字母的区域性名称和（如果需要）与国家或地区相关的两个大写字母的子区域性名称组成。  子区域性名称位于区域性名称之后，用短划线 \(\-\) 隔开。  示例包括在日本讲的日语ja\-JP，在美国讲的英语 en\-US，在德国讲的德语de\-DE，或者在澳大利亚讲的德语de\-AT。  参见 [区域语言支持 \(NLS\) API 参考](http://go.microsoft.com/fwlink/?LinkId=200048) 在转到全局 Developer Center 为区域性名称的完整列表。  
  
> [!NOTE]
>  有关创建资源文件的信息，请参见MSDN Library上的[创建资源文件](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md) 和 [创建附属程序集](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md) 。  
  
<a name="cpconpackagingdeployingresourcesanchor1"></a>   
## 资源回退进程  
 用于打包和部署资源的轮辐式模型使用回退进程来定位合适的资源。  如果应用程序的用户请求不可用的本地化资源，则公共语言运行时为与该用户请求最匹配的适当后备资源搜索该区域性的层次结构，并且只在迫不得已的情况下才引发异常。  在层次结构的每一级别，只要发现了适当的资源，运行时就使用该资源。  如果未找到合适的资源，则继续在下一个级别进行搜索。  
  
 若要提高查找性能，请将 <xref:System.Resources.NeutralResourcesLanguageAttribute> 特性应用于您的主程序集，并传递给它将用于您的主程序集的非特定语言的名称。  
  
> [!TIP]
>  您可以使用 [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) 配置元素优化运行时的资源程序集的进程和探查资源回退进程。  有关更多信息，请参见 [优化资源回退进程](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#Optimizing)一节。  
  
 资源后备进程将在下面的步骤中涉及：  
  
1.  运行时首先检查[全局程序集缓存](../../../docs/framework/app-domains/gac.md)，以找到与为应用程序请求的区域性匹配的程序集。  
  
     全局程序集缓存可以存储由许多应用程序共享的资源程序集。  这使您免去不得不在您创建的每一应用程序的目录结构中包括特定资源组之苦。  如果运行时找到了对程序集的引用，则它将搜索该程序集以找到请求的资源。  如果它在程序集中找到了该项，将使用请求的资源。  如果它没有找到该项，将继续搜索。  
  
2.  运行时接下来检查当前执行的程序集的目录以找到与请求的区域性匹配的目录。  如果它找到了匹配的目录，它将搜索该目录以找到请求的区域性的有效附属程序集。  然后运行时搜索该有效附属程序集以找到请求的资源。  如果它在程序集中找到了该资源，则使用这一资源。  如果它没有找到该资源，将继续搜索。  
  
3.  运行时接下来查询Windows Installer以确定附属程序集是按需安装。  如果是这样，则会处理安装，加载程序集，并搜索其或请求的资源。  如果它在程序集中找到了该资源，则使用这一资源。  如果它没有找到该资源，将继续搜索。  
  
4.  运行时引发 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 事件指示无法查找附属程序集。  如果选择处理事件，则事件处理程序可以返回至对查找将使用资源的附属程序集。  否则，该事件处理程序会返回 `null`，同时继续搜索。  
  
5.  运行时接下来再次搜索全局程序集缓存，这一次是为了找到请求的区域性的父程序集。  如果在全局程序集缓存中存在资源的父程序集，则运行时搜索该程序集以找到请求的资源。  
  
     父程序区域性被定义为合适的后备区域性。  将父程序集视作后备的候选，因为提供任意资源要比引发一个异常更可取。  此进程还允许您重复使用资源。  只有在子区域性不需要本地化请求的资源时，您应该包括父级别的特定的资源。  例如，如果您提供 en（非特定英语），en\-GB（英国英语）和 en\-US（美国英语）的附属程序集，则 en 附属程序集应包含公共术语，并且 en\-GB 和 en\-US 附属程序集可能只对那些不同的术语提供重写。  
  
6.  运行时接下来检查当前执行的程序集的目录，以查看该目录中是否包含父目录。  如果存在父目录，则运行时搜索该目录以找到父区域性的有效附属程序集。  如果它找到了有效附属程序集，则运行时搜索该程序集以找到请求的资源。  如果它找到了该资源，则使用它。  如果它没有找到该资源，将继续搜索。  
  
7.  运行时接下来查询Windows Installer以确定父附属程序集是按需安装。  如果是这样，则会处理安装，加载程序集，并搜索其或请求的资源。  如果它在程序集中找到了该资源，则使用这一资源。  如果它没有找到该资源，将继续搜索。  
  
8.  运行时引发 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 事件，该时间指示无法找到一个合适的后备资源。  如果选择处理事件，则事件处理程序可以返回至对查找将使用资源的附属程序集。  否则，该事件处理程序会返回 `null`，同时继续搜索。  
  
9. 运行时接下来在许多可能的级别搜索父程序集（如前面三个步骤中所述）。  每一区域性只有一个父区域性，由 <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=fullName> 属性定义的，即，但一个父区域性可能还有其自己的父区域性。  当区域性的 <xref:System.Globalization.CultureInfo.Parent%2A> 属性返回 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>，父区域性的搜索停止；对于资源回退，固定区域性视为可以存在资源的父区域性或区域性。  
  
10. 如果对最初指定的区域性以及所有父区域性都进行了搜索但仍然未找到所需资源，则使用默认（回退）区域性的资源。  通常，默认区域性的资源放置在主应用程序集中。  但是，可以为 <xref:System.Resources.NeutralResourcesLanguageAttribute> 特性的 <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A> 属性的值 <xref:System.Resources.UltimateResourceFallbackLocation> 指示资源的最终后备位置是附属程序集，而不是主程序集。  
  
    > [!NOTE]
    >  默认资源是由主程序集编译的唯一资源。  除非使用 <xref:System.Resources.NeutralResourcesLanguageAttribute>属性指定附属程序集，否则它是最终后备（最终父程序集）。  因此，强烈建议您始终将默认的资源组包括在您的主程序集中。  这有助于防止引发异常。  通过包括默认的资源文件，您可以为所有资源提供回退，并且确保对于该用户始终提供至少一个资源，即使该资源不是特定于区域性的。  
  
11. 最后，如果运行时没有找到默认（后备）区域性的资源，则将引发<xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException>异常，指示未能找到资源。  
  
 例如，假设应用程序为西班牙语\(墨西哥\) \(es\-MX区域性\)请求一个资源本地化。  运行时首先搜索匹配 es\-MX 的程序集的全局程序集缓存 \(GAC\)，但未找到。  运行时搜索当前执行的程序集的目录以找到“es\-MX”目录。  如果也没有找到该目录，运行时再次搜索全局程序集缓存以找到反映适当的后备区域性，在此例子中为“es”（西班牙语）的父程序集。  如果没有找到父程序集，则运行时搜索所有潜在的父程序集级别以找到“es\-MX”区域性，直到找到相应的资源为止。  如果还是没有找到一个合适的资源，则运行时使用默认区域性的资源。  
  
<a name="Optimizing"></a>   
### 优化资源回退进程  
 在以下情况下，运行时可以优化进程，这样运行时在附属程序集中搜索资源。  
  
-   附属程序集部署的位置和代码程序集的位置相同。  如果代码程序集在安装 [全局程序集缓存](../../../docs/framework/app-domains/gac.md)，附属程序集在全局程序集缓存中进行安装。  如果代码程序集在目录中安装，附属程序集安装在位于该目录特定于区域性的文件夹。  
  
-   附属程序集中没有按需安装。  
  
-   应用程序代码不处理 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 事件。  
  
 如下例所示，可以通过在应用程序配置文件中包括 [\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md) 元素并将其 `enabled` 特性设置为`true`。  
  
```  
  
<configuration>  
   <runtime>  
      <relativeBindForResources enabled="true" />  
   </runtime>  
</configuration>  
  
```  
  
 附属程序集优化探测是一种可考虑的功能。  即运行时按照[资源回退进程](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md#cpconpackagingdeployingresourcesanchor1)除非[\<relativeBindForResources\>](../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)元素存在于应用程序的配置文件，且其`enabled`特性设置为`true`。  如果的确如此，附属程序集进行修改进程探查如下：  
  
-   运行时使用该父代码程序集的位置来进行附属程序集的探测。  如果父程序集位于全局程序集缓存安装，运行时在缓存中探测，但不在应用程序的目录。  如果父程序集在应用程序目录中安装，运行时在应用程序目录中探测，但不在全局程序集缓存。  
  
-   运行时不查询附属程序集的按需安装程序的 Windows Installer。  
  
-   如果特定资源程序集的探测失败，则运行时不会引发 <xref:System.AppDomain.AssemblyResolve?displayProperty=fullName> 事件。  
  
### 将最终回退放置在附属程序集中  
 可以选择从主程序集中移除资源和一种指定运行时应从与特定区域性对应的附属程序集中加载最终回退资源。  为控制后备进程，可以使用 <xref:System.Resources.NeutralResourcesLanguageAttribute.%23ctor%28System.String%2CSystem.Resources.UltimateResourceFallbackLocation%29?displayProperty=fullName> 构造函数并提供指定 <xref:System.Resources.UltimateResourceFallbackLocation> 参数的值，该参数指定资源管理器是否从主程序集中或附属程序集应提取回退资源。  
  
 下面的示例使用 <xref:System.Resources.NeutralResourcesLanguageAttribute> 特性在法语 \(fr\) 语言附属程序集中存储应用程序的后备资源。示例有定义了一个名为 `Greeting`的字符串资源的两个基于文本的资源文件。  第一，resources.fr.txt包含一法语资源。  
  
```  
Greeting=Bon jour!  
```  
  
 第二，资源，ru.txt，包含俄语资源。  
  
```  
Greeting=Добрый день  
```  
  
 这两个文件通过从命令行运行[资源文件生成器 \(Resgen.exe\)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)被编译为 .resources 文件。对于法语资源，命令是：  
  
 **resgen.exe resources.fr.txt**  
  
 对于俄语资源，命令是：  
  
 **resgen.exe resources.ru.txt**  
  
 .resources 文件通过从法语资源的命令行运行 [程序集链接器 \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)来下嵌入动态链接库，如下：  
  
 **al \/t:lib \/embed:resources.fr.resources \/culture:fr \/out:fr\\Example1.resources.dll**  
  
 对于俄语资源，如下：  
  
 **al \/t:lib \/embed:resources.ru.resources \/culture:ru \/out:ru\\Example1.resources.dll**  
  
 应用程序源代码驻留名为 Example1.cs 或 Example1.vb 的文件。  它包括 <xref:System.Resources.NeutralResourcesLanguageAttribute> 特性来表示默认应用程序资源在子目录中。  实例化该资源管理器中，检索 `Greeting`资源的值并显示到控制台。  
  
 [!code-csharp[Conceptual.Resources.Packaging#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.packaging/cs/example1.cs#1)]
 [!code-vb[Conceptual.Resources.Packaging#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.packaging/vb/example1.vb#1)]  
  
 可以从命令行编译 C\# 源代码如下所示：  
  
 **csc Example1.cs**  
  
 Visual Basic 编译器的命令非常相似：  
  
 **vbc Example1.vb**  
  
 由于没有嵌入在主程序集中的资源，使用 `/resource` 开关，则无需编译。  
  
 当从语言是任何语言（除了俄语）的系统上运行示例时，显示以下输出：  
  
```  
Bon jour!  
```  
  
## 建议的替代打包  
 由于时间或预算的约束，阻止为应用程序支持的每一子区域性均创建一组资源。  反而，在此情况中，您可以为所有相关子区域性可能使用的父区域性创建单个附属程序集。  例如，您可以提供单个英语附属程序集 \(en\)，请求特定于区域的英语资源的用户将检索该程序集，并且为请求特定于区域的德语资源创建单个德语附属程序集。  例如，对德国德语 \(de\-DE\)、奥地利德语 \(de\-AT\) 和瑞士德语 \(de\-CH\) 的请求都将后备到该德语附属程序集 \(de\)。  默认资源是最终后备资源，因而应是大多数应用程序用户将请求的资源，因此仔细选择资源。  应用程序部署较少特定于区域性的资源，但它能够显著降低您的应用程序的本地化成本。  
  
## 请参阅  
 [桌面应用程序中的资源](../../../docs/framework/resources/index.md)   
 [全局程序集缓存](../../../docs/framework/app-domains/gac.md)   
 [创建资源文件](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md)   
 [创建附属程序集](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md)