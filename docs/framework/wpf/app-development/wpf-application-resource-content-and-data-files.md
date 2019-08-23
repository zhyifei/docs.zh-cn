---
title: WPF 应用程序资源、内容和数据文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
ms.openlocfilehash: 57eae5067a72777db2c19331029b6df679a9fdce
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956193"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF 应用程序资源、内容和数据文件
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]应用程序通常依赖于包含不可执行的数据的文件, 例如[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]图像、视频和音频。 Windows Presentation Foundation (WPF) 为配置、标识和使用这些类型的数据文件 (称为应用程序数据文件) 提供特殊支持。 这种支持主要针对一组特定的应用程序数据文件类型，包括：  
  
- **资源文件**:编译到可执行文件或库[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]程序集中的数据文件。  
  
- **内容文件**:与可执行[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]程序集显式关联的独立数据文件。  
  
- **源站点文件**:独立的数据文件, 与可执行[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]程序集没有关联。  
  
 这三种类型的文件之间的一个重要区别是：资源文件和内容文件在生成时即为程序集所知；程序集明确知道它们的存在。 然而, 对于源站点文件, 程序集可能根本不知道它们, 或者通过包[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]引用隐式了解; 对于后一种情况, 不保证引用的源站点文件确实存在。  
  
 若要引用应用程序数据文件, Windows Presentation Foundation (wpf) 使用[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]打包方案, 详见 WPF 中的[pack uri](pack-uris-in-wpf.md)。  
  
 本主题介绍如何配置和使用应用程序数据文件。  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a>资源文件  
 如果应用程序数据文件必须始终可供某个应用程序使用，那么保证可用性的唯一方法是将其编译到应用程序的主可执行程序集内，或者它所引用的程序集内。 这种类型的应用程序数据文件称为*资源文件*。  
  
 应在以下情况下使用资源文件：  
  
- 将资源文件编译到程序集内之后，无需更新资源文件的内容。  
  
- 希望通过减少文件依赖项的数量来简化应用程序分发的复杂性。  
  
- 应用程序数据文件需要可本地化 (请参阅[WPF 全球化和本地化概述](../advanced/wpf-globalization-and-localization-overview.md))。  
  
> [!NOTE]
> 本节中所述的资源文件不同于[XAML 资源](../advanced/xaml-resources.md)中所述的资源文件, 与[管理应用程序资源 (.net)](/visualstudio/ide/managing-application-resources-dotnet)中所述的嵌入或链接的资源不同。  
  
### <a name="configuring-resource-files"></a>配置资源文件  
 在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]中, 资源文件是`Resource`作为项包含在 Microsoft 生成引擎 (MSBuild) 项目中的文件。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> 在[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]中, 可以通过将文件添加到项目并将其`Build Action`设置为来`Resource`创建资源文件。  
  
 生成项目时, MSBuild 会将资源编译到程序集中。  
  
