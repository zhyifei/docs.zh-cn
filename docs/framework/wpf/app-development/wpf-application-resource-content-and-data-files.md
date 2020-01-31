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
ms.openlocfilehash: ee636c49da64ad07ec5df2f11171b7f9aed713d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743362"
---
# <a name="wpf-application-resource-content-and-data-files"></a>WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일
Microsoft Windows 应用程序通常依赖于包含不可执行的数据的文件，例如 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]、图像、视频和音频。 Windows Presentation Foundation （WPF）为配置、标识和使用这些类型的数据文件（称为应用程序数据文件）提供特殊支持。 이러한 지원에는 다음을 포함한 특정 애플리케이션 데이터 파일 형식 집합이 포함됩니다.  
  
- **资源文件**：编译为可执行文件或库 WPF 程序集的数据文件。  
  
- **内容文件**：独立的数据文件，与可执行的 WPF 程序集具有显式关联。  
  
- **源站点文件**：与可执行 WPF 程序集没有关联的独立数据文件。  
  
 이 세 가지 파일 형식을 구분하는 한 가지 중요한 차이점은 리소스 파일과 콘텐츠 파일은 빌드할 때 인식된다는 점입니다. 어셈블리는 명시적으로 이 파일을 인식합니다. 但对于源站点文件，程序集可能根本不知道它们，或者通过包统一资源标识符（URI）引用隐式了解;对于后一种情况，不能保证引用的源站点文件确实存在。  
  
 若要引用应用程序数据文件，Windows Presentation Foundation （WPF）使用包统一资源标识符（URI）方案，详见 WPF 中的[Pack uri](pack-uris-in-wpf.md)。  
  
 이 항목에서는 애플리케이션 데이터 파일을 구성하고 사용하는 방법을 설명합니다.  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a>리소스 파일  
 애플리케이션에서 애플리케이션 데이터 파일을 항상 사용할 수 있어야 하는 경우 가용성을 보장하는 유일한 방법은 데이터 파일을 애플리케이션의 주 실행 어셈블리 또는 참조되는 어셈블리 중 하나로 컴파일하는 것입니다. 这种类型的应用程序数据文件称为*资源文件*。  
  
 다음과 같은 경우에 리소스 파일을 사용해야 합니다.  
  
- 어셈블리로 컴파일한 뒤에는 리소스 파일의 콘텐츠를 업데이트할 필요가 없는 경우.  
  
- 파일 종속성의 수를 줄여 애플리케이션 배포의 복잡성을 줄이려는 경우.  
  
- 应用程序数据文件需要可本地化（请参阅[WPF 全球化和本地化概述](../advanced/wpf-globalization-and-localization-overview.md)）。  
  
> [!NOTE]
> 本节中所述的资源文件不同于[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)中所述的资源文件，与[管理应用程序资源（.net）](/visualstudio/ide/managing-application-resources-dotnet)中所述的嵌入或链接的资源不同。  
  
### <a name="configuring-resource-files"></a>리소스 파일 구성  
 在 WPF 中，资源文件是作为 `Resource` 项包含在 Microsoft 生成引擎（MSBuild）项目中的文件。  
  
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
> 在 Visual Studio 中，可以通过将文件添加到项目并将其 `Build Action` 设置为 `Resource`来创建资源文件。  
  
 生成项目时，MSBuild 会将资源编译到程序集中。  
  
### <a name="using-resource-files"></a>리소스 파일 사용  
 若要加载资源文件，可以调用 <xref:System.Windows.Application> 类的 <xref:System.Windows.Application.GetResourceStream%2A> 方法，同时传递标识所需资源文件的包 URI。 <xref:System.Windows.Application.GetResourceStream%2A> 返回一个 <xref:System.Windows.Resources.StreamResourceInfo> 对象，该对象将资源文件公开为 <xref:System.IO.Stream> 并描述其内容类型。  
  
 例如，下面的代码演示如何使用 <xref:System.Windows.Application.GetResourceStream%2A> 加载 <xref:System.Windows.Controls.Page> 资源文件并将其设置为 <xref:System.Windows.Controls.Frame> （`pageFrame`）的内容：  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 当调用 <xref:System.Windows.Application.GetResourceStream%2A> 使你能够访问 <xref:System.IO.Stream>时，需要执行其他工作，将其转换为你要将其设置到的属性的类型。 相反，你可以让 WPF 通过使用代码将资源文件直接加载到类型的属性中来处理 <xref:System.IO.Stream> 的打开和转换。  
  
 下面的示例演示如何使用代码将 <xref:System.Windows.Controls.Page> 直接加载到 <xref:System.Windows.Controls.Frame> （`pageFrame`）。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>리소스 파일로 사용되는 애플리케이션 코드 파일  
 使用包 Uri 可以引用一组特殊的 WPF 应用程序代码文件，包括 windows、页面、流文档和资源字典。 例如，你可以使用一个包 URI 设置 <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> 属性，该 URL 引用在应用程序启动时要加载的窗口或页面。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 当将 XAML 文件作为 `Page` 项包含在 MSBuild 项目中时，可以执行此操作。  
  
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
> 在 Visual Studio 中，向项目添加新的 <xref:System.Windows.Window>、<xref:System.Windows.Navigation.NavigationWindow>、<xref:System.Windows.Controls.Page>、<xref:System.Windows.Documents.FlowDocument>或 <xref:System.Windows.ResourceDictionary> 时，标记文件的 `Build Action` 默认为 `Page`。  
  
 在编译具有 `Page` 项的项目时，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 项将转换为二进制格式，并编译到关联的程序集中。 결과적으로 이 파일을 일반적인 리소스 파일과 같은 방법으로 사용할 수 있습니다.  
  
