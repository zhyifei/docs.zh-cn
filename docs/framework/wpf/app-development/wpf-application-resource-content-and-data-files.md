---
title: 应用程序资源、内容和数据文件
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
ms.openlocfilehash: f17898972eeef66447060db32bae5fae377b710e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186192"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF 应用程序资源、内容和数据文件
Microsoft Windows 应用程序通常依赖于包含不可执行数据的文件，例如[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，图像、视频和音频。 Windows 演示基础 （WPF） 为配置、识别和使用这些类型的数据文件（称为应用程序数据文件）提供特殊支持。 这种支持主要针对一组特定的应用程序数据文件类型，包括：  
  
- **资源文件**：编译为可执行文件或库 WPF 程序集的数据文件。  
  
- **内容文件**：与可执行 WPF 程序集具有显式关联的独立数据文件。  
  
- **源文件站点**：与可执行 WPF 程序集没有关联的独立数据文件。  
  
 这三种类型的文件之间的一个重要区别是：资源文件和内容文件在生成时即为程序集所知；程序集明确知道它们的存在。 但是，对于源站点文件，程序集可能根本不了解它们，或者通过包统一资源标识符 （URI） 引用隐式知识;在后一种情况下，不能保证引用的源文件站点确实存在。  
  
 为了引用应用程序数据文件，Windows 演示基础 （WPF） 使用包统一资源标识符 （URI） 方案，这在[WPF 中的包 URI 中](pack-uris-in-wpf.md)进行了详细说明。  
  
 本主题介绍如何配置和使用应用程序数据文件。  

<a name="Resource_Files"></a>
## <a name="resource-files"></a>资源文件  
 如果应用程序数据文件必须始终可供某个应用程序使用，那么保证可用性的唯一方法是将其编译到应用程序的主可执行程序集内，或者它所引用的程序集内。 这种类型的应用程序数据文件称为*资源文件*。  
  
 应在以下情况下使用资源文件：  
  
- 将资源文件编译到程序集内之后，无需更新资源文件的内容。  
  
- 希望通过减少文件依赖项的数量来简化应用程序分发的复杂性。  
  
- 应用程序数据文件需要可本地化（请参阅[WPF 全球化和本地化概述](../advanced/wpf-globalization-and-localization-overview.md)）。  
  
> [!NOTE]
> 本节中描述的资源文件与[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)中描述的资源文件不同，与[管理应用程序资源 （.NET）](/visualstudio/ide/managing-application-resources-dotnet)中描述的嵌入或链接资源不同。  
  
### <a name="configuring-resource-files"></a>配置资源文件  
 在 WPF 中，资源文件是作为`Resource`项包含在 Microsoft 生成引擎 （MSBuild） 项目中的文件。  
  
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
> 在 Visual Studio 中，您可以通过将文件添加到项目并将其`Build Action`设置为`Resource`来创建资源文件。  
  
 生成项目时，MSBuild 会将资源编译到程序集中。  
  
### <a name="using-resource-files"></a>使用资源文件  
 要加载资源文件，可以调用<xref:System.Windows.Application.GetResourceStream%2A><xref:System.Windows.Application>类的方法，传递标识所需资源文件的包 URI。 <xref:System.Windows.Application.GetResourceStream%2A>返回一<xref:System.Windows.Resources.StreamResourceInfo>个对象，该对象将资源文件公开为<xref:System.IO.Stream>，并描述其内容类型。  
  
 例如，以下代码演示如何使用<xref:System.Windows.Application.GetResourceStream%2A>来加载<xref:System.Windows.Controls.Page>资源文件并将其设置为<xref:System.Windows.Controls.Frame>（`pageFrame`的内容）：  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 调用<xref:System.Windows.Application.GetResourceStream%2A>时，您需要<xref:System.IO.Stream>执行将之转换为要使用它设置的属性类型的其他工作。 相反，您可以通过使用代码将资源文件直接加载到类型的属性中来<xref:System.IO.Stream>处理打开和转换 的 WPF。  
  
 下面的示例演示如何使用代码直接加载<xref:System.Windows.Controls.Page>到<xref:System.Windows.Controls.Frame>（`pageFrame`） 中。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 下面的示例是与上例等效的标记。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>作为资源文件的应用程序代码文件  
 可以使用包 URI 引用一组特殊的 WPF 应用程序代码文件，包括窗口、页面、流文档和资源字典。 例如，可以使用引用应用程序启动时<xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>要加载的窗口或页面的包 URI 设置属性。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 当 XAML 文件作为项目包含在 MSBuild 项目中时，`Page`可以执行此操作。  
  
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
> 在 Visual Studio 中，<xref:System.Windows.Window>向<xref:System.Windows.Navigation.NavigationWindow>项目<xref:System.Windows.Controls.Page>添加新<xref:System.Windows.Documents.FlowDocument> <xref:System.Windows.ResourceDictionary> 、、、、`Build Action`标记文件将默认为`Page`。  
  
 编译具有`Page`项的项目时，这些项目[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]将转换为二进制格式并编译到关联的程序集中。 因此，可以像使用典型的资源文件一样使用这些文件。  
  
> [!NOTE]
> 如果[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件配置为项`Resource`，并且没有代码背后的文件，则原始[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件将编译为程序集，而不是原始[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的二进制版本。  
  
<a name="Content_Files"></a>
## <a name="content-files"></a>内容文件  
 *内容文件*与可执行程序集一起作为松散文件分发。 虽然它们不编译到程序集内，但编译程序集时所使用的元数据建立了与每个内容文件的关联。  
  
 如果应用程序需要一组特定的应用程序数据文件，并且你希望能够更新这些文件，而无需重新编译使用它们的程序集，应使用内容文件。  
  
### <a name="configuring-content-files"></a>配置内容文件  
 要将内容文件添加到项目，必须将应用程序数据文件作为项包含在内`Content`。 此外，由于内容文件未直接编译到程序集中，因此您需要设置 MSBuild`CopyToOutputDirectory`元数据元素以指定将内容文件复制到相对于生成的程序集的位置。 如果希望在每次生成项目时将资源复制到生成输出文件夹，则可以使用`CopyToOutputDirectory``Always`该值设置元数据元素。 否则，您可以确保仅使用`PreserveNewest`该值将资源的最新版本复制到生成输出文件夹。  
  
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
> 在 Visual Studio 中`Build Action`，通过将文件添加到项目并将其设置为`Content`（`Copy to Output Directory``Copy always`与`Always`） 和`Copy if newer`（与`PreserveNewest`相同） 创建内容文件来创建内容文件。  
  
 生成项目时，将属性<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>编译为每个内容文件的程序集元数据。  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 的值<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>意味着内容文件的路径相对于其在项目中的位置。 例如，如果内容文件位于项目子文件夹中，则其他路径信息将合并到该值中<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>。  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 该<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>值也是生成输出文件夹中内容文件的路径的值。  
  
### <a name="using-content-files"></a>使用内容文件  
 要加载内容文件，可以调用<xref:System.Windows.Application.GetContentStream%2A><xref:System.Windows.Application>类的方法，传递标识所需内容文件的包 URI。 <xref:System.Windows.Application.GetContentStream%2A>返回一<xref:System.Windows.Resources.StreamResourceInfo>个对象，该对象将内容文件公开为<xref:System.IO.Stream>，并描述其内容类型。  
  
 例如，以下代码演示如何使用<xref:System.Windows.Application.GetContentStream%2A>来加载<xref:System.Windows.Controls.Page>内容文件并将其设置为<xref:System.Windows.Controls.Frame>的内容 。`pageFrame`  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 调用<xref:System.Windows.Application.GetContentStream%2A>时，您需要<xref:System.IO.Stream>执行将之转换为要使用它设置的属性类型的其他工作。 相反，您可以通过使用代码将资源文件直接加载到类型的属性中来<xref:System.IO.Stream>处理打开和转换 的 WPF。  
  
 下面的示例演示如何使用代码直接加载<xref:System.Windows.Controls.Page>到<xref:System.Windows.Controls.Frame>（`pageFrame`） 中。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 下面的示例是与上例等效的标记。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a>源站点文件  
 资源文件与它们与它们一起分发的程序集具有显式关系，由 定义<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>。 但是，有些情况下可能需要在程序集和应用程序数据文件之间建立隐式关系或不存在的关系，这些情况包括：  
  
- 文件在编译时不存在。  
  
- 在运行之前不知道程序集将需要哪些文件。  
  
- 希望能够更新文件，无需重新编译与这些文件关联的程序集。  
  
- 应用程序使用大型数据文件（如音频和视频），并且你希望仅在用户选择下载时才下载这些文件。  
  
 可以使用传统的 URI 方案（如file:///和http://方案）加载这些类型的文件。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 但是，file:/// 和 http:// 方案要求应用程序具有完全信任。 如果应用程序是从 Internet 或 Intranet 启动的 XAML 浏览器应用程序 （XBAP），并且它仅请求允许从这些位置启动的应用程序的权限集，则只能从应用程序的原点（启动位置）。 此类文件称为源文件*站点*。  
  
 虽然源站点文件并不仅限于部分信任应用程序，但这些文件是部分信任应用程序的唯一选择。 完全信任应用程序可能仍然需要加载它们在生成时所不知道的应用程序数据文件；但是完全信任应用程序可以使用 file:///，应用程序数据文件很可能将安装在该应用程序程序集所在的文件夹或其子文件夹中。 在此情况下，使用源站点引用比使用 file:/// 更加容易，因为使用 file:/// 需要找出文件的完整路径。  
  
> [!NOTE]
> 源站点文件不会在客户端计算机上使用 XAML 浏览器应用程序 （XBAP） 缓存，而内容文件是。 因此，只有在专门请求下载源站点文件时，才会下载它们。 如果 XAML 浏览器应用程序 （XBAP） 应用程序具有大型媒体文件，将它们配置为源文件站点意味着初始应用程序启动速度更快，并且文件仅按需下载。  
  
### <a name="configuring-site-of-origin-files"></a>配置源站点文件  
 如果源站点文件在编译时不存在或未知，则需要使用传统的部署机制来确保所需的文件在运行时可用，包括使用`XCopy`命令行程序或 Microsoft Windows 安装程序。  
  
 如果在编译时确实知道要位于原点的文件，但仍希望避免显式依赖项，则可以将这些文件作为`None`项添加到 MSBuild 项目中。 与内容文件一样，您需要设置 MSBuild`CopyToOutputDirectory`属性，通过指定`Always`值或`PreserveNewest`值来指定原点文件复制到相对于生成的程序集的位置。  
  
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
> 在 Visual Studio 中，您可以通过将文件添加到项目并将其设置为`Build Action``None`来创建源网站文件。  
  
 生成项目时，MSBuild 会将指定的文件复制到生成输出文件夹。  
  
### <a name="using-site-of-origin-files"></a>使用源站点文件  
 要加载源站点文件，可以调用<xref:System.Windows.Application.GetRemoteStream%2A><xref:System.Windows.Application>类的方法，传递一个包 URI 来标识所需的源站点文件。 <xref:System.Windows.Application.GetRemoteStream%2A>返回一<xref:System.Windows.Resources.StreamResourceInfo>个对象，该对象将源文件的站点公开为<xref:System.IO.Stream>， 并描述其内容类型。  
  
 例如，<xref:System.Windows.Application.GetRemoteStream%2A>以下代码演示如何使用 来加载源<xref:System.Windows.Controls.Page>站点文件并将其设置为<xref:System.Windows.Controls.Frame>（`pageFrame`的内容）。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 调用<xref:System.Windows.Application.GetRemoteStream%2A>时，您需要<xref:System.IO.Stream>执行将之转换为要使用它设置的属性类型的其他工作。 相反，您可以通过使用代码将资源文件直接加载到类型的属性中来<xref:System.IO.Stream>处理打开和转换 的 WPF。  
  
 下面的示例演示如何使用代码直接加载<xref:System.Windows.Controls.Page>到<xref:System.Windows.Controls.Frame>（`pageFrame`） 中。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 下面的示例是与上例等效的标记。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a>更改生成类型后重新生成  
 在更改应用程序数据文件的生成类型后，需要重新生成整个应用程序以确保应用这些更改。 如果只生成应用程序，则不会应用更改。  
  
## <a name="see-also"></a>另请参阅

- [WPF 中的 Pack URI](pack-uris-in-wpf.md)
