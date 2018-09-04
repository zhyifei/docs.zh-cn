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
ms.openlocfilehash: 7addb503d0a7d4c7a4388144759e7f40264d7703
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522430"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="f0c71-102">WPF 中的 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-102">Pack URIs in WPF</span></span>
<span data-ttu-id="f0c71-103">在 Windows Presentation Foundation (WPF)[!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)]用于标识和加载在许多方面，包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="f0c71-103">In Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] are used to identify and load files in many ways, including the following:</span></span>  
  
-   <span data-ttu-id="f0c71-104">指定[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]以显示应用程序首次启动时。</span><span class="sxs-lookup"><span data-stu-id="f0c71-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>  
  
-   <span data-ttu-id="f0c71-105">加载图像。</span><span class="sxs-lookup"><span data-stu-id="f0c71-105">Loading images.</span></span>  
  
-   <span data-ttu-id="f0c71-106">导航到页。</span><span class="sxs-lookup"><span data-stu-id="f0c71-106">Navigating to pages.</span></span>  
  
-   <span data-ttu-id="f0c71-107">加载不可执行的数据文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-107">Loading non-executable data files.</span></span>  
  
 <span data-ttu-id="f0c71-108">此外，[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]可用于标识和加载不同的位置，包括以下文件：</span><span class="sxs-lookup"><span data-stu-id="f0c71-108">Furthermore, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] can be used to identify and load files from a variety of locations, including the following:</span></span>  
  
-   <span data-ttu-id="f0c71-109">当前程序集。</span><span class="sxs-lookup"><span data-stu-id="f0c71-109">The current assembly.</span></span>  
  
-   <span data-ttu-id="f0c71-110">引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="f0c71-110">A referenced assembly.</span></span>  
  
-   <span data-ttu-id="f0c71-111">相对于程序集的某个位置。</span><span class="sxs-lookup"><span data-stu-id="f0c71-111">A location relative to an assembly.</span></span>  
  
-   <span data-ttu-id="f0c71-112">应用程序的源站点。</span><span class="sxs-lookup"><span data-stu-id="f0c71-112">The application's site of origin.</span></span>  
  
 <span data-ttu-id="f0c71-113">若要标识和从这些位置加载这些类型的文件提供一致的机制[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]利用的可扩展性*pack URI 方案*。</span><span class="sxs-lookup"><span data-stu-id="f0c71-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="f0c71-114">本主题提供的方案的概述，介绍了如何构造 pack[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]的各种方案，讨论绝对和相对[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]并[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]解析，然后说明如何使用包[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]从这两个标记和代码。</span><span class="sxs-lookup"><span data-stu-id="f0c71-114">This topic provides an overview of the scheme, covers how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for a variety of scenarios, discusses absolute and relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] and [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution, before showing how to use pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] from both markup and code.</span></span>  
  
  