> [!NOTE]
> 如果 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件配置为 `Resource` 项，但没有代码隐藏文件，则原始 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 会编译为程序集，而不是原始 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的二进制版本。  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>콘텐츠 파일  
 *内容文件*与可执行程序集一起分发为松散文件。 어셈블리로 컴파일되지는 않지만 어셈블리는 각 콘텐츠 파일과 연결되는 메타데이터와 함께 컴파일됩니다.  
  
 데이터 파일을 사용하는 어셈블리를 재컴파일하지 않고 업데이트하고자 하는 애플리케이션 데이터 파일을 애플리케이션에서 필요로 할 때는 콘텐츠 파일을 사용해야 합니다.  
  
### <a name="configuring-content-files"></a>콘텐츠 파일 구성  
 若要将内容文件添加到项目中，应用程序数据文件必须作为 `Content` 项包含在内。 此外，由于不会将内容文件直接编译到程序集中，因此需要设置 MSBuild `CopyToOutputDirectory` metadata 元素，以指定将内容文件复制到相对于生成的程序集的位置。 如果希望在每次生成项目时将资源复制到生成输出文件夹，请使用 `Always` 值设置 `CopyToOutputDirectory` 元数据元素。 否则，你可以通过使用 `PreserveNewest` 值来确保只将最新版本的资源复制到生成输出文件夹。  
  
 다음 예제에서는 리소스의 새 버전이 프로젝트에 추가된 경우에만 콘텐츠 파일이 빌드 출력 폴더에 복사되는 방식으로 구성된 파일을 보여 줍니다.  
  
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
> 在 Visual Studio 中，你可以通过将文件添加到项目并将其 `Build Action` 设置为 `Content`来创建内容文件，并将其 `Copy to Output Directory` 设置为 `Copy always` （与 `Always`相同）和 `Copy if newer` （与 `PreserveNewest`相同）。  
  
 生成项目时，会将 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性编译到每个内容文件的程序集的元数据中。  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 的值表示内容文件相对于其在项目中的位置的路径。 例如，如果内容文件位于项目子文件夹中，则其他路径信息将合并到 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 值中。  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 值也是内容文件在生成输出文件夹中的路径的值。  
  
### <a name="using-content-files"></a>콘텐츠 파일 사용  
 若要加载内容文件，可以调用 <xref:System.Windows.Application> 类的 <xref:System.Windows.Application.GetContentStream%2A> 方法，同时传递标识所需内容文件的包 URI。 <xref:System.Windows.Application.GetContentStream%2A> 返回一个 <xref:System.Windows.Resources.StreamResourceInfo> 对象，该对象将内容文件作为 <xref:System.IO.Stream> 公开，并描述其内容类型。  
  
 例如，下面的代码演示如何使用 <xref:System.Windows.Application.GetContentStream%2A> 加载 <xref:System.Windows.Controls.Page> 的内容文件，并将其设置为 <xref:System.Windows.Controls.Frame> （`pageFrame`）的内容。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 当调用 <xref:System.Windows.Application.GetContentStream%2A> 使你能够访问 <xref:System.IO.Stream>时，需要执行其他工作，将其转换为你要将其设置到的属性的类型。 相反，你可以让 WPF 通过使用代码将资源文件直接加载到类型的属性中来处理 <xref:System.IO.Stream> 的打开和转换。  
  
 下面的示例演示如何使用代码将 <xref:System.Windows.Controls.Page> 直接加载到 <xref:System.Windows.Controls.Frame> （`pageFrame`）。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>원본 사이트 파일  
 资源文件与一起分发的程序集具有显式关系，如 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>所定义。 하지만 다음과 같이 어셈블리와 애플리케이션 데이터 파일 사이에 암시적 관계 또는 존재하지 않는 관계를 설정해야 할 경우가 종종 있습니다.  
  
- 文件在编译时不存在。  
  
- 런타임까지 어셈블리에 필요한 파일을 모르는 경우.  
  
