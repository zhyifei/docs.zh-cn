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
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="78ea4-102">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="78ea4-102">WPF Application Resource, Content, and Data Files</span></span>
<span data-ttu-id="78ea4-103">Microsoft Windows 应用程序通常依赖于包含不可执行的数据的文件，例如 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]、图像、视频和音频。</span><span class="sxs-lookup"><span data-stu-id="78ea4-103">Microsoft Windows applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="78ea4-104">Windows Presentation Foundation （WPF）为配置、标识和使用这些类型的数据文件（称为应用程序数据文件）提供特殊支持。</span><span class="sxs-lookup"><span data-stu-id="78ea4-104">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="78ea4-105">이러한 지원에는 다음을 포함한 특정 애플리케이션 데이터 파일 형식 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="78ea4-106">**资源文件**：编译为可执行文件或库 WPF 程序集的数据文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-106">**Resource Files**: Data files that are compiled into either an executable or library WPF assembly.</span></span>  
  
- <span data-ttu-id="78ea4-107">**内容文件**：独立的数据文件，与可执行的 WPF 程序集具有显式关联。</span><span class="sxs-lookup"><span data-stu-id="78ea4-107">**Content Files**: Standalone data files that have an explicit association with an executable WPF assembly.</span></span>  
  
- <span data-ttu-id="78ea4-108">**源站点文件**：与可执行 WPF 程序集没有关联的独立数据文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-108">**Site of Origin Files**: Standalone data files that have no association with an executable WPF assembly.</span></span>  
  
 <span data-ttu-id="78ea4-109">이 세 가지 파일 형식을 구분하는 한 가지 중요한 차이점은 리소스 파일과 콘텐츠 파일은 빌드할 때 인식된다는 점입니다. 어셈블리는 명시적으로 이 파일을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="78ea4-110">但对于源站点文件，程序集可能根本不知道它们，或者通过包统一资源标识符（URI）引用隐式了解;对于后一种情况，不能保证引用的源站点文件确实存在。</span><span class="sxs-lookup"><span data-stu-id="78ea4-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="78ea4-111">若要引用应用程序数据文件，Windows Presentation Foundation （WPF）使用包统一资源标识符（URI）方案，详见 WPF 中的[Pack uri](pack-uris-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="78ea4-111">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="78ea4-112">이 항목에서는 애플리케이션 데이터 파일을 구성하고 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-112">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a><span data-ttu-id="78ea4-113">리소스 파일</span><span class="sxs-lookup"><span data-stu-id="78ea4-113">Resource Files</span></span>  
 <span data-ttu-id="78ea4-114">애플리케이션에서 애플리케이션 데이터 파일을 항상 사용할 수 있어야 하는 경우 가용성을 보장하는 유일한 방법은 데이터 파일을 애플리케이션의 주 실행 어셈블리 또는 참조되는 어셈블리 중 하나로 컴파일하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="78ea4-115">这种类型的应用程序数据文件称为*资源文件*。</span><span class="sxs-lookup"><span data-stu-id="78ea4-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="78ea4-116">다음과 같은 경우에 리소스 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-116">You should use resource files when:</span></span>  
  
