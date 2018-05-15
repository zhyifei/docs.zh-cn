---
title: 部署 .NET Framework 和应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2686d0db966192606656167d6e505f34ded333f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="23731-102">部署 .NET Framework 和应用程序</span><span class="sxs-lookup"><span data-stu-id="23731-102">Deploying the .NET Framework and Applications</span></span>
<span data-ttu-id="23731-103">本文有助于你开始部署应用程序的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="23731-103">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="23731-104">大部分信息都是供开发人员、OEM 和企业管理人员使用的。</span><span class="sxs-lookup"><span data-stu-id="23731-104">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="23731-105">想在其自己的计算机上安装 .NET Framework 的用户应阅读[安装 .NET Framework](~/docs/framework/install/index.md)。</span><span class="sxs-lookup"><span data-stu-id="23731-105">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](~/docs/framework/install/index.md).</span></span>  
  
## <a name="key-deployment-resources"></a><span data-ttu-id="23731-106">关键部署资源</span><span class="sxs-lookup"><span data-stu-id="23731-106">Key Deployment Resources</span></span>  
 <span data-ttu-id="23731-107">使用以下指向启用 MSDN 主题的链接了解关于部署和维护 .NET Framework 的特定信息。</span><span class="sxs-lookup"><span data-stu-id="23731-107">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>  
  
 <span data-ttu-id="23731-108">**安装和部署**</span><span class="sxs-lookup"><span data-stu-id="23731-108">**Setup and deployment**</span></span>  
  
