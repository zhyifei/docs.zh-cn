---
title: 包 Uri
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: 0fec72bdedbcc2c84d8bc65e72391366e42d82be
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739158"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="c3002-102">WPF의 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-102">Pack URIs in WPF</span></span>

<span data-ttu-id="c3002-103">在 Windows Presentation Foundation （WPF）中，统一资源标识符（Uri）用于通过多种方式标识和加载文件，其中包括：</span><span class="sxs-lookup"><span data-stu-id="c3002-103">In Windows Presentation Foundation (WPF), uniform resource identifiers (URIs) are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="c3002-104">指定在应用程序首次启动时要显示的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c3002-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="c3002-105">이미지 로드</span><span class="sxs-lookup"><span data-stu-id="c3002-105">Loading images.</span></span>

- <span data-ttu-id="c3002-106">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="c3002-106">Navigating to pages.</span></span>

- <span data-ttu-id="c3002-107">비실행 데이터 파일 로드</span><span class="sxs-lookup"><span data-stu-id="c3002-107">Loading non-executable data files.</span></span>

<span data-ttu-id="c3002-108">此外，可以使用 Uri 来标识和加载来自各种位置的文件，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="c3002-108">Furthermore, URIs can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="c3002-109">현재 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-109">The current assembly.</span></span>

- <span data-ttu-id="c3002-110">참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-110">A referenced assembly.</span></span>

- <span data-ttu-id="c3002-111">어셈블리에 상대적인 위치</span><span class="sxs-lookup"><span data-stu-id="c3002-111">A location relative to an assembly.</span></span>

- <span data-ttu-id="c3002-112">애플리케이션의 원본 사이트</span><span class="sxs-lookup"><span data-stu-id="c3002-112">The application's site of origin.</span></span>

<span data-ttu-id="c3002-113">为了提供用于从这些位置标识和加载这些类型的文件的一致机制，WPF 利用了*PACK URI 方案*的扩展性。</span><span class="sxs-lookup"><span data-stu-id="c3002-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, WPF leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="c3002-114">本主题概述了方案，并介绍了如何为各种方案构造包 Uri，以及如何在显示如何使用标记和代码中的 pack Uri 之前介绍绝对和相对 Uri 以及 URI 解析。</span><span class="sxs-lookup"><span data-stu-id="c3002-114">This topic provides an overview of the scheme, covers how to construct pack URIs for a variety of scenarios, discusses absolute and relative URIs and URI resolution, before showing how to use pack URIs from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="c3002-115">Pack URI 체계</span><span class="sxs-lookup"><span data-stu-id="c3002-115">The Pack URI Scheme</span></span>

