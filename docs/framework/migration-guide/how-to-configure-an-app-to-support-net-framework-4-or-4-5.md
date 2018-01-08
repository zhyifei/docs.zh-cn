---
title: "如何：配置应用程序以支持 .NET Framework 4 或 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring apps to support .NET Framework 4
- .NET Framework 4, configuring apps
- .NET Framework 4.5, configuring apps
ms.assetid: 63c6b9a8-0088-4077-9aa3-521ab7290f79
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ba3d248dbdd81cf2e2e4445d1e1eb160605542c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-an-app-to-support-net-framework-4-or-45"></a><span data-ttu-id="34219-102">如何：配置应用程序以支持 .NET Framework 4 或 4.5</span><span class="sxs-lookup"><span data-stu-id="34219-102">How to: Configure an App to Support .NET Framework 4 or 4.5</span></span>
<span data-ttu-id="34219-103">托管公共语言运行时 (CLR) 的所有应用程序都必须启动（或*激活*）CLR，才能运行托管代码。</span><span class="sxs-lookup"><span data-stu-id="34219-103">All apps that host the common language runtime (CLR) need to start, or *activate*, the CLR in order to run managed code.</span></span> <span data-ttu-id="34219-104">通常，.NET Framework 应用程序在生成它的 CLR 版本上运行，但您可以使用应用程序配置文件（有时称为 app.config 文件）来更改桌面应用程序的此行为。</span><span class="sxs-lookup"><span data-stu-id="34219-104">Typically, a   .NET Framework app runs on the version of the CLR that it was built on, but you can change this behavior for desktop apps by using an application configuration file (sometimes referred to as an app.config file).</span></span> <span data-ttu-id="34219-105">但是，您不能使用应用程序配置文件来更改 Windows 应用商店应用或 Windows Phone 应用程序的默认激活行为。</span><span class="sxs-lookup"><span data-stu-id="34219-105">However, you cannot change the default activation behavior for Windows Store apps or Windows Phone apps by using an application configuration file.</span></span> <span data-ttu-id="34219-106">本文说明如何使桌面应用程序能够在 .NET Framework 的其他版本上运行，并提供了如何定位版本 4 或 4.5 的示例。</span><span class="sxs-lookup"><span data-stu-id="34219-106">This article explains how to enable your desktop app to run on another version of the .NET Framework and provides an example of how to target version 4 or 4.5.</span></span>  
  
 <span data-ttu-id="34219-107">按下列顺序确定在其上运行应用程序的 .NET Framework 的版本：</span><span class="sxs-lookup"><span data-stu-id="34219-107">The version of the .NET Framework that an app runs on is determined in the following order:</span></span>  
  
-   <span data-ttu-id="34219-108">配置文件。</span><span class="sxs-lookup"><span data-stu-id="34219-108">Configuration file.</span></span>  
  
     <span data-ttu-id="34219-109">如果应用程序配置文件中的 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 条目指定了一个或多个 .NET Framework 版本，且用户计算机安装的是其中一个版本，那么应用程序就会在相应版本中运行。</span><span class="sxs-lookup"><span data-stu-id="34219-109">If the application configuration file includes [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) entries that specify one or more .NET Framework versions, and one of those versions is present on the user's computer, the app runs on that version.</span></span> <span data-ttu-id="34219-110">配置文件按列出顺序读取 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 条目，并使用列出的第一个在用户计算机上安装的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="34219-110">The configuration file reads [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) entries in the order they are listed, and uses the first .NET Framework version listed that is present on the user's computer.</span></span> <span data-ttu-id="34219-111">（对版本 1.0 使用 [\<requiredRuntime> 元素](../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)。）</span><span class="sxs-lookup"><span data-stu-id="34219-111">(Use the [\<requiredRuntime> element](../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) for version 1.0.)</span></span>  
  
-   <span data-ttu-id="34219-112">编译的版本。</span><span class="sxs-lookup"><span data-stu-id="34219-112">Compiled version.</span></span>  
  
     <span data-ttu-id="34219-113">如果不存在任何配置文件，但用户计算机上存在基于其构建应用程序的 .NET Framework 版本，则此应用程序将在此版本上运行。</span><span class="sxs-lookup"><span data-stu-id="34219-113">If there is no configuration file, but the version of the .NET Framework that the app was built on is present on the user's computer, the app runs on that version.</span></span>  
  