- 연결된 어셈블리를 재컴파일하지 않고 파일을 업데이트할 수 있어야 하는 경우.  
  
- 애플리케이션에서 오디오나 비디오와 같은 대용량 데이터 파일을 사용하며 사용자가 필요할 때에만 이를 다운로드하도록 하려는 경우.  
  
 可以通过使用传统的 URI 方案（例如 file:///和 http://方案）加载这些类型的文件。  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 하지만 file:/// 및 http:// 스키마를 사용하려면 애플리케이션이 완전히 신뢰되어야 합니다. 如果你的应用程序是从 Internet 或 intranet 启动的 XAML 浏览器应用程序（XBAP），并且该应用程序只请求从这些位置启动的应用程序允许的权限集，则松散文件只能从应用程序的源站点（启动位置）。 此类文件称为*源站点*文件。  
  
 원본 사이트 파일이 부분 신뢰 애플리케이션에서만 사용되는 것은 아니지만 부분 신뢰 애플리케이션에서는 원본 사이트 파일만을 사용할 수 있습니다. 완전 신뢰 애플리케이션의 경우에서도 빌드할 때 인식하지 못한 애플리케이션 데이터 파일을 로드해야 할 경우가 있습니다. 완전 신뢰 애플리케이션은 file:///을 사용할 수 있지만 이 경우 애플리케이션 데이터 파일이 애플리케이션 어셈블리와 같은 폴더 또는 하위 폴더에 설치될 수 있습니다. file:///에는 파일의 전체 경로를 사용해야 하기 때문에 file:///을 사용하는 방법보다 원본 사이트 참조를 사용하는 방법이 쉽습니다.  
  
> [!NOTE]
> 源站点文件不与客户端计算机上的 XAML 浏览器应用程序（XBAP）缓存，而内容文件为。 따라서 구체적으로 요청된 경우에만 다운로드됩니다. 如果 XAML 浏览器应用程序（XBAP）应用程序包含大型媒体文件，则将其配置为源站点文件意味着初始应用程序的启动速度要快得多，并且仅按需下载这些文件。  
  
### <a name="configuring-site-of-origin-files"></a>원본 사이트 파일 구성  
 如果源站点文件在编译时不存在或未知，则需要使用传统的部署机制来确保在运行时可以使用所需的文件，包括使用 `XCopy` 命令行程序或 Microsoft Windows Installer。  
  
 如果你在编译时知道想要位于源站点的文件，但仍希望避免显式依赖项，则可以将这些文件作为 `None` 项添加到 MSBuild 项目。 与内容文件一样，需要设置 MSBuild `CopyToOutputDirectory` 特性，以指定将源站点文件复制到相对于生成的程序集的位置，方法是指定 `Always` 值或 `PreserveNewest` 值。  
  
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
> 在 Visual Studio 中，你可以通过将文件添加到项目并将其 `Build Action` 设置为 `None`来创建源站点文件。  
  
 生成项目时，MSBuild 会将指定的文件复制到生成输出文件夹。  
  
### <a name="using-site-of-origin-files"></a>원본 사이트 파일 사용  
 若要加载源站点文件，可以调用 <xref:System.Windows.Application> 类的 <xref:System.Windows.Application.GetRemoteStream%2A> 方法，同时传递标识所需的源站点文件的包 URI。 <xref:System.Windows.Application.GetRemoteStream%2A> 返回一个 <xref:System.Windows.Resources.StreamResourceInfo> 对象，该对象将源站点文件作为 <xref:System.IO.Stream> 公开，并描述其内容类型。  
  
 例如，下面的代码演示如何使用 <xref:System.Windows.Application.GetRemoteStream%2A> 加载 <xref:System.Windows.Controls.Page> 的源站点文件，并将其设置为 <xref:System.Windows.Controls.Frame> （`pageFrame`）的内容。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 当调用 <xref:System.Windows.Application.GetRemoteStream%2A> 使你能够访问 <xref:System.IO.Stream>时，需要执行其他工作，将其转换为你要将其设置到的属性的类型。 相反，你可以让 WPF 通过使用代码将资源文件直接加载到类型的属性中来处理 <xref:System.IO.Stream> 的打开和转换。  
  
 下面的示例演示如何使用代码将 <xref:System.Windows.Controls.Page> 直接加载到 <xref:System.Windows.Controls.Frame> （`pageFrame`）。  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>빌드 형식 변경 후 다시 빌드  
 애플리케이션 데이터 파일의 빌드 형식을 변경한 뒤에는 변경 내용이 적용되도록 전체 애플리케이션을 다시 빌드해야 합니다. 애플리케이션만 빌드하면 변경 내용이 적용되지 않습니다.  
  
## <a name="see-also"></a>另请参阅

- [WPF의 Pack URI](pack-uris-in-wpf.md)