<a name="The_Pack_URI_Scheme"></a>   
## <a name="the-pack-uri-scheme"></a><span data-ttu-id="f0c71-115">Pack URI 方案</span><span class="sxs-lookup"><span data-stu-id="f0c71-115">The Pack URI Scheme</span></span>  
 <span data-ttu-id="f0c71-116">包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]通过使用方案[开放打包约定](https://go.microsoft.com/fwlink/?LinkID=71255)(OPC) 规范，描述用于组织和标识内容的模型。</span><span class="sxs-lookup"><span data-stu-id="f0c71-116">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="f0c71-117">此模型的关键元素是包和部件，其中*包*是逻辑容器，一个或多个逻辑*部件*。</span><span class="sxs-lookup"><span data-stu-id="f0c71-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="f0c71-118">下图阐释了此概念。</span><span class="sxs-lookup"><span data-stu-id="f0c71-118">The following figure illustrates this concept.</span></span>  
  
 <span data-ttu-id="f0c71-119">![包和部件关系图](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.PNG "WPFPackURISchemeFigure1")</span><span class="sxs-lookup"><span data-stu-id="f0c71-119">![Package and Parts diagram](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.PNG "WPFPackURISchemeFigure1")</span></span>  
  
 <span data-ttu-id="f0c71-120">为了标识部件，OPC 规范利用 RFC 2396 扩展性 (统一资源标识符 (URI): 一般语法) 来定义 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案。</span><span class="sxs-lookup"><span data-stu-id="f0c71-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme.</span></span>  
  
 <span data-ttu-id="f0c71-121">由指定的方案[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]由其前缀; 定义 http、 ftp 和 file 是众所周知的示例。</span><span class="sxs-lookup"><span data-stu-id="f0c71-121">The scheme that is specified by a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="f0c71-122">包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案作为其方案中，使用"包"，并包含两个组件： 授权和路径。</span><span class="sxs-lookup"><span data-stu-id="f0c71-122">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="f0c71-123">下面是包的格式[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-123">The following is the format for a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 <span data-ttu-id="f0c71-124">包: / /*颁发机构*/*路径*</span><span class="sxs-lookup"><span data-stu-id="f0c71-124">pack://*authority*/*path*</span></span>
  
 <span data-ttu-id="f0c71-125">*颁发机构*指定的类型，由包含部件的包时*路径*指定部件在包中的位置。</span><span class="sxs-lookup"><span data-stu-id="f0c71-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>  
  
 <span data-ttu-id="f0c71-126">下图阐释了此概念：</span><span class="sxs-lookup"><span data-stu-id="f0c71-126">This concept is illustrated by the following figure:</span></span>  
  
 <span data-ttu-id="f0c71-127">![包、授权与路径之间的关系](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.PNG "WPFPackURISchemeFigure2")</span><span class="sxs-lookup"><span data-stu-id="f0c71-127">![Relationship among package, authority, and path](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.PNG "WPFPackURISchemeFigure2")</span></span>  
  
 <span data-ttu-id="f0c71-128">包和部件之间的关系类似于应用程序和文件之间的关系，其中应用程序（包）可以包含一个或多个文件（部件），包括：</span><span class="sxs-lookup"><span data-stu-id="f0c71-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>  
  
-   <span data-ttu-id="f0c71-129">编译到本地程序集内的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-129">Resource files that are compiled into the local assembly.</span></span>  
  
-   <span data-ttu-id="f0c71-130">编译到所引用的程序集内的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-130">Resource files that are compiled into a referenced assembly.</span></span>  
  
-   <span data-ttu-id="f0c71-131">编译到引用程序集内的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-131">Resource files that are compiled into a referencing assembly.</span></span>  
  
-   <span data-ttu-id="f0c71-132">内容文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-132">Content files.</span></span>  
  
-   <span data-ttu-id="f0c71-133">源站点文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-133">Site of origin files.</span></span>  
  
 <span data-ttu-id="f0c71-134">若要访问这些类型的文件，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]支持两种授权： 应用程序: / / 和 siteoforigin:///: / /。</span><span class="sxs-lookup"><span data-stu-id="f0c71-134">To access these types of files, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="f0c71-135">application:/// 授权标识在编译时已知的应用程序数据文件，包括资源文件和内容文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="f0c71-136">siteoforigin:/// 授权标识源站点文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="f0c71-137">下图显示了每种授权的范围。</span><span class="sxs-lookup"><span data-stu-id="f0c71-137">The scope of each authority is shown in the following figure.</span></span>  
  
 <span data-ttu-id="f0c71-138">![Pack URI 关系图](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")</span><span class="sxs-lookup"><span data-stu-id="f0c71-138">![Pack URI diagram](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0c71-139">包的证书颁发机构部分[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]是一个嵌入式[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的指向包并且必须符合 RFC 2396。</span><span class="sxs-lookup"><span data-stu-id="f0c71-139">The authority component of a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is an embedded [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="f0c71-140">另外，必须用字符“,”替换字符“/”，并且必须对保留字符（如“%”和“?”）进行转义。</span><span class="sxs-lookup"><span data-stu-id="f0c71-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="f0c71-141">有关详细信息，请参阅 OPC。</span><span class="sxs-lookup"><span data-stu-id="f0c71-141">See the OPC for details.</span></span>  
  
 <span data-ttu-id="f0c71-142">以下各节说明如何构造 pack[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]与相应的路径结合使用这两种授权，用于标识资源、 内容和源站点文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-142">The following sections explain how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## <a name="resource-file-pack-uris"></a><span data-ttu-id="f0c71-143">资源文件 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-143">Resource File Pack URIs</span></span>  
 <span data-ttu-id="f0c71-144">资源文件配置为[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Resource`项并编译到程序集。</span><span class="sxs-lookup"><span data-stu-id="f0c71-144">Resource files are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Resource` items and are compiled into assemblies.</span></span> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="f0c71-145"> 支持包构造[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]可以用于标识资源文件编译到本地程序集或编译到从本地程序集引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="f0c71-145"> supports the construction of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>  
  
<a name="Local_Assembly_Resource_File"></a>   
### <a name="local-assembly-resource-file"></a><span data-ttu-id="f0c71-146">本地程序集资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-146">Local Assembly Resource File</span></span>  
 <span data-ttu-id="f0c71-147">包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]资源编译到本地程序集的文件使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="f0c71-147">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="f0c71-148">**授权**：application:///。</span><span class="sxs-lookup"><span data-stu-id="f0c71-148">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="f0c71-149">**路径**：资源文件的名称，包括其相对于本地程序集项目文件夹根目录的路径。</span><span class="sxs-lookup"><span data-stu-id="f0c71-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>  
  
 <span data-ttu-id="f0c71-150">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]位于本地程序集的项目文件夹的根目录中的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-150">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="f0c71-151">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]位于本地程序集的项目文件夹的子文件夹中的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-151">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="f0c71-152">引用的程序集资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-152">Referenced Assembly Resource File</span></span>  
 <span data-ttu-id="f0c71-153">包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]资源编译到引用的程序集中的文件使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="f0c71-153">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="f0c71-154">**授权**：application:///。</span><span class="sxs-lookup"><span data-stu-id="f0c71-154">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="f0c71-155">**路径**：编译到所引用程序集内的资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f0c71-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="f0c71-156">路径必须符合以下格式：</span><span class="sxs-lookup"><span data-stu-id="f0c71-156">The path must conform to the following format:</span></span>  
  
     <span data-ttu-id="f0c71-157">*程序集短名称*{*;版本*] {*;PublicKey*]; 组件 /*路径*</span><span class="sxs-lookup"><span data-stu-id="f0c71-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>  
  
    -   <span data-ttu-id="f0c71-158">**程序集短名称**：所引用的程序集的短名称。</span><span class="sxs-lookup"><span data-stu-id="f0c71-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>  
  
    -   <span data-ttu-id="f0c71-159">**;版本** [可选]：所引用的包含资源文件的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="f0c71-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="f0c71-160">此部分在加载两个或多个具有相同短名称的引用程序集时使用。</span><span class="sxs-lookup"><span data-stu-id="f0c71-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    -   <span data-ttu-id="f0c71-161">**;公钥** [可选]：用于对引用程序集进行签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="f0c71-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="f0c71-162">此部分在加载两个或多个具有相同短名称的引用程序集时使用。</span><span class="sxs-lookup"><span data-stu-id="f0c71-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>  
  
    -   <span data-ttu-id="f0c71-163">**;组件**：指定所引用的程序集是从本地程序集引用的。</span><span class="sxs-lookup"><span data-stu-id="f0c71-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>  
  
    -   <span data-ttu-id="f0c71-164">**/路径**：资源文件的名称，包括其相对于所引用程序集的项目文件夹根目录的路径。</span><span class="sxs-lookup"><span data-stu-id="f0c71-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>  
  
 <span data-ttu-id="f0c71-165">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]位于引用程序集的项目文件夹的根目录中的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-165">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 <span data-ttu-id="f0c71-166">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]位于被引用程序集的项目文件夹的子文件夹中的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-166">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 <span data-ttu-id="f0c71-167">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]位于引用的、 特定于版本的程序集的项目文件夹的根文件夹中的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-167">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 <span data-ttu-id="f0c71-168">请注意，包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用的程序集资源文件的语法可以仅用于应用程序: / / 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="f0c71-168">Note that the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="f0c71-169">例如，以下不支持在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-169">For example, the following is not supported in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## <a name="content-file-pack-uris"></a><span data-ttu-id="f0c71-170">内容文件 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-170">Content File Pack URIs</span></span>  
 <span data-ttu-id="f0c71-171">包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]内容文件使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="f0c71-171">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a content file uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="f0c71-172">**授权**：application:///。</span><span class="sxs-lookup"><span data-stu-id="f0c71-172">**Authority**: application:///.</span></span>  
  