<span data-ttu-id="c3002-116">Pack URI 方案由[开放式打包约定](https://go.microsoft.com/fwlink/?LinkID=71255)（OPC）规范使用，此规范描述了用于组织和标识内容的模型。</span><span class="sxs-lookup"><span data-stu-id="c3002-116">The pack URI scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="c3002-117">此模型的关键元素是包和部件，其中，*包*是一个或多个逻辑*部分*的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="c3002-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="c3002-118">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-118">The following figure illustrates this concept.</span></span>

![패키지 및 파트 다이어그램](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="c3002-120">为了识别部件，OPC 规范利用了 RFC 2396 （统一资源标识符（URI）：通用语法）的扩展性来定义 pack URI 方案。</span><span class="sxs-lookup"><span data-stu-id="c3002-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack URI scheme.</span></span>

<span data-ttu-id="c3002-121">由 URI 指定的方案由其前缀定义;http、ftp 和 file 是众所周知的示例。</span><span class="sxs-lookup"><span data-stu-id="c3002-121">The scheme that is specified by a URI is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="c3002-122">Pack URI 方案使用 "pack" 作为其方案，并且包含两个组件：颁发机构和路径。</span><span class="sxs-lookup"><span data-stu-id="c3002-122">The pack URI scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="c3002-123">下面是 pack URI 的格式。</span><span class="sxs-lookup"><span data-stu-id="c3002-123">The following is the format for a pack URI.</span></span>

<span data-ttu-id="c3002-124">pack://*机构*/*路径*</span><span class="sxs-lookup"><span data-stu-id="c3002-124">pack://*authority*/*path*</span></span>

<span data-ttu-id="c3002-125">*颁发机构*指定包含部件的包类型，而*路径*指定部件在包中的位置。</span><span class="sxs-lookup"><span data-stu-id="c3002-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="c3002-126">다음 그림에서는 이 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-126">This concept is illustrated by the following figure:</span></span>

![패키지, 권한 및 경로의 관계](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="c3002-128">패키지와 파트는 애플리케이션 및 파일과 유사합니다. 즉, 애플리케이션(패키지)은 다음을 비롯한 하나 이상의 파일(파트)을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="c3002-129">로컬 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-129">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="c3002-130">참조된 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-130">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="c3002-131">참조하는 어셈블리로 컴파일되는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-131">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="c3002-132">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-132">Content files.</span></span>

- <span data-ttu-id="c3002-133">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-133">Site of origin files.</span></span>

<span data-ttu-id="c3002-134">为了访问这些类型的文件，WPF 支持两个权限： application:///和 siteoforigin:///。</span><span class="sxs-lookup"><span data-stu-id="c3002-134">To access these types of files, WPF supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="c3002-135">application:/// 인증 기관은 리소스 및 콘텐츠 파일을 비롯하여 컴파일 시 알려진 애플리케이션 데이터 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="c3002-136">siteoforigin:/// 인증 기관은 원본 사이트 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="c3002-137">다음 그림에서는 각 인증 기관의 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-137">The scope of each authority is shown in the following figure.</span></span>

![Pack URI 다이어그램](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="c3002-139">包 URI 的颁发机构组件是一个指向包并必须符合 RFC 2396 的嵌入 URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-139">The authority component of a pack URI is an embedded URI that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="c3002-140">또한 “/” 문자를 “,” 문자로 바꾸고 “%” 및 “?” 같은 예약 문자는 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="c3002-141">자세한 내용은 OPC를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3002-141">See the OPC for details.</span></span>

<span data-ttu-id="c3002-142">以下各节说明如何使用这两个颁发机构构造包 Uri 以及用于标识资源、内容和源站点文件的相应路径。</span><span class="sxs-lookup"><span data-stu-id="c3002-142">The following sections explain how to construct pack URIs using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="c3002-143">리소스 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-143">Resource File Pack URIs</span></span>

<span data-ttu-id="c3002-144">资源文件配置为 MSBuild `Resource` 项，并编译到程序集中。</span><span class="sxs-lookup"><span data-stu-id="c3002-144">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="c3002-145">WPF 支持构造包 Uri，这些 Uri 可用于标识编译到本地程序集中或编译到从本地程序集引用的程序集中的资源文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-145">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="c3002-146">로컬 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-146">Local Assembly Resource File</span></span>

<span data-ttu-id="c3002-147">编译到本地程序集的资源文件的 pack URI 使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="c3002-147">The pack URI for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="c3002-148">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="c3002-148">**Authority**: application:///.</span></span>

- <span data-ttu-id="c3002-149">**경로**: 로컬 어셈블리 프로젝트 폴더 루트에 상대적인 경로를 포함한 리소스 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="c3002-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="c3002-150">下面的示例演示位于本地程序集的项目文件夹的根目录中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-150">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="c3002-151">下面的示例演示位于本地程序集的项目文件夹的子文件夹中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-151">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="c3002-152">참조된 어셈블리 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-152">Referenced Assembly Resource File</span></span>

<span data-ttu-id="c3002-153">编译到引用的程序集中的资源文件的 pack URI 使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="c3002-153">The pack URI for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="c3002-154">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="c3002-154">**Authority**: application:///.</span></span>

- <span data-ttu-id="c3002-155">**경로**: 참조된 어셈블리로 컴파일되는 리소스 파일의 이름.</span><span class="sxs-lookup"><span data-stu-id="c3002-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="c3002-156">경로는 다음 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-156">The path must conform to the following format:</span></span>

  <span data-ttu-id="c3002-157">*AssemblyShortName*{ *;版本*] { *;PublicKey*]; 组件/*路径*</span><span class="sxs-lookup"><span data-stu-id="c3002-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="c3002-158">**AssemblyShortName**: 참조된 어셈블리에 대한 약식 이름</span><span class="sxs-lookup"><span data-stu-id="c3002-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="c3002-159">**;Version**[옵션]: 리소스 파일을 포함하는 참조된 어셈블리의 버전.</span><span class="sxs-lookup"><span data-stu-id="c3002-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="c3002-160">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="c3002-161">**;PublicKey**[옵션]: 참조된 어셈블리를 서명하는 데 사용된 공개 키.</span><span class="sxs-lookup"><span data-stu-id="c3002-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="c3002-162">동일한 약식 이름을 갖는 두 개 이상의 참조된 어셈블리가 로드된 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="c3002-163">**;component**: 참조되는 어셈블리가 로컬 어셈블리에서 참조된다는 것을 지정</span><span class="sxs-lookup"><span data-stu-id="c3002-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="c3002-164">**/Path**: 참조된 어셈블리 프로젝트 폴더의 루트에 상대적인 경로를 포함한 리소스 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="c3002-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="c3002-165">下面的示例显示了位于所引用程序集的项目文件夹的根目录中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-165">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="c3002-166">下面的示例显示了位于所引用程序集的项目文件夹的子文件夹中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-166">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="c3002-167">下面的示例演示一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 资源文件的 pack URI，该文件位于所引用的特定于版本的程序集的项目文件夹的根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c3002-167">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="c3002-168">请注意，所引用的程序集资源文件的 pack URI 语法只能与 application:///机构一起使用。</span><span class="sxs-lookup"><span data-stu-id="c3002-168">Note that the pack URI syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="c3002-169">例如，WPF 不支持以下。</span><span class="sxs-lookup"><span data-stu-id="c3002-169">For example, the following is not supported in WPF.</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="c3002-170">콘텐츠 파일 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-170">Content File Pack URIs</span></span>

<span data-ttu-id="c3002-171">内容文件的 pack URI 使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="c3002-171">The pack URI for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="c3002-172">**인증 기관**: application:///</span><span class="sxs-lookup"><span data-stu-id="c3002-172">**Authority**: application:///.</span></span>

- <span data-ttu-id="c3002-173">**경로**: 애플리케이션의 주 실행 가능 어셈블리의 파일 시스템 위치에 상대적인 경로를 포함한 콘텐츠 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="c3002-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="c3002-174">下面的示例演示与可执行程序集位于同一文件夹中的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 内容文件的 pack URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-174">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="c3002-175">下面的示例演示一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 内容文件的 pack URI，该 URI 位于相对于应用程序的可执行程序集的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c3002-175">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="c3002-176">不能导航到 HTML 内容文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-176">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="c3002-177">URI 方案仅支持导航到位于源站点的 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-177">The URI scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="c3002-178">원본 사이트 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-178">Site of Origin Pack URIs</span></span>

<span data-ttu-id="c3002-179">源站点文件的 pack URI 使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="c3002-179">The pack URI for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="c3002-180">**인증 기관**: siteoforigin:///</span><span class="sxs-lookup"><span data-stu-id="c3002-180">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="c3002-181">**경로**: 실행 가능 어셈블리가 시작된 위치에 상대적인 경로를 포함한 원본 사이트 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="c3002-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="c3002-182">下面的示例显示了一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 源站点文件的 pack URI，该 URI 存储在从中启动可执行程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="c3002-182">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="c3002-183">下面的示例显示了一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 源站点文件的 pack URI，该 URI 存储在相对于应用程序可执行程序集的启动位置的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c3002-183">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="c3002-184">페이지 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-184">Page Files</span></span>

<span data-ttu-id="c3002-185">配置为 MSBuild `Page` 项的 XAML 文件将以与资源文件相同的方式编译到程序集中。</span><span class="sxs-lookup"><span data-stu-id="c3002-185">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="c3002-186">因此，可以使用资源文件的 pack Uri 来标识 MSBuild `Page` 项。</span><span class="sxs-lookup"><span data-stu-id="c3002-186">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="c3002-187">通常配置为 MSBuild`Page` 项的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件的类型具有以下项之一作为其根元素：</span><span class="sxs-lookup"><span data-stu-id="c3002-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="c3002-188">绝对和相对 Pack Uri</span><span class="sxs-lookup"><span data-stu-id="c3002-188">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="c3002-189">完全限定的 pack URI 包含方案、颁发机构和路径，并被视为绝对包 URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-189">A fully qualified pack URI includes the scheme, the authority, and the path, and it is considered an absolute pack URI.</span></span> <span data-ttu-id="c3002-190">作为开发人员的简化，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 元素通常允许使用相对 pack URI 设置相应的属性，其中只包含路径。</span><span class="sxs-lookup"><span data-stu-id="c3002-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack URI, which includes only the path.</span></span>

<span data-ttu-id="c3002-191">例如，请考虑本地程序集中某个资源文件的以下绝对包 URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-191">For example, consider the following absolute pack URI for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="c3002-192">引用此资源文件的相对 pack URI 如下所示。</span><span class="sxs-lookup"><span data-stu-id="c3002-192">The relative pack URI that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="c3002-193">由于源站点文件不与程序集相关联，因此只能用绝对包 Uri 来引用它们。</span><span class="sxs-lookup"><span data-stu-id="c3002-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack URIs.</span></span>

<span data-ttu-id="c3002-194">默认情况下，相对 pack URI 被视为相对于包含引用的标记或代码的位置。</span><span class="sxs-lookup"><span data-stu-id="c3002-194">By default, a relative pack URI is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="c3002-195">但是，如果使用前导反斜杠，则相对 pack URI 引用将被视为相对于应用程序的根。</span><span class="sxs-lookup"><span data-stu-id="c3002-195">If a leading backslash is used, however, the relative pack URI reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="c3002-196">예를 들어 다음과 같은 프로젝트 구조를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-196">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="c3002-197">如果 Page1 包含引用*根*\SUBFOLDER\PAGE2.XAML 的 URI，则引用可以使用以下相对 pack URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-197">If Page1.xaml contains a URI that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`Page2.xaml`

<span data-ttu-id="c3002-198">如果 Page1 包含引用*根*\PAGE2.XAML 的 URI，则引用可以使用以下相对 pack URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-198">If Page1.xaml contains a URI that references *Root*\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="c3002-199">Pack URI 확인</span><span class="sxs-lookup"><span data-stu-id="c3002-199">Pack URI Resolution</span></span>

<span data-ttu-id="c3002-200">Pack Uri 的格式使得不同类型的文件的包 Uri 能够看起来相同。</span><span class="sxs-lookup"><span data-stu-id="c3002-200">The format of pack URIs makes it possible for pack URIs for different types of files to look the same.</span></span> <span data-ttu-id="c3002-201">例如，请考虑下面的绝对包 URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-201">For example, consider the following absolute pack URI.</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="c3002-202">此绝对包 URI 可以引用本地程序集或内容文件中的资源文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-202">This absolute pack URI could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="c3002-203">对于以下相对 URI 也是如此。</span><span class="sxs-lookup"><span data-stu-id="c3002-203">The same is true for the following relative URI.</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="c3002-204">为了确定 pack URI 引用的文件类型，WPF 使用以下试探法解析本地程序集中的资源文件和内容文件的 Uri：</span><span class="sxs-lookup"><span data-stu-id="c3002-204">In order to determine the type of file that a pack URI refers to, WPF resolves URIs for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="c3002-205">探测与 pack URI 匹配的 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性的程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="c3002-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack URI.</span></span>

2. <span data-ttu-id="c3002-206">如果找到 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 属性，包 URI 的路径将引用一个内容文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack URI refers to a content file.</span></span>

3. <span data-ttu-id="c3002-207">如果找不到 <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> 特性，请探测编译到本地程序集的资源文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="c3002-208">如果找到与包 URI 的路径匹配的资源文件，则包 URI 的路径引用资源文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-208">If a resource file that matches the path of the pack URI is found, the path of the pack URI refers to a resource file.</span></span>

5. <span data-ttu-id="c3002-209">如果找不到该资源，则内部创建的 <xref:System.Uri> 无效。</span><span class="sxs-lookup"><span data-stu-id="c3002-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

<span data-ttu-id="c3002-210">URI 解析不适用于引用以下各项的 Uri：</span><span class="sxs-lookup"><span data-stu-id="c3002-210">URI resolution does not apply for URIs that refer to the following:</span></span>

- <span data-ttu-id="c3002-211">引用的程序集中的内容文件： WPF 不支持这些文件类型。</span><span class="sxs-lookup"><span data-stu-id="c3002-211">Content files in referenced assemblies: these file types are not supported by WPF.</span></span>

- <span data-ttu-id="c3002-212">引用的程序集中的嵌入文件：标识这些文件的 Uri 是唯一的，因为它们包括引用的程序集的名称和 `;component` 后缀。</span><span class="sxs-lookup"><span data-stu-id="c3002-212">Embedded files in referenced assemblies: URIs that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="c3002-213">源站点文件：标识它们的 Uri 是唯一的，因为它们是可以由包含 siteoforigin:///机构的 pack Uri 标识的唯一文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-213">Site of origin files: URIs that identify them are unique because they are the only files that can be identified by pack URIs that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="c3002-214">Pack URI 解析可以通过一种简化来使代码在一定程度上独立于资源和内容文件的位置。</span><span class="sxs-lookup"><span data-stu-id="c3002-214">One simplification that pack URI resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="c3002-215">例如，如果本地程序集中有一个资源文件，该文件已重新配置为内容文件，则该资源的 pack URI 将保持不变，这与使用包 URI 的代码一样。</span><span class="sxs-lookup"><span data-stu-id="c3002-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack URI for the resource remains the same, as does the code that uses the pack URI.</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="c3002-216">Pack URI를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c3002-216">Programming with Pack URIs</span></span>

<span data-ttu-id="c3002-217">许多 WPF 类实现可通过 pack Uri 进行设置的属性，包括：</span><span class="sxs-lookup"><span data-stu-id="c3002-217">Many WPF classes implement properties that can be set with pack URIs, including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="c3002-218">이러한 속성을 태그와 코드 모두에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="c3002-219">이 섹션에서는 두 경우에 대한 기본 구조를 설명한 다음 일반적인 시나리오 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="c3002-220">태그에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="c3002-220">Using Pack URIs in Markup</span></span>

<span data-ttu-id="c3002-221">通过使用 pack URI 设置特性的元素，在标记中指定包 URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-221">A pack URI is specified in markup by setting the element of an attribute with the pack URI.</span></span> <span data-ttu-id="c3002-222">예를 들면 다음과 같습니다.:</span><span class="sxs-lookup"><span data-stu-id="c3002-222">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="c3002-223">表1说明了可在标记中指定的各种绝对包 Uri。</span><span class="sxs-lookup"><span data-stu-id="c3002-223">Table 1 illustrates the various absolute pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="c3002-224">표 1: 태그의 절대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-224">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="c3002-225">File</span><span class="sxs-lookup"><span data-stu-id="c3002-225">File</span></span>|<span data-ttu-id="c3002-226">绝对包 URI</span><span class="sxs-lookup"><span data-stu-id="c3002-226">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="c3002-227">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-228">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-229">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-230">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-231">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-232">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="c3002-233">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="c3002-234">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="c3002-235">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="c3002-236">表2说明了可以在标记中指定的各种相对包 Uri。</span><span class="sxs-lookup"><span data-stu-id="c3002-236">Table 2 illustrates the various relative pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="c3002-237">표 2: 태그의 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-237">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="c3002-238">File</span><span class="sxs-lookup"><span data-stu-id="c3002-238">File</span></span>|<span data-ttu-id="c3002-239">相对 pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-239">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="c3002-240">로컬 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-241">로컬 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-242">참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-243">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="c3002-244">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-244">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="c3002-245">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="c3002-246">코드에서 Pack URI 사용</span><span class="sxs-lookup"><span data-stu-id="c3002-246">Using Pack URIs in Code</span></span>

<span data-ttu-id="c3002-247">通过实例化 <xref:System.Uri> 类并将包 URI 作为参数传递给构造函数，可以在代码中指定包 URI。</span><span class="sxs-lookup"><span data-stu-id="c3002-247">You specify a pack URI in code by instantiating the <xref:System.Uri> class and passing the pack URI as a parameter to the constructor.</span></span> <span data-ttu-id="c3002-248">다음 예제를 통해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-248">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="c3002-249">默认情况下，<xref:System.Uri> 类将包 Uri 视为绝对 Uri。</span><span class="sxs-lookup"><span data-stu-id="c3002-249">By default, the <xref:System.Uri> class considers pack URIs to be absolute.</span></span> <span data-ttu-id="c3002-250">因此，当使用相对 pack URI 创建 <xref:System.Uri> 类的实例时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="c3002-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack URI.</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="c3002-251">幸运的是，<xref:System.Uri> 类构造函数的 <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> 重载接受 <xref:System.UriKind> 类型的参数，以允许您指定包 URI 是绝对的还是相对的。</span><span class="sxs-lookup"><span data-stu-id="c3002-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack URI is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="c3002-252">在确定所提供的 pack URI 为 one 时，应仅指定 <xref:System.UriKind.Absolute> 或 <xref:System.UriKind.Relative>。</span><span class="sxs-lookup"><span data-stu-id="c3002-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack URI is one or the other.</span></span> <span data-ttu-id="c3002-253">如果你不知道所使用的 pack URI 的类型，例如当用户在运行时输入包 URI 时，请改用 <xref:System.UriKind.RelativeOrAbsolute>。</span><span class="sxs-lookup"><span data-stu-id="c3002-253">If you don't know the type of pack URI that is used, such as when a user enters a pack URI at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="c3002-254">表3说明了可以使用 <xref:System.Uri?displayProperty=nameWithType>在代码中指定的各种相对包 Uri。</span><span class="sxs-lookup"><span data-stu-id="c3002-254">Table 3 illustrates the various relative pack URIs that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="c3002-255">표 3: 코드의 절대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-255">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="c3002-256">File</span><span class="sxs-lookup"><span data-stu-id="c3002-256">File</span></span>|<span data-ttu-id="c3002-257">绝对包 URI</span><span class="sxs-lookup"><span data-stu-id="c3002-257">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="c3002-258">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-259">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-260">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-261">참조된 어셈블리의 하위 폴더에 있는 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-262">버전이 있는 참조된 어셈블리의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-263">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-264">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-265">원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="c3002-266">하위 폴더의 원본 사이트 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="c3002-267">表4说明了可使用 <xref:System.Uri?displayProperty=nameWithType>在代码中指定的各种相对包 Uri。</span><span class="sxs-lookup"><span data-stu-id="c3002-267">Table 4 illustrates the various relative pack URIs that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="c3002-268">표 4: 코드의 상대 Pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-268">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="c3002-269">File</span><span class="sxs-lookup"><span data-stu-id="c3002-269">File</span></span>|<span data-ttu-id="c3002-270">相对 pack URI</span><span class="sxs-lookup"><span data-stu-id="c3002-270">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="c3002-271">리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="c3002-272">하위 폴더의 리소스 파일 - 로컬 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="c3002-273">리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="c3002-274">하위 폴더의 리소스 파일 - 참조된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c3002-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="c3002-275">콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="c3002-276">하위 폴더의 콘텐츠 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="c3002-277">일반적인 Pack URI 시나리오</span><span class="sxs-lookup"><span data-stu-id="c3002-277">Common Pack URI Scenarios</span></span>

<span data-ttu-id="c3002-278">前面几节讨论了如何构造包 Uri 来标识资源、内容和源站点文件。</span><span class="sxs-lookup"><span data-stu-id="c3002-278">The preceding sections have discussed how to construct pack URIs to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="c3002-279">在 WPF 中，可以通过多种方式使用这些构造，以下部分介绍了几种常见的用法。</span><span class="sxs-lookup"><span data-stu-id="c3002-279">In WPF, these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="c3002-280">애플리케이션을 시작할 때 표시되는 UI 지정</span><span class="sxs-lookup"><span data-stu-id="c3002-280">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="c3002-281"><xref:System.Windows.Application.StartupUri%2A> 指定在启动 WPF 应用程序时要显示的第一个 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c3002-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a WPF application is launched.</span></span> <span data-ttu-id="c3002-282">对于独立应用程序，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 可以是窗口，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c3002-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="c3002-283">独立应用程序和 XAML 浏览器应用程序（Xbap）还可以将页指定为初始 UI，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c3002-283">Standalone applications and XAML browser applications (XBAPs) can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="c3002-284">如果应用程序是独立的应用程序，并且使用 <xref:System.Windows.Application.StartupUri%2A>指定了页面，则 WPF 将打开一个 <xref:System.Windows.Navigation.NavigationWindow> 来承载页面。</span><span class="sxs-lookup"><span data-stu-id="c3002-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, WPF opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="c3002-285">对于 Xbap，将在主机浏览器中显示页面。</span><span class="sxs-lookup"><span data-stu-id="c3002-285">For XBAPs, the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="c3002-286">페이지 탐색</span><span class="sxs-lookup"><span data-stu-id="c3002-286">Navigating to a Page</span></span>

<span data-ttu-id="c3002-287">다음 예제에서는 페이지를 탐색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-287">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="c3002-288">有关在 WPF 中导航的各种方式的详细信息，请参阅[导航概述](navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3002-288">For more information on the various ways to navigate in WPF, see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="c3002-289">창 아이콘 지정</span><span class="sxs-lookup"><span data-stu-id="c3002-289">Specifying a Window Icon</span></span>

<span data-ttu-id="c3002-290">다음 예제에서는 URI를 사용하여 창 아이콘을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-290">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="c3002-291">자세한 내용은 <xref:System.Windows.Window.Icon%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3002-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="c3002-292">이미지, 오디오 및 비디오 파일 로드</span><span class="sxs-lookup"><span data-stu-id="c3002-292">Loading Image, Audio, and Video Files</span></span>

<span data-ttu-id="c3002-293">WPF 允许应用程序使用各种媒体类型，所有这些类型都可以使用 pack Uri 进行标识和加载，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c3002-293">WPF allows applications to use a wide variety of media types, all of which can be identified and loaded with pack URIs, as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="c3002-294">有关使用媒体内容的详细信息，请参阅[图形和多媒体](../graphics-multimedia/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c3002-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="c3002-295">원본 사이트에서 리소스 사전 로드</span><span class="sxs-lookup"><span data-stu-id="c3002-295">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="c3002-296">资源字典（<xref:System.Windows.ResourceDictionary>）可用于支持应用程序主题。</span><span class="sxs-lookup"><span data-stu-id="c3002-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="c3002-297">테마를 만들고 관리하는 한 가지 방법은 애플리케이션의 원본 사이트에 위치한 리소스 사전으로 여러 개의 테마를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="c3002-298">이렇게 하면 애플리케이션을 다시 컴파일하여 배포할 필요 없이 테마를 추가하고 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3002-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="c3002-299">可以使用 pack Uri 来标识和加载这些资源字典，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c3002-299">These resource dictionaries can be identified and loaded using pack URIs, which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="c3002-300">有关 WPF 中的主题的概述，请参阅[样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3002-300">For an overview of themes in WPF, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3002-301">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3002-301">See also</span></span>

- [<span data-ttu-id="c3002-302">WPF 애플리케이션 리소스, 콘텐츠 및 데이터 파일</span><span class="sxs-lookup"><span data-stu-id="c3002-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
