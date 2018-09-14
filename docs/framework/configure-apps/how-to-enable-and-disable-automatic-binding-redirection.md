---
title: 如何：启用和禁用自动绑定重定向
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cf38bd753127e40c61512411c7aa2ebbbd7687db
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45618661"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="b1dba-102">如何：启用和禁用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="b1dba-102">How to: Enable and Disable Automatic Binding Redirection</span></span>

<span data-ttu-id="b1dba-103">当你编译面向 Visual Studio 中的应用[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]和更高版本，绑定重定向可能会自动添加到应用程序配置文件以重写程序集统一。</span><span class="sxs-lookup"><span data-stu-id="b1dba-103">When you compile apps in Visual Studio that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions, binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="b1dba-104">如果你的应用或其组件引用同一程序集的多个版本，就会添加绑定重定向，即使你在应用的配置文件中手动指定绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="b1dba-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="b1dba-105">自动绑定重定向功能会影响传统桌面应用和 web 应用面向[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]或更高版本中，虽然行为会略有不同的 web 应用。</span><span class="sxs-lookup"><span data-stu-id="b1dba-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] or a later version, although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="b1dba-106">如果你有面向较早版本 .NET Framework 的现有应用，则可以启用自动绑定重定向，如果要保留手动编写的绑定重定向，你可以将此功能禁用。</span><span class="sxs-lookup"><span data-stu-id="b1dba-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="b1dba-107">禁用自动绑定重定向在桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="b1dba-107">Disable automatic binding redirects in desktop apps</span></span>

<span data-ttu-id="b1dba-108">默认情况下，将为面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 及更高版本的传统桌面应用启用自动绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="b1dba-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="b1dba-109">编译应用并重写可能发生的程序集统一时，绑定重定向将添加到输出配置 (app.config) 文件中。</span><span class="sxs-lookup"><span data-stu-id="b1dba-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="b1dba-110">不修改源 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b1dba-110">The source app.config file is not modified.</span></span> <span data-ttu-id="b1dba-111">你可以通过修改应用的项目文件来禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="b1dba-111">You can disable this feature by modifying the project file for the app.</span></span>

1. <span data-ttu-id="b1dba-112">打开该项目文件进行编辑使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="b1dba-112">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="b1dba-113">在 Visual Studio 中，选择在项目**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="b1dba-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="b1dba-114">在文件资源管理器，找到项目 （.csproj 或.vbproj） 文件，并在记事本中打开它。</span><span class="sxs-lookup"><span data-stu-id="b1dba-114">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="b1dba-115">在 Visual Studio 中，在**解决方案资源管理器**，右键单击项目，然后选择**卸载项目**。</span><span class="sxs-lookup"><span data-stu-id="b1dba-115">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="b1dba-116">再次，右键单击已卸载的项目，然后选择**编辑 [项目名.csproj]**。</span><span class="sxs-lookup"><span data-stu-id="b1dba-116">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="b1dba-117">在项目文件中，查找以下属性项：</span><span class="sxs-lookup"><span data-stu-id="b1dba-117">In the project file, find the following property entry:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. <span data-ttu-id="b1dba-118">将 `true` 更改为 `false`：</span><span class="sxs-lookup"><span data-stu-id="b1dba-118">Change `true` to `false`:</span></span>

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a><span data-ttu-id="b1dba-119">手动启用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="b1dba-119">Enable automatic binding redirects manually</span></span>

<span data-ttu-id="b1dba-120">你可以面向旧版本的.NET Framework 中，或在其中你会不会自动提示你添加重定向的情况下启用现有应用中的自动绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="b1dba-120">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you're not automatically prompted to add a redirect.</span></span> <span data-ttu-id="b1dba-121">如果你面向较新版本的 framework 但未自动提示以添加重定向，则可能会建议重新映射程序集的生成输出。</span><span class="sxs-lookup"><span data-stu-id="b1dba-121">If you're targeting a newer version of the framework but do not get automatically prompted to add a redirect, you'll likely get build output that suggests you remap assemblies.</span></span>