- <span data-ttu-id="78ea4-117">어셈블리로 컴파일한 뒤에는 리소스 파일의 콘텐츠를 업데이트할 필요가 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="78ea4-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="78ea4-118">파일 종속성의 수를 줄여 애플리케이션 배포의 복잡성을 줄이려는 경우.</span><span class="sxs-lookup"><span data-stu-id="78ea4-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="78ea4-119">应用程序数据文件需要可本地化（请参阅[WPF 全球化和本地化概述](../advanced/wpf-globalization-and-localization-overview.md)）。</span><span class="sxs-lookup"><span data-stu-id="78ea4-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78ea4-120">本节中所述的资源文件不同于[XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)中所述的资源文件，与[管理应用程序资源（.net）](/visualstudio/ide/managing-application-resources-dotnet)中所述的嵌入或链接的资源不同。</span><span class="sxs-lookup"><span data-stu-id="78ea4-120">The resource files described in this section are different than the resource files described in [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="78ea4-121">리소스 파일 구성</span><span class="sxs-lookup"><span data-stu-id="78ea4-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="78ea4-122">在 WPF 中，资源文件是作为 `Resource` 项包含在 Microsoft 生成引擎（MSBuild）项目中的文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-122">In WPF, a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
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
> <span data-ttu-id="78ea4-123">在 Visual Studio 中，可以通过将文件添加到项目并将其 `Build Action` 设置为 `Resource`来创建资源文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-123">In Visual Studio, you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="78ea4-124">生成项目时，MSBuild 会将资源编译到程序集中。</span><span class="sxs-lookup"><span data-stu-id="78ea4-124">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="78ea4-125">리소스 파일 사용</span><span class="sxs-lookup"><span data-stu-id="78ea4-125">Using Resource Files</span></span>  
 <span data-ttu-id="78ea4-126">若要加载资源文件，可以调用 <xref:System.Windows.Application> 类的 <xref:System.Windows.Application.GetResourceStream%2A> 方法，同时传递标识所需资源文件的包 URI。</span><span class="sxs-lookup"><span data-stu-id="78ea4-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="78ea4-127"><xref:System.Windows.Application.GetResourceStream%2A> 返回一个 <xref:System.Windows.Resources.StreamResourceInfo> 对象，该对象将资源文件公开为 <xref:System.IO.Stream> 并描述其内容类型。</span><span class="sxs-lookup"><span data-stu-id="78ea4-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="78ea4-128">例如，下面的代码演示如何使用 <xref:System.Windows.Application.GetResourceStream%2A> 加载 <xref:System.Windows.Controls.Page> 资源文件并将其设置为 <xref:System.Windows.Controls.Frame> （`pageFrame`）的内容：</span><span class="sxs-lookup"><span data-stu-id="78ea4-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="78ea4-129">当调用 <xref:System.Windows.Application.GetResourceStream%2A> 使你能够访问 <xref:System.IO.Stream>时，需要执行其他工作，将其转换为你要将其设置到的属性的类型。</span><span class="sxs-lookup"><span data-stu-id="78ea4-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="78ea4-130">相反，你可以让 WPF 通过使用代码将资源文件直接加载到类型的属性中来处理 <xref:System.IO.Stream> 的打开和转换。</span><span class="sxs-lookup"><span data-stu-id="78ea4-130">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="78ea4-131">下面的示例演示如何使用代码将 <xref:System.Windows.Controls.Page> 直接加载到 <xref:System.Windows.Controls.Frame> （`pageFrame`）。</span><span class="sxs-lookup"><span data-stu-id="78ea4-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="78ea4-132">다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="78ea4-133">리소스 파일로 사용되는 애플리케이션 코드 파일</span><span class="sxs-lookup"><span data-stu-id="78ea4-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="78ea4-134">使用包 Uri 可以引用一组特殊的 WPF 应用程序代码文件，包括 windows、页面、流文档和资源字典。</span><span class="sxs-lookup"><span data-stu-id="78ea4-134">A special set of WPF application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="78ea4-135">例如，你可以使用一个包 URI 设置 <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> 属性，该 URL 引用在应用程序启动时要加载的窗口或页面。</span><span class="sxs-lookup"><span data-stu-id="78ea4-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="78ea4-136">当将 XAML 文件作为 `Page` 项包含在 MSBuild 项目中时，可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="78ea4-136">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
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
> <span data-ttu-id="78ea4-137">在 Visual Studio 中，向项目添加新的 <xref:System.Windows.Window>、<xref:System.Windows.Navigation.NavigationWindow>、<xref:System.Windows.Controls.Page>、<xref:System.Windows.Documents.FlowDocument>或 <xref:System.Windows.ResourceDictionary> 时，标记文件的 `Build Action` 默认为 `Page`。</span><span class="sxs-lookup"><span data-stu-id="78ea4-137">In Visual Studio, you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="78ea4-138">在编译具有 `Page` 项的项目时，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 项将转换为二进制格式，并编译到关联的程序集中。</span><span class="sxs-lookup"><span data-stu-id="78ea4-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="78ea4-139">결과적으로 이 파일을 일반적인 리소스 파일과 같은 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78ea4-140">如果 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件配置为 `Resource` 项，但没有代码隐藏文件，则原始 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 会编译为程序集，而不是原始 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的二进制版本。</span><span class="sxs-lookup"><span data-stu-id="78ea4-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a><span data-ttu-id="78ea4-141">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="78ea4-141">Content Files</span></span>  
 <span data-ttu-id="78ea4-142">*内容文件*与可执行程序集一起分发为松散文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="78ea4-143">어셈블리로 컴파일되지는 않지만 어셈블리는 각 콘텐츠 파일과 연결되는 메타데이터와 함께 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="78ea4-144">데이터 파일을 사용하는 어셈블리를 재컴파일하지 않고 업데이트하고자 하는 애플리케이션 데이터 파일을 애플리케이션에서 필요로 할 때는 콘텐츠 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="78ea4-145">콘텐츠 파일 구성</span><span class="sxs-lookup"><span data-stu-id="78ea4-145">Configuring Content Files</span></span>  
 <span data-ttu-id="78ea4-146">若要将内容文件添加到项目中，应用程序数据文件必须作为 `Content` 项包含在内。</span><span class="sxs-lookup"><span data-stu-id="78ea4-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="78ea4-147">此外，由于不会将内容文件直接编译到程序集中，因此需要设置 MSBuild `CopyToOutputDirectory` metadata 元素，以指定将内容文件复制到相对于生成的程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="78ea4-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="78ea4-148">如果希望在每次生成项目时将资源复制到生成输出文件夹，请使用 `Always` 值设置 `CopyToOutputDirectory` 元数据元素。</span><span class="sxs-lookup"><span data-stu-id="78ea4-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="78ea4-149">否则，你可以通过使用 `PreserveNewest` 值来确保只将最新版本的资源复制到生成输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="78ea4-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="78ea4-150">다음 예제에서는 리소스의 새 버전이 프로젝트에 추가된 경우에만 콘텐츠 파일이 빌드 출력 폴더에 복사되는 방식으로 구성된 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
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
> <span data-ttu-id="78ea4-151">在 Visual Studio 中，你可以通过将文件添加到项目并将其 `Build Action` 设置为 `Content`来创建内容文件，并将其 `Copy to Output Directory` 设置为 `Copy always` （与 `Always`相同）和 `Copy if newer` （与 `PreserveNewest`相同）。</span><span class="sxs-lookup"><span data-stu-id="78ea4-151">In Visual Studio, you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="78ea4-152">生成项目时，会将 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性编译到每个内容文件的程序集的元数据中。</span><span class="sxs-lookup"><span data-stu-id="78ea4-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="78ea4-153"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 的值表示内容文件相对于其在项目中的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="78ea4-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="78ea4-154">例如，如果内容文件位于项目子文件夹中，则其他路径信息将合并到 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 值中。</span><span class="sxs-lookup"><span data-stu-id="78ea4-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="78ea4-155"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 值也是内容文件在生成输出文件夹中的路径的值。</span><span class="sxs-lookup"><span data-stu-id="78ea4-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="78ea4-156">콘텐츠 파일 사용</span><span class="sxs-lookup"><span data-stu-id="78ea4-156">Using Content Files</span></span>  
 <span data-ttu-id="78ea4-157">若要加载内容文件，可以调用 <xref:System.Windows.Application> 类的 <xref:System.Windows.Application.GetContentStream%2A> 方法，同时传递标识所需内容文件的包 URI。</span><span class="sxs-lookup"><span data-stu-id="78ea4-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="78ea4-158"><xref:System.Windows.Application.GetContentStream%2A> 返回一个 <xref:System.Windows.Resources.StreamResourceInfo> 对象，该对象将内容文件作为 <xref:System.IO.Stream> 公开，并描述其内容类型。</span><span class="sxs-lookup"><span data-stu-id="78ea4-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="78ea4-159">例如，下面的代码演示如何使用 <xref:System.Windows.Application.GetContentStream%2A> 加载 <xref:System.Windows.Controls.Page> 的内容文件，并将其设置为 <xref:System.Windows.Controls.Frame> （`pageFrame`）的内容。</span><span class="sxs-lookup"><span data-stu-id="78ea4-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="78ea4-160">当调用 <xref:System.Windows.Application.GetContentStream%2A> 使你能够访问 <xref:System.IO.Stream>时，需要执行其他工作，将其转换为你要将其设置到的属性的类型。</span><span class="sxs-lookup"><span data-stu-id="78ea4-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="78ea4-161">相反，你可以让 WPF 通过使用代码将资源文件直接加载到类型的属性中来处理 <xref:System.IO.Stream> 的打开和转换。</span><span class="sxs-lookup"><span data-stu-id="78ea4-161">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="78ea4-162">下面的示例演示如何使用代码将 <xref:System.Windows.Controls.Page> 直接加载到 <xref:System.Windows.Controls.Frame> （`pageFrame`）。</span><span class="sxs-lookup"><span data-stu-id="78ea4-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="78ea4-163">다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a><span data-ttu-id="78ea4-164">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="78ea4-164">Site of Origin Files</span></span>  
 <span data-ttu-id="78ea4-165">资源文件与一起分发的程序集具有显式关系，如 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>所定义。</span><span class="sxs-lookup"><span data-stu-id="78ea4-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="78ea4-166">하지만 다음과 같이 어셈블리와 애플리케이션 데이터 파일 사이에 암시적 관계 또는 존재하지 않는 관계를 설정해야 할 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="78ea4-167">文件在编译时不存在。</span><span class="sxs-lookup"><span data-stu-id="78ea4-167">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="78ea4-168">런타임까지 어셈블리에 필요한 파일을 모르는 경우.</span><span class="sxs-lookup"><span data-stu-id="78ea4-168">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="78ea4-169">연결된 어셈블리를 재컴파일하지 않고 파일을 업데이트할 수 있어야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="78ea4-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="78ea4-170">애플리케이션에서 오디오나 비디오와 같은 대용량 데이터 파일을 사용하며 사용자가 필요할 때에만 이를 다운로드하도록 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="78ea4-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="78ea4-171">可以通过使用传统的 URI 方案（例如 file:///和 http://方案）加载这些类型的文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-171">It is possible to load these types of files by using traditional URI schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="78ea4-172">하지만 file:/// 및 http:// 스키마를 사용하려면 애플리케이션이 완전히 신뢰되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="78ea4-173">如果你的应用程序是从 Internet 或 intranet 启动的 XAML 浏览器应用程序（XBAP），并且该应用程序只请求从这些位置启动的应用程序允许的权限集，则松散文件只能从应用程序的源站点（启动位置）。</span><span class="sxs-lookup"><span data-stu-id="78ea4-173">If your application is a XAML browser application (XBAP) that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="78ea4-174">此类文件称为*源站点*文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="78ea4-175">원본 사이트 파일이 부분 신뢰 애플리케이션에서만 사용되는 것은 아니지만 부분 신뢰 애플리케이션에서는 원본 사이트 파일만을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="78ea4-176">완전 신뢰 애플리케이션의 경우에서도 빌드할 때 인식하지 못한 애플리케이션 데이터 파일을 로드해야 할 경우가 있습니다. 완전 신뢰 애플리케이션은 file:///을 사용할 수 있지만 이 경우 애플리케이션 데이터 파일이 애플리케이션 어셈블리와 같은 폴더 또는 하위 폴더에 설치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="78ea4-177">file:///에는 파일의 전체 경로를 사용해야 하기 때문에 file:///을 사용하는 방법보다 원본 사이트 참조를 사용하는 방법이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78ea4-178">源站点文件不与客户端计算机上的 XAML 浏览器应用程序（XBAP）缓存，而内容文件为。</span><span class="sxs-lookup"><span data-stu-id="78ea4-178">Site of origin files are not cached with an XAML browser application (XBAP) on a client machine, while content files are.</span></span> <span data-ttu-id="78ea4-179">따라서 구체적으로 요청된 경우에만 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="78ea4-180">如果 XAML 浏览器应用程序（XBAP）应用程序包含大型媒体文件，则将其配置为源站点文件意味着初始应用程序的启动速度要快得多，并且仅按需下载这些文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-180">If an XAML browser application (XBAP) application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="78ea4-181">원본 사이트 파일 구성</span><span class="sxs-lookup"><span data-stu-id="78ea4-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="78ea4-182">如果源站点文件在编译时不存在或未知，则需要使用传统的部署机制来确保在运行时可以使用所需的文件，包括使用 `XCopy` 命令行程序或 Microsoft Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="78ea4-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the Microsoft Windows Installer.</span></span>  
  
 <span data-ttu-id="78ea4-183">如果你在编译时知道想要位于源站点的文件，但仍希望避免显式依赖项，则可以将这些文件作为 `None` 项添加到 MSBuild 项目。</span><span class="sxs-lookup"><span data-stu-id="78ea4-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="78ea4-184">与内容文件一样，需要设置 MSBuild `CopyToOutputDirectory` 特性，以指定将源站点文件复制到相对于生成的程序集的位置，方法是指定 `Always` 值或 `PreserveNewest` 值。</span><span class="sxs-lookup"><span data-stu-id="78ea4-184">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
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
> <span data-ttu-id="78ea4-185">在 Visual Studio 中，你可以通过将文件添加到项目并将其 `Build Action` 设置为 `None`来创建源站点文件。</span><span class="sxs-lookup"><span data-stu-id="78ea4-185">In Visual Studio, you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="78ea4-186">生成项目时，MSBuild 会将指定的文件复制到生成输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="78ea4-186">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="78ea4-187">원본 사이트 파일 사용</span><span class="sxs-lookup"><span data-stu-id="78ea4-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="78ea4-188">若要加载源站点文件，可以调用 <xref:System.Windows.Application> 类的 <xref:System.Windows.Application.GetRemoteStream%2A> 方法，同时传递标识所需的源站点文件的包 URI。</span><span class="sxs-lookup"><span data-stu-id="78ea4-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="78ea4-189"><xref:System.Windows.Application.GetRemoteStream%2A> 返回一个 <xref:System.Windows.Resources.StreamResourceInfo> 对象，该对象将源站点文件作为 <xref:System.IO.Stream> 公开，并描述其内容类型。</span><span class="sxs-lookup"><span data-stu-id="78ea4-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="78ea4-190">例如，下面的代码演示如何使用 <xref:System.Windows.Application.GetRemoteStream%2A> 加载 <xref:System.Windows.Controls.Page> 的源站点文件，并将其设置为 <xref:System.Windows.Controls.Frame> （`pageFrame`）的内容。</span><span class="sxs-lookup"><span data-stu-id="78ea4-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="78ea4-191">当调用 <xref:System.Windows.Application.GetRemoteStream%2A> 使你能够访问 <xref:System.IO.Stream>时，需要执行其他工作，将其转换为你要将其设置到的属性的类型。</span><span class="sxs-lookup"><span data-stu-id="78ea4-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="78ea4-192">相反，你可以让 WPF 通过使用代码将资源文件直接加载到类型的属性中来处理 <xref:System.IO.Stream> 的打开和转换。</span><span class="sxs-lookup"><span data-stu-id="78ea4-192">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="78ea4-193">下面的示例演示如何使用代码将 <xref:System.Windows.Controls.Page> 直接加载到 <xref:System.Windows.Controls.Frame> （`pageFrame`）。</span><span class="sxs-lookup"><span data-stu-id="78ea4-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="78ea4-194">다음 예제는 태그를 사용하여 앞의 예제를 구현한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="78ea4-195">빌드 형식 변경 후 다시 빌드</span><span class="sxs-lookup"><span data-stu-id="78ea4-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="78ea4-196">애플리케이션 데이터 파일의 빌드 형식을 변경한 뒤에는 변경 내용이 적용되도록 전체 애플리케이션을 다시 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="78ea4-197">애플리케이션만 빌드하면 변경 내용이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78ea4-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ea4-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78ea4-198">See also</span></span>

- [<span data-ttu-id="78ea4-199">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="78ea4-199">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