-   <span data-ttu-id="f0c71-173">**路径**：内容文件的名称，包括其相对于应用程序的主可执行程序集的文件系统位置的路径。</span><span class="sxs-lookup"><span data-stu-id="f0c71-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>  
  
 <span data-ttu-id="f0c71-174">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]位于可执行程序集所在的文件夹中的内容文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-174">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 <span data-ttu-id="f0c71-175">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]内容文件位于相对于应用程序的可执行程序集的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f0c71-175">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  <span data-ttu-id="f0c71-176">无法导航到 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 内容文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-176">[!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] content files cannot be navigated to.</span></span> <span data-ttu-id="f0c71-177">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]方案仅支持导航到[!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]位于源站点的文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-177">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] scheme only supports navigation to [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] files that are located at the site of origin.</span></span>  
  
<a name="The_siteoforigin_____Authority"></a>   
## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="f0c71-178">源站点 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-178">Site of Origin Pack URIs</span></span>  
 <span data-ttu-id="f0c71-179">包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为源站点文件使用以下授权和路径：</span><span class="sxs-lookup"><span data-stu-id="f0c71-179">The pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a site of origin file uses the following authority and path:</span></span>  
  
-   <span data-ttu-id="f0c71-180">**授权**：siteoforigin:///。</span><span class="sxs-lookup"><span data-stu-id="f0c71-180">**Authority**: siteoforigin:///.</span></span>  
  