-   <span data-ttu-id="23731-109">安装程序和部署的一般信息：</span><span class="sxs-lookup"><span data-stu-id="23731-109">General installer and deployment information:</span></span>  
  
    -   <span data-ttu-id="23731-110">安装程序选项：</span><span class="sxs-lookup"><span data-stu-id="23731-110">Installer options:</span></span>  
  
        -   [<span data-ttu-id="23731-111">Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="23731-111">Web installer</span></span>](~/docs/framework/install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)  
  
        -   [<span data-ttu-id="23731-112">脱机安装程序</span><span class="sxs-lookup"><span data-stu-id="23731-112">Offline installer</span></span>](~/docs/framework/install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)  
  
    -   <span data-ttu-id="23731-113">安装模式：</span><span class="sxs-lookup"><span data-stu-id="23731-113">Installation modes:</span></span>  
  
        -   [<span data-ttu-id="23731-114">无提示安装</span><span class="sxs-lookup"><span data-stu-id="23731-114">Silent installation</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#chaining_custom)  
  
        -   [<span data-ttu-id="23731-115">显示 UI</span><span class="sxs-lookup"><span data-stu-id="23731-115">Displaying a UI</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#chaining_default)  
  
    -   [<span data-ttu-id="23731-116">在 .NET Framework 4.5 安装期间减少系统重新启动次数</span><span class="sxs-lookup"><span data-stu-id="23731-116">Reducing system restarts during .NET Framework 4.5 installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)  
  
    -   [<span data-ttu-id="23731-117">安装和卸载 .NET Framework 受阻疑难解答</span><span class="sxs-lookup"><span data-stu-id="23731-117">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](~/docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)  
  
-   <span data-ttu-id="23731-118">部署客户端应用程序中的 .NET Framework（适用于开发人员）：</span><span class="sxs-lookup"><span data-stu-id="23731-118">Deploying the .NET Framework with a client application (for developers):</span></span>  
  
    -   <span data-ttu-id="23731-119">在安装和部署项目中[使用 InstallShield](../../../docs/framework/deployment/deployment-guide-for-developers.md#installshield-deployment)</span><span class="sxs-lookup"><span data-stu-id="23731-119">[Using InstallShield](../../../docs/framework/deployment/deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>  
  
    -   [<span data-ttu-id="23731-120">使用 Visual Studio ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="23731-120">Using a Visual Studio ClickOnce application</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#clickonce-deployment)  
  
    -   [<span data-ttu-id="23731-121">创建 WiX 安装包</span><span class="sxs-lookup"><span data-stu-id="23731-121">Creating a WiX installation package</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#wix)  
  
    -   [<span data-ttu-id="23731-122">使用自定义安装程序</span><span class="sxs-lookup"><span data-stu-id="23731-122">Using a custom installer</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md#chaining)  
  
    -   <span data-ttu-id="23731-123">适用于开发人员的[其他信息](../../../docs/framework/deployment/deployment-guide-for-developers.md)</span><span class="sxs-lookup"><span data-stu-id="23731-123">[Additional information](../../../docs/framework/deployment/deployment-guide-for-developers.md) for developers</span></span>  
  
-   <span data-ttu-id="23731-124">部署.NET Framework（适用于 OEM 和管理人员）：</span><span class="sxs-lookup"><span data-stu-id="23731-124">Deploying the .NET Framework (for OEMs and administrators):</span></span>  
  
    -   [<span data-ttu-id="23731-125">Windows 评估和部署工具包 (ADK)</span><span class="sxs-lookup"><span data-stu-id="23731-125">Windows Assessment and Deployment Kit (ADK)</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=254976)  
  
    -   [<span data-ttu-id="23731-126">管理员指南</span><span class="sxs-lookup"><span data-stu-id="23731-126">Administrator's guide</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)  
  
 <span data-ttu-id="23731-127">**服务**</span><span class="sxs-lookup"><span data-stu-id="23731-127">**Servicing**</span></span>  
  
-   <span data-ttu-id="23731-128">有关一般信息，请参阅 [.NET Framework 博客](http://go.microsoft.com/fwlink/p/?LinkId=254977)</span><span class="sxs-lookup"><span data-stu-id="23731-128">For general information, see the [.NET Framework blog](http://go.microsoft.com/fwlink/p/?LinkId=254977)</span></span>  
  
-   [<span data-ttu-id="23731-129">检测版本</span><span class="sxs-lookup"><span data-stu-id="23731-129">Detecting versions</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
  
-   [<span data-ttu-id="23731-130">检测服务包和更新</span><span class="sxs-lookup"><span data-stu-id="23731-130">Detecting service packs and updates</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
  
## <a name="features-that-simplify-deployment"></a><span data-ttu-id="23731-131">简化部署的功能</span><span class="sxs-lookup"><span data-stu-id="23731-131">Features That Simplify Deployment</span></span>  
 <span data-ttu-id="23731-132">.NET Framework 提供了大量基本功能，让部署应用程序变得更加容易：</span><span class="sxs-lookup"><span data-stu-id="23731-132">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>  
  
-   <span data-ttu-id="23731-133">不产生影响的应用程序。</span><span class="sxs-lookup"><span data-stu-id="23731-133">No-impact applications.</span></span>  
  
     <span data-ttu-id="23731-134">此功能提供应用程序隔离功能并消除 DLL 冲突。</span><span class="sxs-lookup"><span data-stu-id="23731-134">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="23731-135">默认情况下，组件不会影响其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="23731-135">By default, components do not affect other applications.</span></span>  
  
-   <span data-ttu-id="23731-136">默认情况下的私有组件。</span><span class="sxs-lookup"><span data-stu-id="23731-136">Private components by default.</span></span>  
  
     <span data-ttu-id="23731-137">默认情况下，组件部署到应用程序目录，并且仅对包含的应用程序可见。</span><span class="sxs-lookup"><span data-stu-id="23731-137">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>  
  
-   <span data-ttu-id="23731-138">可控的代码共享。</span><span class="sxs-lookup"><span data-stu-id="23731-138">Controlled code sharing.</span></span>  
  
     <span data-ttu-id="23731-139">代码共享要求你显式提供代码以便进行共享而不是执行默认行为。</span><span class="sxs-lookup"><span data-stu-id="23731-139">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>  
  
-   <span data-ttu-id="23731-140">并行版本。</span><span class="sxs-lookup"><span data-stu-id="23731-140">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="23731-141">组件或应用程序的多个版本可以共存，你可以选择要使用的版本类型，公共语言运行时可以增强版本策略。</span><span class="sxs-lookup"><span data-stu-id="23731-141">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>  
  
-   <span data-ttu-id="23731-142">XCOPY 部署和复制。</span><span class="sxs-lookup"><span data-stu-id="23731-142">XCOPY deployment and replication.</span></span>  
  
     <span data-ttu-id="23731-143">在没有注册表项或依赖项的情况下就可以部署自描述和自持有的组件和应用程序。</span><span class="sxs-lookup"><span data-stu-id="23731-143">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>  
  
-   <span data-ttu-id="23731-144">动态更新。</span><span class="sxs-lookup"><span data-stu-id="23731-144">On-the-fly updates.</span></span>  
  
     <span data-ttu-id="23731-145">管理员可以使用宿主（例如，ASP.NET）更新程序 Dll，即使在远程计算机也可以。</span><span class="sxs-lookup"><span data-stu-id="23731-145">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>  
  
-   <span data-ttu-id="23731-146">与 Windows 安装程序相集成。</span><span class="sxs-lookup"><span data-stu-id="23731-146">Integration with the Windows Installer.</span></span>  
  
     <span data-ttu-id="23731-147">部署应用程序时，播发、发布、修复和按需安装都可用。</span><span class="sxs-lookup"><span data-stu-id="23731-147">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>  
  
-   <span data-ttu-id="23731-148">企业部署。</span><span class="sxs-lookup"><span data-stu-id="23731-148">Enterprise deployment.</span></span>  
  
     <span data-ttu-id="23731-149">此功能提供了简单的软件分发，包括使用 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="23731-149">This feature provides easy software distribution, including using Active Directory.</span></span>  
  
-   <span data-ttu-id="23731-150">下载和缓存。</span><span class="sxs-lookup"><span data-stu-id="23731-150">Downloading and caching.</span></span>  
  
     <span data-ttu-id="23731-151">增量下载可使下载大小变得更小，并且组件可以相互隔离，使其只供部署影响较低的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="23731-151">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>  
  
-   <span data-ttu-id="23731-152">部分受信任代码。</span><span class="sxs-lookup"><span data-stu-id="23731-152">Partially trusted code.</span></span>  
  
     <span data-ttu-id="23731-153">标识是基于代码而不是基于用户，并且不会出现任何证书对话框。</span><span class="sxs-lookup"><span data-stu-id="23731-153">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>  
  
## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="23731-154">打包和分发 .NET Framework 应用程序</span><span class="sxs-lookup"><span data-stu-id="23731-154">Packaging and Distributing .NET Framework Applications</span></span>  
 <span data-ttu-id="23731-155">文档中的其他章节介绍了打包和部署 .NET Framework 的部分信息。</span><span class="sxs-lookup"><span data-stu-id="23731-155">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="23731-156">这些章节介绍了以下关于自描述单元的信息：[程序集](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（不需要注册表项）、[强名称程序集](../../../docs/framework/app-domains/strong-named-assemblies.md)（确保名称的唯一性和避免名称欺骗）和[程序集版本控制](../../../docs/framework/app-domains/assembly-versioning.md)（可解决很多与 DLL 冲突相关的问题）。</span><span class="sxs-lookup"><span data-stu-id="23731-156">Those sections provide information about the self-describing units called [assemblies](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md), which require no registry entries, [strong-named assemblies](../../../docs/framework/app-domains/strong-named-assemblies.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../../docs/framework/app-domains/assembly-versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="23731-157">以下各节提供有关打包和分发.NET Framework 应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="23731-157">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>  
  
### <a name="packaging"></a><span data-ttu-id="23731-158">打包</span><span class="sxs-lookup"><span data-stu-id="23731-158">Packaging</span></span>  
 <span data-ttu-id="23731-159">.NET Framework 提供了用于打包应用程序的以下选项：</span><span class="sxs-lookup"><span data-stu-id="23731-159">The .NET Framework provides the following options for packaging applications:</span></span>  
  
-   <span data-ttu-id="23731-160">作为单个程序集或作为程序集的集合。</span><span class="sxs-lookup"><span data-stu-id="23731-160">As a single assembly or as a collection of assemblies.</span></span>  
  
     <span data-ttu-id="23731-161">使用此选项，你只需使用创建的 .dll 或 .exe 文件即可。</span><span class="sxs-lookup"><span data-stu-id="23731-161">With this option, you simply use the .dll or .exe files as they were built.</span></span>  
  
-   <span data-ttu-id="23731-162">作为 cabinet (CAB) 文件。</span><span class="sxs-lookup"><span data-stu-id="23731-162">As cabinet (CAB) files.</span></span>  
  
     <span data-ttu-id="23731-163">使用此选项，将文件压缩成 .cab 文件可使分发或下载耗时更少。</span><span class="sxs-lookup"><span data-stu-id="23731-163">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>  
  
-   <span data-ttu-id="23731-164">为 Windows Installer 程序包或其他安装程序格式。</span><span class="sxs-lookup"><span data-stu-id="23731-164">As a Windows Installer package or in other installer formats.</span></span>  
  
     <span data-ttu-id="23731-165">使用此选项，你可以创建用于 Windows Installer 的 .msi 文件或打包用于其他安装程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="23731-165">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>  
  
### <a name="distribution"></a><span data-ttu-id="23731-166">分布</span><span class="sxs-lookup"><span data-stu-id="23731-166">Distribution</span></span>  
 <span data-ttu-id="23731-167">.NET Framework 提供了用于分发应用程序的以下选项：</span><span class="sxs-lookup"><span data-stu-id="23731-167">The .NET Framework provides the following options for distributing applications:</span></span>  
  
-   <span data-ttu-id="23731-168">使用 XCOPY 或 FTP。</span><span class="sxs-lookup"><span data-stu-id="23731-168">Use XCOPY or FTP.</span></span>  
  
     <span data-ttu-id="23731-169">由于公共语言运行时应用程序是自描述的并且不需要注册表项，因此，你可以使用 XCOPY 或 FTP 只将应用程序复制到相应的目录。</span><span class="sxs-lookup"><span data-stu-id="23731-169">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="23731-170">然后即可从该目录运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="23731-170">The application can then be run from that directory.</span></span>  
  
-   <span data-ttu-id="23731-171">使用代码下载。</span><span class="sxs-lookup"><span data-stu-id="23731-171">Use code download.</span></span>  
  
     <span data-ttu-id="23731-172">如果你要通过 Internet 或公司的 Intranet 分发应用程序，只需将代码下载到计算机并在下载位置运行应用程序即可。</span><span class="sxs-lookup"><span data-stu-id="23731-172">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>  
  
-   <span data-ttu-id="23731-173">使用安装程序（例如 Windows Installer 2.0）。</span><span class="sxs-lookup"><span data-stu-id="23731-173">Use an installer program such as Windows Installer 2.0.</span></span>  
  
     <span data-ttu-id="23731-174">Windows Installer 2.0 可以安装、修复或删除全局程序集缓存和专用目录中的 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="23731-174">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>  
  
### <a name="installation-location"></a><span data-ttu-id="23731-175">安装位置</span><span class="sxs-lookup"><span data-stu-id="23731-175">Installation Location</span></span>  
 <span data-ttu-id="23731-176">要确定部署应用程序的程序集的位置，以便通过运行时找到它们，请参阅[运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="23731-176">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="23731-177">安全注意事项也可能会影响你部署应用程序的方式。</span><span class="sxs-lookup"><span data-stu-id="23731-177">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="23731-178">根据代码所在的位置授予托管代码安全权限。</span><span class="sxs-lookup"><span data-stu-id="23731-178">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="23731-179">将应用程序或组件部署到得不到信任的位置（例如 Internet），可限制应用程序或组件可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="23731-179">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="23731-180">有关部署和安全注意事项的详细信息，请参阅[代码访问安全性基础知识](../../../docs/framework/misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="23731-180">For more information about deployment and security considerations, see [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="23731-181">相关主题</span><span class="sxs-lookup"><span data-stu-id="23731-181">Related Topics</span></span>  
  
|<span data-ttu-id="23731-182">标题</span><span class="sxs-lookup"><span data-stu-id="23731-182">Title</span></span>|<span data-ttu-id="23731-183">描述</span><span class="sxs-lookup"><span data-stu-id="23731-183">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="23731-184">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="23731-184">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|<span data-ttu-id="23731-185">描述公共语言运行时如何确定将用于满足绑定请求的程序集类型。</span><span class="sxs-lookup"><span data-stu-id="23731-185">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|  
|[<span data-ttu-id="23731-186">适用于程序集加载的最佳做法</span><span class="sxs-lookup"><span data-stu-id="23731-186">Best Practices for Assembly Loading</span></span>](../../../docs/framework/deployment/best-practices-for-assembly-loading.md)|<span data-ttu-id="23731-187">讨论避免类型标识问题的方法，从而避免发生 <xref:System.InvalidCastException><xref:System.MissingMethodException> 和其他错误。</span><span class="sxs-lookup"><span data-stu-id="23731-187">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|  
|[<span data-ttu-id="23731-188">在 .NET Framework 4.5 安装期间减少系统重新启动次数</span><span class="sxs-lookup"><span data-stu-id="23731-188">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)|<span data-ttu-id="23731-189">描述在任何可能的情况下可以阻止重启的 Restart Manager，并说明安装 .NET Framework 的应用程序如何利用它。</span><span class="sxs-lookup"><span data-stu-id="23731-189">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|  
|[<span data-ttu-id="23731-190">面向管理员的部署指南</span><span class="sxs-lookup"><span data-stu-id="23731-190">Deployment Guide for Administrators</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)|<span data-ttu-id="23731-191">说明系统管理员如何通过系统中心配置管理器 (SCCM) 跨网络部署 .NET Framework 及其系统依赖项。</span><span class="sxs-lookup"><span data-stu-id="23731-191">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>|  
|[<span data-ttu-id="23731-192">面向开发人员的部署指南</span><span class="sxs-lookup"><span data-stu-id="23731-192">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)|<span data-ttu-id="23731-193">说明开发人员如何在其计算机的应用程序中安装 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="23731-193">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|  
|[<span data-ttu-id="23731-194">部署应用程序、服务和组件</span><span class="sxs-lookup"><span data-stu-id="23731-194">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="23731-195">讨论 Visual Studio 中的部署选项，包括使用 ClickOnce 和 Windows Installer 技术发布应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="23731-195">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>| 
|[<span data-ttu-id="23731-196">发布 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="23731-196">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="23731-197">描述打包 Windows 窗体应用程序以及使用 ClickOnce 将其部署到连网的客户端计算机上的方法。</span><span class="sxs-lookup"><span data-stu-id="23731-197">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|  
|[<span data-ttu-id="23731-198">打包和部署资源</span><span class="sxs-lookup"><span data-stu-id="23731-198">Packaging and Deploying Resources</span></span>](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="23731-199">描述 .NET Framework 用于打包和部署资源的中心辐射模型，包括资源命名约定、后备进程和打包替代项。</span><span class="sxs-lookup"><span data-stu-id="23731-199">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|  
|[<span data-ttu-id="23731-200">部署互操作应用程序</span><span class="sxs-lookup"><span data-stu-id="23731-200">Deploying an Interop Application</span></span>](../../../docs/framework/interop/deploying-an-interop-application.md)|<span data-ttu-id="23731-201">说明如何传送和安装互操作应用程序，通常包括 .NET Framework 客户端程序集、表示区分 COM 类型库的一个或多个互操作程序集以及一个或多个已注册的 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="23731-201">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|  
|[<span data-ttu-id="23731-202">如何：获取 .NET Framework 4.5 安装程序的进度</span><span class="sxs-lookup"><span data-stu-id="23731-202">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="23731-203">描述如何在没有提示的情况下启动和跟踪 .NET Framework 安装进度，同时显示你自己的安装进度视图。</span><span class="sxs-lookup"><span data-stu-id="23731-203">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23731-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="23731-204">See Also</span></span>  
 [<span data-ttu-id="23731-205">开发指南</span><span class="sxs-lookup"><span data-stu-id="23731-205">Development Guide</span></span>](../../../docs/framework/development-guide.md)
