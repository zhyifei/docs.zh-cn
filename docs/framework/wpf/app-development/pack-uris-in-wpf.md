---
title: WPF 中的 Pack URI
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: ad928fb223ce22c65bb86a78c7d4cd006651a2d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950757"
---
# <a name="pack-uris-in-wpf"></a>WPF 中的 Pack URI

在 Windows Presentation Foundation (WPF) 中[!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] , 用于通过多种方式标识和加载文件, 包括以下内容:

- [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]指定以显示应用程序第一次启动的时间。

- 加载图像。

- 导航到页。

- 加载不可执行的数据文件。

此外, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]可用于从各种位置识别和加载文件, 包括以下各项:

- 当前程序集。

- 引用的程序集。

- 相对于程序集的某个位置。

- 应用程序的源站点。

若要为从这些位置标识和加载这些类型的文件提供一致的机制[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , 利用*包 URI 方案*的扩展性。 本主题概述了方案, 涵盖了如何构建各种方案的包[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 、讨论绝对和相对[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]和[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]解决方法, 然后显示如何从两个标记使用 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]和代码。

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a>Pack URI 方案

打包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案由[开放式打包约定](https://go.microsoft.com/fwlink/?LinkID=71255)(OPC) 规范使用, 此规范描述了用于组织和标识内容的模型。 此模型的关键元素是包和部件, 其中,*包*是一个或多个逻辑*部分*的逻辑容器。 下图阐释了此概念。

![包和部件示意图](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

为了识别部件, OPC 规范利用了 RFC 2396 的扩展性 (统一资源标识符 (URI)):一般语法) 来定义包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案。

由[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]指定的方案由其前缀定义; http、ftp 和 file 是众所周知的示例。 Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案使用 "pack" 作为其方案, 并且包含两个组件: 颁发机构和路径。 下面是包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的格式。

pack://*机构*/*路径*

*颁发机构*指定包含部件的包类型, 而*路径*指定部件在包中的位置。

下图阐释了此概念：

![包、颁发机构与路径之间的关系](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

包和部件之间的关系类似于应用程序和文件之间的关系，其中应用程序（包）可以包含一个或多个文件（部件），包括：

- 编译到本地程序集内的资源文件。

- 编译到所引用的程序集内的资源文件。

- 编译到引用程序集内的资源文件。

- 内容文件。

- 源站点文件。

若要访问这些类型的文件[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , 支持两个权限: application:///和 siteoforigin:///。 application:/// 授权标识在编译时已知的应用程序数据文件，包括资源文件和内容文件。 siteoforigin:/// 授权标识源站点文件。 下图显示了每种授权的范围。

![Pack URI 示意图](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> 包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的颁发机构组件是嵌入[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的, 它指向包并且必须符合 RFC 2396。 另外，必须用字符“,”替换字符“/”，并且必须对保留字符（如“%”和“?”）进行转义。 有关详细信息，请参阅 OPC。

以下各节说明如何使用这两[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]个颁发机构构造包以及用于标识资源、内容和源站点文件的相应路径。

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a>资源文件 Pack URI

资源文件配置为 MSBuild `Resource`项并编译为程序集。 WPF 支持构造包 Uri, 这些 Uri 可用于标识编译到本地程序集中或编译到从本地程序集引用的程序集中的资源文件。

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a>本地程序集资源文件

编译到[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]本地程序集的资源文件的 pack 使用以下授权和路径:

- **授权**：application:///。

- **路径**:资源文件的名称, 包括其相对于本地程序集项目文件夹根目录的路径。

下面的示例演示一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]资源文件的 pack, 该资源文件位于本地程序集的项目文件夹的根目录中。

`pack://application:,,,/ResourceFile.xaml`

下面的示例演示一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]资源文件的 pack, 该资源文件位于本地程序集的项目文件夹的子文件夹中。

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a>引用的程序集资源文件

编译到[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用的程序集中的资源文件的 pack 使用以下授权和路径:

- **授权**：application:///。

- **路径**:编译到所引用的程序集中的资源文件的名称。 路径必须符合以下格式：

  *AssemblyShortName*{ *;版本*] { *;PublicKey*]; 组件/*路径*

  - **程序集短名称**：所引用的程序集的短名称。

  - **;版本** [可选]：所引用的包含资源文件的程序集的版本。 此部分在加载两个或多个具有相同短名称的引用程序集时使用。

  - **;公钥** [可选]：用于对引用程序集进行签名的公钥。 此部分在加载两个或多个具有相同短名称的引用程序集时使用。

  - **;组件**：指定所引用的程序集是从本地程序集引用的。

  - **/路径**：资源文件的名称，包括其相对于所引用程序集的项目文件夹根目录的路径。

下面的示例演示一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]资源文件的 pack, 该资源文件位于所引用程序集的项目文件夹的根目录中。

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

下面的示例演示一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]资源文件的 pack, 该资源文件位于所引用程序集的项目文件夹的子文件夹中。

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

下面的示例演示一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]资源文件的 pack, 该资源文件位于所引用的特定于版本的程序集的项目文件夹的根文件夹中。

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

请注意, 所[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用的程序集资源文件的包语法只能与 application:///机构一起使用。 例如, 在中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]不支持以下。

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a>内容文件 Pack URI

内容文件[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的 pack 使用以下授权和路径:

- **授权**：application:///。

- **路径**:内容文件的名称, 包括其相对于应用程序的主可执行程序集的文件系统位置的路径。

下面的示例演示一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]内容文件的 pack, 该文件与可执行程序集位于同一文件夹中。

`pack://application:,,,/ContentFile.xaml`

下面的示例演示一个[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]内容文件的 pack, 该内容文件位于相对于应用程序的可执行程序集的子文件夹中。

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> 不能导航到 HTML 内容文件。 该[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案仅支持导航到位于源站点的 HTML 文件。

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a>源站点 Pack URI

源站点[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]文件的 pack 使用以下授权和路径:

- **授权**：siteoforigin:///。

- **路径**:源站点文件的名称, 包括其相对于从中启动可执行程序集的位置的路径。

下面的示例演示了源[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]站点文件的 pack, 该文件存储在从中启动可执行程序集的位置。

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

下面的示例演示了源[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]站点文件的 pack, 该文件存储在相对于应用程序可执行程序集的启动位置的子文件夹中。

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a>页面文件

配置为 MSBuild `Page`项的 XAML 文件将以与资源文件相同的方式编译到程序集中。 因此, 可以`Page`使用资源文件的 pack uri 来标识 MSBuild 项。

通常配置为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] MSBuild`Page`项的文件类型具有以下项之一作为其根元素:

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a>绝对与相对 Pack URI

完全限定的包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]包括方案、颁发机构和路径, 并被视为绝对包。 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 作为开发人员的简化, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]元素通常允许使用相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]设置相应的属性, 其中只包含路径。