-   <span data-ttu-id="f0c71-181">**路径**：源站点文件的名称，包括其相对于可执行程序集启动位置的路径。</span><span class="sxs-lookup"><span data-stu-id="f0c71-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>  
  
 <span data-ttu-id="f0c71-182">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]源站点文件，存储在从中启动可执行程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="f0c71-182">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 <span data-ttu-id="f0c71-183">下面的示例演示了包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]源站点文件，存储在相对于从中启动应用程序的可执行程序集位置的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="f0c71-183">The following example shows the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## <a name="page-files"></a><span data-ttu-id="f0c71-184">页面文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-184">Page Files</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<span data-ttu-id="f0c71-185"> 为配置文件[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page`项被编译到程序集资源文件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="f0c71-185"> files that are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="f0c71-186">因此， [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page`可以使用包标识项[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-186">Consequently, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items can be identified using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files.</span></span>  
  
 <span data-ttu-id="f0c71-187">类型[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通常被配置为文件[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page`项具有以下内容作为其根元素之一：</span><span class="sxs-lookup"><span data-stu-id="f0c71-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items have one of the following as their root element:</span></span>  
  
-   <xref:System.Windows.Window?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="f0c71-188">绝对与相对 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-188">Absolute vs. Relative Pack URIs</span></span>  
 <span data-ttu-id="f0c71-189">完全限定的 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]包括方案、 授权和路径，且将其视为绝对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-189">A fully qualified pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] includes the scheme, the authority, and the path, and it is considered an absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="f0c71-190">作为面向开发人员，简化[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]元素通常允许您设置相应的属性的相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]，其中仅包含路径。</span><span class="sxs-lookup"><span data-stu-id="f0c71-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], which includes only the path.</span></span>  
  
 <span data-ttu-id="f0c71-191">例如，考虑具有以下绝对 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]本地程序集内的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-191">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for a resource file in the local assembly.</span></span>  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 <span data-ttu-id="f0c71-192">相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] ，是指此资源文件将如下所示。</span><span class="sxs-lookup"><span data-stu-id="f0c71-192">The relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that refers to this resource file would be the following.</span></span>  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  <span data-ttu-id="f0c71-193">由于源站点文件不与程序集相关联，因此它们可以仅引用使用绝对 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="f0c71-194">默认情况下，相对 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]被视为相对于标记或包含引用的代码的位置。</span><span class="sxs-lookup"><span data-stu-id="f0c71-194">By default, a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="f0c71-195">但是，如果使用前导反斜杠，则将相对 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用视为相对于应用程序的根。</span><span class="sxs-lookup"><span data-stu-id="f0c71-195">If a leading backslash is used, however, the relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="f0c71-196">例如，假设具有以下项目结构。</span><span class="sxs-lookup"><span data-stu-id="f0c71-196">For example, consider the following project structure.</span></span>  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 <span data-ttu-id="f0c71-197">如果 Page1.xaml 包含[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用*根*\SubFolder\Page2.xaml，该引用可以使用以下相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-197">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `Page2.xaml`  
  
 <span data-ttu-id="f0c71-198">如果 Page1.xaml 包含[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用*根*\Page2.xaml，该引用可以使用以下相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-198">If Page1.xaml contains a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references *Root*\Page2.xaml, the reference can use the following relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## <a name="pack-uri-resolution"></a><span data-ttu-id="f0c71-199">Pack URI 解析</span><span class="sxs-lookup"><span data-stu-id="f0c71-199">Pack URI Resolution</span></span>  
 <span data-ttu-id="f0c71-200">包的格式[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]使得包[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]对于不同类型的文件看起来相同。</span><span class="sxs-lookup"><span data-stu-id="f0c71-200">The format of pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] makes it possible for pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for different types of files to look the same.</span></span> <span data-ttu-id="f0c71-201">例如，考虑具有以下绝对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-201">For example, consider the following absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="f0c71-202">此绝对 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]无法引用本地程序集内的资源文件或内容文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-202">This absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="f0c71-203">同样适用于以下相对[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-203">The same is true for the following relative [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
 `/ResourceOrContentFile.xaml`  
  
 <span data-ttu-id="f0c71-204">为了确定的类型文件的 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]指的是，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]解析[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]本地程序集和内容文件使用以下试探方法内的资源文件：</span><span class="sxs-lookup"><span data-stu-id="f0c71-204">In order to determine the type of file that a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] resolves [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] for resource files in local assemblies and content files by using the following heuristics:</span></span>  
  
1.  <span data-ttu-id="f0c71-205">探测程序集的元数据<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>匹配的包属性[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0c71-206">如果<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>找到属性，包的路径[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用的内容文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a content file.</span></span>  
  
3.  <span data-ttu-id="f0c71-207">如果<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>找不到属性，探测编译到本地程序集的集资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>  
  
4.  <span data-ttu-id="f0c71-208">如果匹配的包的路径的资源文件[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]找到，则包的路径[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]引用的资源文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-208">If a resource file that matches the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is found, the path of the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] refers to a resource file.</span></span>  
  
5.  <span data-ttu-id="f0c71-209">如果未找到资源，在内部创建<xref:System.Uri>无效。</span><span class="sxs-lookup"><span data-stu-id="f0c71-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]<span data-ttu-id="f0c71-210"> 解析不适用于[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="f0c71-210"> resolution does not apply for [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that refer to the following:</span></span>  
  
-   <span data-ttu-id="f0c71-211">引用的程序集内的内容文件： 这些文件类型不受[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-211">Content files in referenced assemblies: these file types are not supported by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span>  
  
-   <span data-ttu-id="f0c71-212">嵌入的文件中引用的程序集：[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]标识这些是唯一的因为它们包括这两个引用的程序集的名称和`;component`后缀。</span><span class="sxs-lookup"><span data-stu-id="f0c71-212">Embedded files in referenced assemblies: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>  
  
-   <span data-ttu-id="f0c71-213">源站点文件：[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]标识这些是唯一的因为它们是由包的唯一文件[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]包含 siteoforigin:/// 授权: / / 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="f0c71-213">Site of origin files: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that identify them are unique because they are the only files that can be identified by pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that contain the siteoforigin:/// authority.</span></span>  
  
 <span data-ttu-id="f0c71-214">包的一种简化形式[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]解析使是让代码在某种程度上独立于资源和内容文件的位置。</span><span class="sxs-lookup"><span data-stu-id="f0c71-214">One simplification that pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="f0c71-215">例如，如果有本地程序集重新配置为内容文件，包中的资源文件[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]的资源将保持不变，可使用包的代码一样[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] for the resource remains the same, as does the code that uses the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
<a name="Programming_with_Pack_URIs"></a>   
## <a name="programming-with-pack-uris"></a><span data-ttu-id="f0c71-216">使用 Pack URI 编程</span><span class="sxs-lookup"><span data-stu-id="f0c71-216">Programming with Pack URIs</span></span>  
 <span data-ttu-id="f0c71-217">许多[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]类实现可设置与包属性的[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]，其中包括：</span><span class="sxs-lookup"><span data-stu-id="f0c71-217">Many [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classes implement properties that can be set with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], including:</span></span>  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="f0c71-218">可以从标记和代码中设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="f0c71-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="f0c71-219">本节演示这两种设置方式的基本构造，然后演示通用方案示例。</span><span class="sxs-lookup"><span data-stu-id="f0c71-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="f0c71-220">在标记中使用 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-220">Using Pack URIs in Markup</span></span>  
 <span data-ttu-id="f0c71-221">一个包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]通过设置包具有的属性元素标记中指定[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-221">A pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is specified in markup by setting the element of an attribute with the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span> <span data-ttu-id="f0c71-222">例如：</span><span class="sxs-lookup"><span data-stu-id="f0c71-222">For example:</span></span>  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 <span data-ttu-id="f0c71-223">表 1 说明了各种绝对 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] ，可以在标记中指定。</span><span class="sxs-lookup"><span data-stu-id="f0c71-223">Table 1 illustrates the various absolute pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="f0c71-224">表 1：标记中的绝对 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-224">Table 1: Absolute Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="f0c71-225">文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-225">File</span></span>|<span data-ttu-id="f0c71-226">绝对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c71-226">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="f0c71-227">资源文件 - 本地程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-228">子文件夹中的资源文件 - 本地程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-229">资源文件 - 引用的程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-230">所引用程序集的子文件夹中的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-231">所引用版本化程序集中的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-232">内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|  
|<span data-ttu-id="f0c71-233">子文件夹中的内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|  
|<span data-ttu-id="f0c71-234">源站点文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|  
|<span data-ttu-id="f0c71-235">子文件夹中的源站点文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|  
  
 <span data-ttu-id="f0c71-236">表 2 说明了各种相对 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] ，可以在标记中指定。</span><span class="sxs-lookup"><span data-stu-id="f0c71-236">Table 2 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in markup.</span></span>  
  
 <span data-ttu-id="f0c71-237">表 2：标记中的相对 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-237">Table 2: Relative Pack URIs in Markup</span></span>  
  
|<span data-ttu-id="f0c71-238">文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-238">File</span></span>|<span data-ttu-id="f0c71-239">相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c71-239">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="f0c71-240">本地程序集内的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-241">本地程序集的子文件夹中的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-242">所引用程序集内的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-243">所引用程序集的子文件夹中的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|<span data-ttu-id="f0c71-244">内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-244">Content file</span></span>|`"/ContentFile.xaml"`|  
|<span data-ttu-id="f0c71-245">子文件夹中的内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### <a name="using-pack-uris-in-code"></a><span data-ttu-id="f0c71-246">在代码中使用 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-246">Using Pack URIs in Code</span></span>  
 <span data-ttu-id="f0c71-247">指定包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]在代码中通过实例化<xref:System.Uri>类并传递包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]作为构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="f0c71-247">You specify a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in code by instantiating the <xref:System.Uri> class and passing the pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] as a parameter to the constructor.</span></span> <span data-ttu-id="f0c71-248">下面的示例说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="f0c71-248">This is demonstrated in the following example.</span></span>  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 <span data-ttu-id="f0c71-249">默认情况下<xref:System.Uri>类将 pack[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]以是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="f0c71-249">By default, the <xref:System.Uri> class considers pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to be absolute.</span></span> <span data-ttu-id="f0c71-250">因此，引发异常的实例时<xref:System.Uri>类创建的相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f0c71-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 <span data-ttu-id="f0c71-251">幸运的是，<xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29>的重载<xref:System.Uri>类构造函数接受类型的参数<xref:System.UriKind>允许您指定是否将包[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]是绝对或相对。</span><span class="sxs-lookup"><span data-stu-id="f0c71-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is either absolute or relative.</span></span>  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml",   
                        UriKind.Relative);  
```  
  
 <span data-ttu-id="f0c71-252">应仅指定<xref:System.UriKind.Absolute>或<xref:System.UriKind.Relative>您可以确信所提供的 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]是一个或另一个。</span><span class="sxs-lookup"><span data-stu-id="f0c71-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] is one or the other.</span></span> <span data-ttu-id="f0c71-253">如果不知道包的类型[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]，使用，例如当用户输入 pack[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]在运行时，使用<xref:System.UriKind.RelativeOrAbsolute>相反。</span><span class="sxs-lookup"><span data-stu-id="f0c71-253">If you don't know the type of pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that is used, such as when a user enters a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 <span data-ttu-id="f0c71-254">表 3 说明了各种相对 pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] ，可以使用在代码中指定<xref:System.Uri?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f0c71-254">Table 3 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f0c71-255">表 3：代码中的绝对 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-255">Table 3: Absolute Pack URIs in Code</span></span>  
  
|<span data-ttu-id="f0c71-256">文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-256">File</span></span>|<span data-ttu-id="f0c71-257">绝对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c71-257">Absolute pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="f0c71-258">资源文件 - 本地程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-259">子文件夹中的资源文件 - 本地程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-260">资源文件 - 引用的程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-261">所引用程序集的子文件夹中的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-262">所引用版本化程序集中的资源文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-263">内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-264">子文件夹中的内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-265">源站点文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|  
|<span data-ttu-id="f0c71-266">子文件夹中的源站点文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|  
  
 <span data-ttu-id="f0c71-267">表 4 阐释了各种相对 pack[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]你可以指定在代码中使用<xref:System.Uri?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="f0c71-267">Table 4 illustrates the various relative pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f0c71-268">表 4：代码中的相对 Pack URI</span><span class="sxs-lookup"><span data-stu-id="f0c71-268">Table 4: Relative Pack URIs in Code</span></span>  
  
|<span data-ttu-id="f0c71-269">文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-269">File</span></span>|<span data-ttu-id="f0c71-270">相对 pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c71-270">Relative pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]</span></span>|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="f0c71-271">资源文件 - 本地程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="f0c71-272">子文件夹中的资源文件 - 本地程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="f0c71-273">资源文件 - 引用的程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="f0c71-274">子文件夹中的资源文件 - 引用的程序集</span><span class="sxs-lookup"><span data-stu-id="f0c71-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="f0c71-275">内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|<span data-ttu-id="f0c71-276">子文件夹中的内容文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="f0c71-277">常见 Pack URI 方案</span><span class="sxs-lookup"><span data-stu-id="f0c71-277">Common Pack URI Scenarios</span></span>  
 <span data-ttu-id="f0c71-278">前面几节讨论了如何构造 pack[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]来标识资源、 内容和源站点文件。</span><span class="sxs-lookup"><span data-stu-id="f0c71-278">The preceding sections have discussed how to construct pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="f0c71-279">在[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]、 中有许多种情况下，使用这些构造和以下部分介绍了几种常见用法。</span><span class="sxs-lookup"><span data-stu-id="f0c71-279">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="f0c71-280">指定当应用程序启动时显示的 UI</span><span class="sxs-lookup"><span data-stu-id="f0c71-280">Specifying the UI to Show When an Application Starts</span></span>  
 <span data-ttu-id="f0c71-281"><xref:System.Windows.Application.StartupUri%2A> 指定第一个[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]时显示[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0c71-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application is launched.</span></span> <span data-ttu-id="f0c71-282">对于独立应用程序，[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]可以是一个窗口，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f0c71-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 <span data-ttu-id="f0c71-283">独立应用程序和[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]还可以指定页为初始 UI，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f0c71-283">Standalone applications and [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] can also specify a page as the initial UI, as shown in the following example.</span></span>  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 <span data-ttu-id="f0c71-284">如果应用程序是一个独立应用程序并使用指定了一个页面<xref:System.Windows.Application.StartupUri%2A>，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]将打开<xref:System.Windows.Navigation.NavigationWindow>以承载该页面。</span><span class="sxs-lookup"><span data-stu-id="f0c71-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="f0c71-285">有关[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]，主机浏览器中显示了页。</span><span class="sxs-lookup"><span data-stu-id="f0c71-285">For [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], the page is shown in the host browser.</span></span>  
  
<a name="Navigating_to_a_Page"></a>   
#### <a name="navigating-to-a-page"></a><span data-ttu-id="f0c71-286">导航到页面</span><span class="sxs-lookup"><span data-stu-id="f0c71-286">Navigating to a Page</span></span>  
 <span data-ttu-id="f0c71-287">下面的示例演示如何导航到页面。</span><span class="sxs-lookup"><span data-stu-id="f0c71-287">The following example shows how to navigate to a page.</span></span>  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 <span data-ttu-id="f0c71-288">有关详细信息中导航的各种方法[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，请参阅[导航概述](../../../../docs/framework/wpf/app-development/navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f0c71-288">For more information on the various ways to navigate in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>  
  
<a name="Specifying_a_Window_Icon"></a>   
#### <a name="specifying-a-window-icon"></a><span data-ttu-id="f0c71-289">指定窗口图标</span><span class="sxs-lookup"><span data-stu-id="f0c71-289">Specifying a Window Icon</span></span>  
 <span data-ttu-id="f0c71-290">下面的示例演示如何使用 URI 指定窗口的图标。</span><span class="sxs-lookup"><span data-stu-id="f0c71-290">The following example shows how to use a URI to specify a window's icon.</span></span>  
  
 [!code-xaml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 <span data-ttu-id="f0c71-291">有关详细信息，请参阅<xref:System.Windows.Window.Icon%2A>。</span><span class="sxs-lookup"><span data-stu-id="f0c71-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="f0c71-292">加载图像、音频和视频文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-292">Loading Image, Audio, and Video Files</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="f0c71-293"> 允许应用程序使用各种媒体类型，所有这些都可以标识和加载与包[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f0c71-293"> allows applications to use a wide variety of media types, all of which can be identified and loaded with pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], as shown in the following examples.</span></span>  
  
 [!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xaml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 <span data-ttu-id="f0c71-294">使用媒体内容的详细信息，请参阅[图形和多媒体](../../../../docs/framework/wpf/graphics-multimedia/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f0c71-294">For more information on working with media content, see [Graphics and Multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md).</span></span>  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="f0c71-295">从源站点加载资源字典</span><span class="sxs-lookup"><span data-stu-id="f0c71-295">Loading a Resource Dictionary from the Site of Origin</span></span>  
 <span data-ttu-id="f0c71-296">资源字典 (<xref:System.Windows.ResourceDictionary>) 可用于支持应用程序的主题。</span><span class="sxs-lookup"><span data-stu-id="f0c71-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="f0c71-297">创建和管理主题的一种方式是将多个主题创建为位于应用程序源站点的资源字典。</span><span class="sxs-lookup"><span data-stu-id="f0c71-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="f0c71-298">这样，在添加和更新主题时将无需重新编译和重新部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0c71-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="f0c71-299">这些资源字典可以标识和使用包加载[!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]，下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="f0c71-299">These resource dictionaries can be identified and loaded using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], which is shown in the following example.</span></span>  
  
 [!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 <span data-ttu-id="f0c71-300">有关中的主题的概述[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，请参阅[样式和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="f0c71-300">For an overview of themes in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c71-301">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0c71-301">See Also</span></span>  
 [<span data-ttu-id="f0c71-302">WPF 应用程序资源、内容和数据文件</span><span class="sxs-lookup"><span data-stu-id="f0c71-302">WPF Application Resource, Content, and Data Files</span></span>](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