1. <span data-ttu-id="b1dba-122">打开该项目文件进行编辑使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="b1dba-122">Open the project file for editing using one of the following methods:</span></span>

   - <span data-ttu-id="b1dba-123">在 Visual Studio 中，选择在项目**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="b1dba-123">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span> <span data-ttu-id="b1dba-124">在文件资源管理器，找到项目 （.csproj 或.vbproj） 文件，并在记事本中打开它。</span><span class="sxs-lookup"><span data-stu-id="b1dba-124">In File Explorer, find the project (.csproj or .vbproj) file and open it in Notepad.</span></span>
   - <span data-ttu-id="b1dba-125">在 Visual Studio 中，在**解决方案资源管理器**，右键单击项目，然后选择**卸载项目**。</span><span class="sxs-lookup"><span data-stu-id="b1dba-125">In Visual Studio, in **Solution Explorer**, right-click the project and choose **Unload Project**.</span></span> <span data-ttu-id="b1dba-126">再次，右键单击已卸载的项目，然后选择**编辑 [项目名.csproj]**。</span><span class="sxs-lookup"><span data-stu-id="b1dba-126">Right-click the unloaded project again, and then choose **Edit [projectname.csproj]**.</span></span>

2. <span data-ttu-id="b1dba-127">将以下元素添加到第一个配置属性组 (在\<PropertyGroup > 标记):</span><span class="sxs-lookup"><span data-stu-id="b1dba-127">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   <span data-ttu-id="b1dba-128">下面的示例项目文件具有插入元素：</span><span class="sxs-lookup"><span data-stu-id="b1dba-128">The following shows an example project file with the element inserted:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
       <PropertyGroup>
         <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>
         <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
         <ProjectGuid>{123334}</ProjectGuid>
         ...
         <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
       </PropertyGroup>
     ...
   </Project>
   ```

3. <span data-ttu-id="b1dba-129">编译你的应用。</span><span class="sxs-lookup"><span data-stu-id="b1dba-129">Compile your app.</span></span>

## <a name="enable-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="b1dba-130">启用 web 应用中的自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="b1dba-130">Enable automatic binding redirects in web apps</span></span>

<span data-ttu-id="b1dba-131">Web 应用的自动绑定重定向实现方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="b1dba-131">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="b1dba-132">由于必须修改 Web 应用的源配置 (web.config) 文件，因此绑定重定向不会自动添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="b1dba-132">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="b1dba-133">但是，Visual Studio 会通知你绑定冲突，你可以添加绑定重定向来解决此冲突。</span><span class="sxs-lookup"><span data-stu-id="b1dba-133">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="b1dba-134">由于系统始终会提示添加绑定重定向，因此不需要显式禁用此功能的 web 应用。</span><span class="sxs-lookup"><span data-stu-id="b1dba-134">Because you're always prompted to add binding redirects, you don't need to explicitly disable this feature for a web app.</span></span>

<span data-ttu-id="b1dba-135">若要将绑定重定向添加到 web.config 文件：</span><span class="sxs-lookup"><span data-stu-id="b1dba-135">To add binding redirects to a web.config file:</span></span>

1. <span data-ttu-id="b1dba-136">在 Visual Studio 中，编译应用，然后检查生成警告。</span><span class="sxs-lookup"><span data-stu-id="b1dba-136">In Visual Studio, compile the app, and check for build warnings.</span></span>

   <span data-ttu-id="b1dba-137">![生成程序集引用冲突的警告](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="b1dba-137">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>

2. <span data-ttu-id="b1dba-138">如果存在程序集绑定冲突，则将显示警告。</span><span class="sxs-lookup"><span data-stu-id="b1dba-138">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="b1dba-139">双击该警告，或选择警告，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="b1dba-139">Double-click the warning, or select the warning and press **Enter**.</span></span>

   <span data-ttu-id="b1dba-140">此时将显示一个对话框，使你可以将必要的绑定重定向添加到源 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b1dba-140">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>

   <span data-ttu-id="b1dba-141">![绑定重定向权限对话框](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="b1dba-141">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>

## <a name="see-also"></a><span data-ttu-id="b1dba-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1dba-142">See also</span></span>

- [<span data-ttu-id="b1dba-143">\<bindingRedirect > 元素</span><span class="sxs-lookup"><span data-stu-id="b1dba-143">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="b1dba-144">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="b1dba-144">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