例如, 请考虑本地程序集中的[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]资源文件的以下绝对包。

`pack://application:,,,/ResourceFile.xaml`

引用此资源[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]文件的相对包如下所示。

`/ResourceFile.xaml`

> [!NOTE]
> 由于源站点文件不与程序集相关联, 因此只能用绝对包[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]来引用它们。

默认情况下, 相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]是相对于标记的位置或包含该引用的代码的。 但是, 如果使用前导反斜杠, 则相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用将被视为相对于应用程序的根。 例如，假设具有以下项目结构。

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

如果 Page1 包含[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用*根*\SubFolder\Page2.xaml 的, 则引用可以使用以下相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。

`Page2.xaml`

如果 Page1 包含[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用*根*\Page2.xaml 的, 则引用可以使用以下相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a>Pack URI 解析

Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]的格式使不同类型的文件的[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pack 能够看起来相同。 例如, 请考虑下面的绝对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。

`pack://application:,,,/ResourceOrContentFile.xaml`

此绝对包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]可以引用本地程序集或内容文件中的资源文件。 对于下面的相对[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], 这一点同样适用。

`/ResourceOrContentFile.xaml`

若要确定 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用的文件类型, 请[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]使用以下试探法解析[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]本地程序集和内容文件中的资源文件:

1. 探测与 pack <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]匹配的属性的程序集元数据。

2. 如果找到<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>该属性, 则包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的路径引用一个内容文件。

3. 如果找<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>不到该属性, 则探测编译到本地程序集的资源文件。

4. 如果找到与包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]路径匹配的资源文件, 则包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的路径引用资源文件。

5. 如果找不到该资源, 则内部创建<xref:System.Uri>的无效。

[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]解决方法不适用于[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]引用以下内容:

- 引用的程序集中的内容文件: 不支持[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]这些文件类型。

- 引用的程序集中的嵌入[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]文件: 标识它们是唯一的, 因为它们包括引用的程序集的名称`;component`和后缀。

- 源站点文件: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]标识它们是唯一的, 因为它们是可以由包含 siteoforigin:///机构的 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]标识的唯一文件。

Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]解析所允许的一种简化方法是使代码在一定程度上独立于资源和内容文件的位置。 例如, 如果在本地程序集中有一个资源文件, 该文件已重新配置为内容文件, 则该资源[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的包将保持不变, 使用包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的代码也是如此。

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a>使用 Pack URI 编程

许多[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]类实现可通过 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]进行设置的属性, 包括:

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

可以从标记和代码中设置这些属性。 本节演示这两种设置方式的基本构造，然后演示通用方案示例。

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a>在标记中使用 Pack URI

通过使用[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]设置特性的元素, 可在标记中指定 pack。 例如:

`<element attribute="pack://application:,,,/File.xaml" />`

表1说明了可以在标记[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]中指定的各种绝对包。

表 1:标记中的绝对 Pack Uri