-   <span data-ttu-id="34219-114">已安装的最新版本。</span><span class="sxs-lookup"><span data-stu-id="34219-114">Latest version installed.</span></span>  
  
     <span data-ttu-id="34219-115">如果生成应用程序的 .NET Framework 版本没有，且配置文件未在 [\<supportedRuntime> 元素](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)中指定版本，那么应用程序会尝试在用户计算机上安装的最新版 .NET Framework 中运行。</span><span class="sxs-lookup"><span data-stu-id="34219-115">If the version of the .NET Framework that the app was built on is not present and a configuration file does not specify a version in a [\<supportedRuntime> element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md), the app tries to run on the latest version of the .NET Framework that is present on the user's computer.</span></span>  
  
     <span data-ttu-id="34219-116">但是，.NET Framework 1.0、1.1、2.0、3.0 和 3.5 应用程序不会自动在 .NET Framework 4 或更高版本上运行，在某些情况下，用户可能会收到错误，且系统可能会提示用户安装 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="34219-116">However, .NET Framework 1.0, 1.1, 2.0, 3.0, and 3.5 apps do not automatically run on the .NET Framework 4 or later, and in some cases, the user may receive an error and may be prompted to install the .NET Framework 3.5.</span></span> <span data-ttu-id="34219-117">由于不同版本的 Windows 系统包含的 .NET Framework 版本不同，因此激活行为还取决于用户的操作系统。</span><span class="sxs-lookup"><span data-stu-id="34219-117">The activation behavior may also depend on the user’s operating system, because  different versions of Windows system include different versions of the .NET Framework.</span></span> <span data-ttu-id="34219-118">如果应用程序支持 .NET Framework 3.5 和 4 或更高版本，建议您在配置文件中使用多个条目来指明这一点，以避免 .NET Framework 初始化错误。</span><span class="sxs-lookup"><span data-stu-id="34219-118">If your app supports both the .NET Framework 3.5 and 4 or later, we recommend that you indicate this with multiple entries in the configuration file to avoid .NET Framework initialization errors.</span></span> <span data-ttu-id="34219-119">有关详细信息，请参见[版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="34219-119">For more information, see [Versions and Dependencies](../../../docs/framework/migration-guide/versions-and-dependencies.md).</span></span>  
  
 <span data-ttu-id="34219-120">为了利用版本 4 和 4.5 中的性能改进，您可能还需要将您的 .NET Framework 3.5 应用程序配置为在 .NET Framework 版本 4 或 4.5 上运行，甚至在安装了 .NET Framework 3.5 的计算机上也是如此。</span><span class="sxs-lookup"><span data-stu-id="34219-120">You might also want to configure your .NET Framework 3.5 apps to run on the .NET Framework 4 or 4.5, even on computers that have the .NET Framework 3.5 installed, to take advantage of the performance improvements in versions 4 and 4.5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34219-121">建议你始终在你支持的每个 .NET Framework 版本上测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="34219-121">We recommend that you always test your app on every .NET Framework version that you support.</span></span> <span data-ttu-id="34219-122">若要了解如何将应用程序升级为支持更高版本的 .NET Framework，请参阅[版本兼容性](../../../docs/framework/migration-guide/version-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="34219-122">See [Version Compatibility](../../../docs/framework/migration-guide/version-compatibility.md) for information about upgrading your application to support later .NET Framework versions.</span></span>  
  
 <span data-ttu-id="34219-123">若要了解如何将 .NET Framework 1.0 和 1.1 应用程序修改为支持 Windows 7 和 Windows 8，请参阅[从 .NET Framework 1.1 迁移](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)。</span><span class="sxs-lookup"><span data-stu-id="34219-123">For information about modifying your .NET Framework 1.0 and 1.1 apps to support Windows 7 and Windows 8, see [Migrating from the .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).</span></span>  
  
### <a name="to-configure-your-app-to-run-on-the-net-framework-4-or-45"></a><span data-ttu-id="34219-124">将应用程序配置为在 .NET Framework 4 或 4.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-124">To configure your app to run on the .NET Framework 4 or 4.5</span></span>  
  
1.  <span data-ttu-id="34219-125">添加或查找 .NET Framework 项目的配置文件。</span><span class="sxs-lookup"><span data-stu-id="34219-125">Add or locate the configuration file for the .NET Framework project.</span></span> <span data-ttu-id="34219-126">应用程序的配置文件与该应用程序位于相同的目录中，并且具有相同的名称，只不过它具有扩展名 .config。</span><span class="sxs-lookup"><span data-stu-id="34219-126">The configuration file for an app is in the same directory and has the same name as the app, but has a .config extension.</span></span> <span data-ttu-id="34219-127">例如，对于名为 MyExecutable.exe 的应用程序，应用程序配置文件的名称为 MyExecutable.exe.config。</span><span class="sxs-lookup"><span data-stu-id="34219-127">For example, for an app named MyExecutable.exe, the application configuration file is named MyExecutable.exe.config.</span></span>  
  
     <span data-ttu-id="34219-128">若要添加配置文件，请在 Visual Studio 菜单栏上依次选择“项目”和“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="34219-128">To add a configuration file, on the Visual Studio menu bar, choose **Project**, **Add New Item**.</span></span> <span data-ttu-id="34219-129">在左侧窗格中，依次选择“常规”和“配置文件”。</span><span class="sxs-lookup"><span data-stu-id="34219-129">Choose **General** from the left pane, and then choose **Configuration File**.</span></span>  <span data-ttu-id="34219-130">将配置文件命名为 *appName*.exe.config。这些菜单选项对于 Windows 应用商店应用或 Windows Phone 应用程序项目不可用，因为您无法在这些平台上更改激活策略。</span><span class="sxs-lookup"><span data-stu-id="34219-130">Name the configuration file *appName*.exe.config. These menu choices are not available for Windows Store app or Windows phone app projects, because you cannot change the activation policy on those platforms.</span></span>  
  
2.  <span data-ttu-id="34219-131">在应用程序配置文件中添加如下 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 元素：</span><span class="sxs-lookup"><span data-stu-id="34219-131">Add the [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) element as follows to the application configuration file:</span></span>  
  
    ```xml  
    <configuration>  
      <startup>  
        <supportedRuntime version="<version>"/>  
      </startup>  
    </configuration>  
    ```  
  
     <span data-ttu-id="34219-132">其中，*\<version>* 指定与应用程序支持的 .NET Framework 版本匹配的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="34219-132">where *\<version>* specifies the CLR version that aligns with the .NET Framework version that your app supports.</span></span> <span data-ttu-id="34219-133">使用以下字符串：</span><span class="sxs-lookup"><span data-stu-id="34219-133">Use the following strings:</span></span>  
  
    -   <span data-ttu-id="34219-134">.NET Framework 1.0：“v1.0.3705”</span><span class="sxs-lookup"><span data-stu-id="34219-134">.NET Framework 1.0: "v1.0.3705"</span></span>  
  
    -   <span data-ttu-id="34219-135">.NET Framework 1.1：“v1.1.4322”</span><span class="sxs-lookup"><span data-stu-id="34219-135">.NET Framework 1.1: "v1.1.4322"</span></span>  
  
    -   <span data-ttu-id="34219-136">.NET Framework 2.0、3.0 和 3.5：“v2.0.50727”</span><span class="sxs-lookup"><span data-stu-id="34219-136">.NET Framework 2.0, 3.0, and 3.5: "v2.0.50727"</span></span>  
  
    -   <span data-ttu-id="34219-137">.NET Framework 4 和 4.5（包括 4.5.1 等单点发行版）：“v4.0”</span><span class="sxs-lookup"><span data-stu-id="34219-137">.NET Framework 4 and 4.5 (including point releases such as 4.5.1): "v4.0"</span></span>  
  
     <span data-ttu-id="34219-138">可以添加多个 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 元素（按优先顺序列出）来指定对多个版本 .NET Framework 的支持。</span><span class="sxs-lookup"><span data-stu-id="34219-138">You can add multiple [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) elements, listed in order of preference, to specify support for multiple versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="34219-139">下表演示安装在计算机上的应用程序配置文件设置和 .NET Framework 版本如何确定在计算机上运行的 .NET Framework 3.5 应用程序的版本。</span><span class="sxs-lookup"><span data-stu-id="34219-139">The following table demonstrates how application configuration file settings and the .NET Framework versions installed on a computer determine the version that a .NET Framework 3.5 app runs on.</span></span> <span data-ttu-id="34219-140">这些示例特定于 .NET Framework 3.5 应用程序，但您可以将类似逻辑用于使用早期版本的 .NET Framework 生成的目标应用程序。</span><span class="sxs-lookup"><span data-stu-id="34219-140">The examples are specific to a .NET Framework 3.5 application, but you can use similar logic to target applications built with earlier .NET Framework versions.</span></span> <span data-ttu-id="34219-141">请注意，.NET Framework 2.0 版本号 (v2.0.50727) 用于在应用程序配置文件中指定 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="34219-141">Note that the .NET Framework 2.0 version number (v2.0.50727) is used to specify the .NET Framework 3.5 in the application configuration file.</span></span>  
  
|<span data-ttu-id="34219-142">App.config 文件设置</span><span class="sxs-lookup"><span data-stu-id="34219-142">App.config file setting</span></span>|<span data-ttu-id="34219-143">在安装了 3.5 版的计算机上</span><span class="sxs-lookup"><span data-stu-id="34219-143">On computer with version 3.5 installed</span></span>|<span data-ttu-id="34219-144">在安装了版本 3.5 和 4 或 4.5 的计算机上</span><span class="sxs-lookup"><span data-stu-id="34219-144">On computer with versions 3.5 and 4 or 4.5 installed</span></span>|<span data-ttu-id="34219-145">在安装了版本 4 或 4.5 的计算机上</span><span class="sxs-lookup"><span data-stu-id="34219-145">On computer with version 4 or 4.5 installed</span></span>|  
|-|-|-|-|  
|<span data-ttu-id="34219-146">无</span><span class="sxs-lookup"><span data-stu-id="34219-146">None</span></span>|<span data-ttu-id="34219-147">在 3.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-147">Runs on 3.5</span></span>|<span data-ttu-id="34219-148">在 3.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-148">Runs on 3.5</span></span>|<span data-ttu-id="34219-149">显示提示用户安装正确版本的错误消息*</span><span class="sxs-lookup"><span data-stu-id="34219-149">Displays error message that prompts user to install the correct version*</span></span>|  
|`<supportedRuntime version="v2.0.50727"/>`|<span data-ttu-id="34219-150">在 3.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-150">Runs on 3.5</span></span>|<span data-ttu-id="34219-151">在 3.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-151">Runs on 3.5</span></span>|<span data-ttu-id="34219-152">显示提示用户安装正确版本的错误消息*</span><span class="sxs-lookup"><span data-stu-id="34219-152">Displays error message that prompts user to install the correct version*</span></span>|  
|`<supportedRuntime version="v2.0.50727"/>` <br /> `<supportedRuntime version="v4.0"/>`|<span data-ttu-id="34219-153">在 3.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-153">Runs on 3.5</span></span>|<span data-ttu-id="34219-154">在 3.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-154">Runs on 3.5</span></span>|<span data-ttu-id="34219-155">在 4 或 4.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-155">Runs on 4 or 4.5</span></span>|  
|`<supportedRuntime version="v4.0"/>` <br /> `<supportedRuntime version="v2.0.50727"/>`|<span data-ttu-id="34219-156">在 3.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-156">Runs on 3.5</span></span>|<span data-ttu-id="34219-157">在 4 或 4.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-157">Runs on 4 or 4.5</span></span>|<span data-ttu-id="34219-158">在 4 或 4.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-158">Runs on 4 or 4.5</span></span>|  
|`<supportedRuntime version="v4.0"/>`|<span data-ttu-id="34219-159">显示提示用户安装正确版本的错误消息*</span><span class="sxs-lookup"><span data-stu-id="34219-159">Displays error message that prompts user to install the correct version*</span></span>|<span data-ttu-id="34219-160">在 4 或 4.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-160">Runs on 4 or 4.5</span></span>|<span data-ttu-id="34219-161">在 4 或 4.5 上运行</span><span class="sxs-lookup"><span data-stu-id="34219-161">Runs on 4 or 4.5</span></span>|  
  
 <span data-ttu-id="34219-162">\*若要详细了解此错误消息以及如何避免它，请参阅 [.NET Framework 初始化错误：管理用户体验](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="34219-162">\* For more information about this error message and ways to avoid it, see [.NET Framework Initialization Errors: Managing the User Experience](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34219-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="34219-163">See Also</span></span>  
 [<span data-ttu-id="34219-164">从 .NET Framework 1.1 迁移</span><span class="sxs-lookup"><span data-stu-id="34219-164">Migrating from the .NET Framework 1.1</span></span>](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)  
 [<span data-ttu-id="34219-165">迁移指南</span><span class="sxs-lookup"><span data-stu-id="34219-165">Migration Guide</span></span>](../../../docs/framework/migration-guide/index.md)