### <a name="using-resource-files"></a>使用资源文件  
 若要加载资源文件, 可以调用<xref:System.Windows.Application.GetResourceStream%2A> <xref:System.Windows.Application>类的方法, 并传递标识所需资源[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]文件的包。 <xref:System.Windows.Application.GetResourceStream%2A>返回一个<xref:System.Windows.Resources.StreamResourceInfo>对象, 该对象将资源文件<xref:System.IO.Stream>作为公开, 并描述其内容类型。  
  
 例如, 下面的<xref:System.Windows.Application.GetResourceStream%2A>代码演示如何使用<xref:System.Windows.Controls.Page>加载资源文件并将其设置<xref:System.Windows.Controls.Frame>为 (`pageFrame`) 的内容:  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 虽然调用<xref:System.Windows.Application.GetResourceStream%2A>会使你<xref:System.IO.Stream>能够访问, 但你需要执行其他工作, 将其转换为你要将其设置为的属性类型。 相反, 你可以[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.IO.Stream>通过使用代码将资源文件直接加载到类型的属性中来开始处理和转换。  
  
 下面的示例演示如何使用代码将<xref:System.Windows.Controls.Page>直接加载<xref:System.Windows.Controls.Frame>到 (`pageFrame`)。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 下面的示例是与上例等效的标记。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>作为资源文件的应用程序代码文件  
 使用包[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]可以引用一组特殊的应用程序代码文件, 包括 windows、页面、流文档和资源字典。 例如, 你可以设置<xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>属性, 其中包含[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]在应用程序启动时要加载的窗口或页面。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 当将 XAML 文件作为`Page`项包含在 MSBuild 项目中时, 可以执行此操作。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> 在[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]中, 将新<xref:System.Windows.Window>的、 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page> `Build Action` 、、 `Page`或<xref:System.Windows.ResourceDictionary>添加到项目, 标记文件的将默认为。 <xref:System.Windows.Documents.FlowDocument>  
  
 在编译具有`Page`项的项目时[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , 项将转换为二进制格式, 并编译到关联的程序集中。 因此，可以像使用典型的资源文件一样使用这些文件。  
  
> [!NOTE]
> 如果将`Resource` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件配置为项, 但没有代码隐藏文件, 则会将原始文件编译为程序集而不是原始[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的二进制版本。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>内容文件  
 *内容文件*与可执行程序集一起分发为松散文件。 虽然它们不编译到程序集内，但编译程序集时所使用的元数据建立了与每个内容文件的关联。  
  
 如果应用程序需要一组特定的应用程序数据文件，并且你希望能够更新这些文件，而无需重新编译使用它们的程序集，应使用内容文件。  
  
### <a name="configuring-content-files"></a>配置内容文件  
 若要将内容文件添加到项目中, 必须将应用程序数据文件作为`Content`项包括在内。 此外, 由于不会将内容文件直接编译到程序集中, 因此需要设置 MSBuild `CopyToOutputDirectory` metadata 元素, 以指定将内容文件复制到相对于生成的程序集的位置。 如果希望在每次生成项目时将资源复制到生成输出文件夹, 请`CopyToOutputDirectory` `Always`使用值设置元数据元素。 否则, 你可以通过使用`PreserveNewest`值来确保只将最新版本的资源复制到生成输出文件夹。  
  
 下面演示的是一个配置为内容文件的文件，此内容文件只有在将新版本的资源添加到项目时才会复制到生成输出文件夹。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> 在[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]中, 你可以通过将文件添加到项目并将其`Build Action`设置`Content`为来创建内容文件`Always`, 并`Copy to Output Directory`将`Copy always`其设置为 (与`Copy if newer`相同) 和`PreserveNewest`(与相同)。  
  
 生成项目时, <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>会将属性编译到每个内容文件的程序集的元数据中。  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 的<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>值表示内容文件相对于其在项目中的位置的路径。 例如, 如果内容文件位于项目子文件夹中, 则其他路径信息将合并到<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>值中。  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>该值也是内容文件在生成输出文件夹中的路径的值。  
  
### <a name="using-content-files"></a>使用内容文件  
 若要加载内容文件, 可以调用<xref:System.Windows.Application.GetContentStream%2A> <xref:System.Windows.Application>类的方法, 并传递标识所需内容[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]文件的包。 <xref:System.Windows.Application.GetContentStream%2A>返回一个<xref:System.Windows.Resources.StreamResourceInfo>对象, 该对象将内容文件<xref:System.IO.Stream>作为公开, 并描述其内容类型。  
  
 例如, 下面的<xref:System.Windows.Application.GetContentStream%2A>代码演示如何使用<xref:System.Windows.Controls.Page>加载内容文件, 并将其设置<xref:System.Windows.Controls.Frame>为 (`pageFrame`) 的内容。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 虽然调用<xref:System.Windows.Application.GetContentStream%2A>会使你<xref:System.IO.Stream>能够访问, 但你需要执行其他工作, 将其转换为你要将其设置为的属性类型。 相反, 你可以[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.IO.Stream>通过使用代码将资源文件直接加载到类型的属性中来开始处理和转换。  
  
 下面的示例演示如何使用代码将<xref:System.Windows.Controls.Page>直接加载<xref:System.Windows.Controls.Frame>到 (`pageFrame`)。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 下面的示例是与上例等效的标记。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>源站点文件  
 资源文件与一起分发的程序集具有显式关系, 如定义<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>。 但是，有些情况下可能需要在程序集和应用程序数据文件之间建立隐式关系或不存在的关系，这些情况包括：  
  
- 文件在编译时不存在。  
  
- 在运行之前不知道程序集将需要哪些文件。  
  
- 希望能够更新文件，无需重新编译与这些文件关联的程序集。  
  
- 应用程序使用大型数据文件（如音频和视频），并且你希望仅在用户选择下载时才下载这些文件。  
  
 可以通过使用传统[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案 (例如 file:///和 http://方案) 加载这些类型的文件。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 但是，file:/// 和 http:// 方案要求应用程序具有完全信任。 如果你的应用程序[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]是从 Internet 或 intranet 启动的, 并且该应用程序只请求从这些位置启动的应用程序允许的权限集, 则只有应用程序的源站点可以加载松散文件 (启动位置)。 此类文件称为*源站点*文件。  
  
 虽然源站点文件并不仅限于部分信任应用程序，但这些文件是部分信任应用程序的唯一选择。 完全信任应用程序可能仍然需要加载它们在生成时所不知道的应用程序数据文件；但是完全信任应用程序可以使用 file:///，应用程序数据文件很可能将安装在该应用程序程序集所在的文件夹或其子文件夹中。 在此情况下，使用源站点引用比使用 file:/// 更加容易，因为使用 file:/// 需要找出文件的完整路径。  
  
> [!NOTE]
> 源站点文件不会[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]在客户端计算机上缓存, 而内容文件为。 因此，只有在专门请求下载源站点文件时，才会下载它们。 如果某个[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]应用程序包含大型媒体文件, 则将其配置为源站点文件意味着初始的应用程序启动速度更快, 且仅按需下载这些文件。  
  
### <a name="configuring-site-of-origin-files"></a>配置源站点文件  
 如果源站点文件在编译时不存在或未知, 则需要使用传统的部署机制来确保在运行时提供所需的文件, 包括使用`XCopy`命令行程序或[!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 如果你在编译时知道想要位于源站点的文件, 但仍希望避免显式依赖项, 则可以将这些文件作为`None`项添加到 MSBuild 项目。 与内容文件一样, 需要设置 MSBuild `CopyToOutputDirectory`属性以指定将源站点文件复制到相对于生成的程序集的位置, 方法是指定`Always`值或`PreserveNewest`值。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
> 在[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]中, 可以通过将文件添加到项目并将其`Build Action`设置为来`None`创建源站点文件。  
  
 生成项目时, MSBuild 会将指定的文件复制到生成输出文件夹。  
  
### <a name="using-site-of-origin-files"></a>使用源站点文件  
 若要加载源站点文件, 可以调用<xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.Windows.Application>类的方法, 同时传递标识所需的源[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]站点文件的包。 <xref:System.Windows.Application.GetRemoteStream%2A>返回一个<xref:System.Windows.Resources.StreamResourceInfo>对象, 该对象将源站点文件<xref:System.IO.Stream>作为公开, 并描述其内容类型。  
  
 例如, 下面的<xref:System.Windows.Application.GetRemoteStream%2A>代码演示如何使用<xref:System.Windows.Controls.Page>加载源站点文件并将其设置<xref:System.Windows.Controls.Frame>为 (`pageFrame`) 的内容。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 虽然调用<xref:System.Windows.Application.GetRemoteStream%2A>会使你<xref:System.IO.Stream>能够访问, 但你需要执行其他工作, 将其转换为你要将其设置为的属性类型。 相反, 你可以[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.IO.Stream>通过使用代码将资源文件直接加载到类型的属性中来开始处理和转换。  
  
 下面的示例演示如何使用代码将<xref:System.Windows.Controls.Page>直接加载<xref:System.Windows.Controls.Frame>到 (`pageFrame`)。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 下面的示例是与上例等效的标记。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>更改生成类型后重新生成  
 在更改应用程序数据文件的生成类型后，需要重新生成整个应用程序以确保应用这些更改。 如果只生成应用程序，则不会应用更改。  
  
## <a name="see-also"></a>请参阅

- [WPF 中的 Pack URI](pack-uris-in-wpf.md)