|文件|绝对包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|资源文件 - 本地程序集|`"pack://application:,,,/ResourceFile.xaml"`|
|子文件夹中的资源文件 - 本地程序集|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|资源文件 - 引用的程序集|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|所引用程序集的子文件夹中的资源文件|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|所引用版本化程序集中的资源文件|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|内容文件|`"pack://application:,,,/ContentFile.xaml"`|
|子文件夹中的内容文件|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|源站点文件|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|子文件夹中的源站点文件|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

表2说明了可以在标记[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]中指定的各种相对 pack。

表 2:标记中的相对 Pack Uri

|文件|相对 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|本地程序集内的资源文件|`"/ResourceFile.xaml"`|
|本地程序集的子文件夹中的资源文件|`"/Subfolder/ResourceFile.xaml"`|
|所引用程序集内的资源文件|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|所引用程序集的子文件夹中的资源文件|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|内容文件|`"/ContentFile.xaml"`|
|子文件夹中的内容文件|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a>在代码中使用 Pack URI

通过[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]实例化类并将包作为参数传递给构造函数, 可以在代码中指定 pack。 <xref:System.Uri> 下面的示例说明了这一点。

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

默认情况下, <xref:System.Uri>类将 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]视为绝对。 因此, 当使用相对 pack <xref:System.Uri> [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]创建类的实例时, 将引发异常。

```csharp
Uri uri = new Uri("/File.xaml");
```

幸运的是<xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> , <xref:System.Uri>类构造函数的重载接受类型<xref:System.UriKind>的参数, 以允许您指定包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]是绝对的还是相对的。

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

你应仅<xref:System.UriKind.Absolute>指定或<xref:System.UriKind.Relative>在你确定所提供的包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]是另一个。 如果你不知道所使用的包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的类型 (例如, 当用户<xref:System.UriKind.RelativeOrAbsolute>在运行时进入包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]时), 请改用。

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

表3说明了可以使用[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] <xref:System.Uri?displayProperty=nameWithType>在代码中指定的各种相对 pack。

表 3:代码中的绝对 Pack Uri

|文件|绝对包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|资源文件 - 本地程序集|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|子文件夹中的资源文件 - 本地程序集|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|资源文件 - 引用的程序集|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|所引用程序集的子文件夹中的资源文件|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|所引用版本化程序集中的资源文件|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|内容文件|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|子文件夹中的内容文件|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|源站点文件|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|子文件夹中的源站点文件|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

表4说明了可使用[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] <xref:System.Uri?displayProperty=nameWithType>代码中指定的各种相对 pack。

表 4:代码中的相对 Pack Uri

|文件|相对 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|资源文件 - 本地程序集|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|子文件夹中的资源文件 - 本地程序集|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|资源文件 - 引用的程序集|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|子文件夹中的资源文件 - 引用的程序集|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|内容文件|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|子文件夹中的内容文件|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a>常见 Pack URI 方案

前面几节讨论了如何构造 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]以标识资源、内容和源站点文件。 在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]中, 这些构造以各种方式使用, 以下部分介绍了几种常见的用法。

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>指定当应用程序启动时显示的 UI

<xref:System.Windows.Application.StartupUri%2A>指定启动[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]应用[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]程序时要显示的第一个。 对于独立应用程序, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]可以是一个窗口, 如下面的示例中所示。

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

独立的应用[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]程序, 还可以将页指定为初始 UI, 如以下示例中所示。

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

如果应用程序是独立的应用程序, 并且使用<xref:System.Windows.Application.StartupUri%2A>指定了页面, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]则<xref:System.Windows.Navigation.NavigationWindow>会打开以承载页面。 对于[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], 该页面显示在主机浏览器中。

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a>导航到页面

下面的示例演示如何导航到页面。

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

有关在中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]导航的各种方式的详细信息, 请参阅[导航概述](navigation-overview.md)。

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a>指定窗口图标

下面的示例演示如何使用 URI 指定窗口的图标。

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

有关详细信息，请参阅 <xref:System.Windows.Window.Icon%2A>。

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a>加载图像、音频和视频文件

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]允许应用程序使用多种媒体类型, 所有这些类型都可以使用 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]进行标识和加载, 如下面的示例中所示。

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

有关使用媒体内容的详细信息, 请参阅[图形和多媒体](../graphics-multimedia/index.md)。

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>从源站点加载资源字典

资源字典 (<xref:System.Windows.ResourceDictionary>) 可用于支持应用程序主题。 创建和管理主题的一种方式是将多个主题创建为位于应用程序源站点的资源字典。 这样，在添加和更新主题时将无需重新编译和重新部署应用程序。 可以使用 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]标识并加载这些资源字典, 如以下示例中所示。

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

有关中[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]主题的概述, 请参阅[样式设置和模板化](../controls/styling-and-templating.md)。

## <a name="see-also"></a>请参阅

- [WPF 应用程序资源、内容和数据文件](wpf-application-resource-content-and-data-files.md)
