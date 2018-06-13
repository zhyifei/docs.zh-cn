---
title: 如何：启用和禁用自动绑定重定向
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2d71da1b48938f9f98221d86f0f9badee3a17919
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757562"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a><span data-ttu-id="cccf6-102">如何：启用和禁用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="cccf6-102">How to: Enable and Disable Automatic Binding Redirection</span></span>
<span data-ttu-id="cccf6-103">从 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] 开始，当你编译面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 的应用程序时，绑定重定向可能会自动添加到应用配置文件，以便重写程序集统一。</span><span class="sxs-lookup"><span data-stu-id="cccf6-103">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], when you compile apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], binding redirects may be automatically added to the app configuration file to override assembly unification.</span></span> <span data-ttu-id="cccf6-104">如果你的应用或其组件引用同一程序集的多个版本，就会添加绑定重定向，即使你在应用的配置文件中手动指定绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="cccf6-104">Binding redirects are added if your app or its components reference more than one version of the same assembly, even if you manually specify binding redirects in the configuration file for your app.</span></span> <span data-ttu-id="cccf6-105">自动绑定重定向功能会影响面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 的传统桌面应用和 Web 应用，但对于 Web 应用来说，行为略有不同。</span><span class="sxs-lookup"><span data-stu-id="cccf6-105">The automatic binding redirection feature affects traditional desktop apps and web apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], although the behavior is slightly different for a web app.</span></span> <span data-ttu-id="cccf6-106">如果你有面向较早版本 .NET Framework 的现有应用，则可以启用自动绑定重定向，如果要保留手动编写的绑定重定向，你可以将此功能禁用。</span><span class="sxs-lookup"><span data-stu-id="cccf6-106">You can enable automatic binding redirection if you have existing apps that target previous versions of the .NET Framework, or you can disable this feature if you want to keep manually authored binding redirects.</span></span>  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a><span data-ttu-id="cccf6-107">在桌面应用中禁用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="cccf6-107">Disabling automatic binding redirects in desktop apps</span></span>  
 <span data-ttu-id="cccf6-108">默认情况下，将为面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 及更高版本的传统桌面应用启用自动绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="cccf6-108">Automatic binding redirects are enabled by default for traditional desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] and later versions.</span></span> <span data-ttu-id="cccf6-109">编译应用并重写可能发生的程序集统一时，绑定重定向将添加到输出配置 (app.config) 文件中。</span><span class="sxs-lookup"><span data-stu-id="cccf6-109">The binding redirects are added to the output configuration (app.config) file when the app is compiled and overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="cccf6-110">不修改源 app.config 文件。</span><span class="sxs-lookup"><span data-stu-id="cccf6-110">The source app.config file is not modified.</span></span> <span data-ttu-id="cccf6-111">你可以通过修改应用的项目文件来禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="cccf6-111">You can disable this feature by modifying the project file for the app.</span></span>  
  
#### <a name="to-disable-automatic-binding-redirects"></a><span data-ttu-id="cccf6-112">禁用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="cccf6-112">To disable automatic binding redirects</span></span>  
  
1.  <span data-ttu-id="cccf6-113">在 Visual Studio 中，选择的项目中**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="cccf6-113">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="cccf6-114">在文件资源管理器中，找到项目（.csproj 或 .vbproj）文件，并用记事本将其打开。</span><span class="sxs-lookup"><span data-stu-id="cccf6-114">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="cccf6-115">在项目文件中，查找以下属性项：</span><span class="sxs-lookup"><span data-stu-id="cccf6-115">In the project file, find the following property entry:</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  <span data-ttu-id="cccf6-116">将 `true` 更改为 `false`：</span><span class="sxs-lookup"><span data-stu-id="cccf6-116">Change `true` to `false`:</span></span>  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a><span data-ttu-id="cccf6-117">手动启用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="cccf6-117">Enabling automatic binding redirects manually</span></span>  
 <span data-ttu-id="cccf6-118">你可以在面向旧版本 .NET Framework 的现有应用中，或在不会自动提示你添加重定向的情况下，启用自动绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="cccf6-118">You can enable automatic binding redirects in existing apps that target older versions of the .NET Framework, or in cases where you are not automatically prompted to add a redirect.</span></span> <span data-ttu-id="cccf6-119">如果你面向较新版本的框架，但没有获得自动提示以添加重定向，你可能会获得建议你重新映射程序集的生成输出。</span><span class="sxs-lookup"><span data-stu-id="cccf6-119">If you are targeting a newer version of the framework but do not get automatically prompted to add a redirect, you will likely get   build output that suggests you remap assemblies.</span></span>  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a><span data-ttu-id="cccf6-120">手动添加自动绑定重定向属性</span><span class="sxs-lookup"><span data-stu-id="cccf6-120">To manually add an automatic binding redirect property</span></span>  
  
1.  <span data-ttu-id="cccf6-121">在 Visual Studio 中，选择的项目中**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="cccf6-121">In Visual Studio, select the project in **Solution Explorer**, and then choose **Open Folder in File Explorer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="cccf6-122">在文件资源管理器中，找到项目（.csproj 或 .vbproj）文件，并用记事本将其打开。</span><span class="sxs-lookup"><span data-stu-id="cccf6-122">In File Explorer, find the project (.csproj or .vbproj) file, and open it in Notepad.</span></span>  
  
3.  <span data-ttu-id="cccf6-123">将以下元素添加到第一个配置属性组 (下\<PropertyGroup > 标记):</span><span class="sxs-lookup"><span data-stu-id="cccf6-123">Add the following element to the first configuration property group (under the \<PropertyGroup> tag):</span></span>  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     <span data-ttu-id="cccf6-124">下面显示具有插入元素的示例项目文件。</span><span class="sxs-lookup"><span data-stu-id="cccf6-124">The following shows an example project file with the element inserted.</span></span>  
  
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
  
4.  <span data-ttu-id="cccf6-125">编译你的应用。</span><span class="sxs-lookup"><span data-stu-id="cccf6-125">Compile your app.</span></span>  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a><span data-ttu-id="cccf6-126">在 Web 应用中启用自动绑定重定向</span><span class="sxs-lookup"><span data-stu-id="cccf6-126">Enabling automatic binding redirects in web apps</span></span>  
 <span data-ttu-id="cccf6-127">Web 应用的自动绑定重定向实现方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="cccf6-127">Automatic binding redirects are implemented differently for web apps.</span></span> <span data-ttu-id="cccf6-128">由于必须修改 Web 应用的源配置 (web.config) 文件，因此绑定重定向不会自动添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="cccf6-128">Because the source configuration (web.config) file must be modified for web apps, binding redirects are not automatically added to the configuration file.</span></span> <span data-ttu-id="cccf6-129">但是，Visual Studio 会通知你绑定冲突，你可以添加绑定重定向来解决此冲突。</span><span class="sxs-lookup"><span data-stu-id="cccf6-129">However, Visual Studio notifies you of binding conflicts, and you can add binding redirects to resolve the conflicts.</span></span> <span data-ttu-id="cccf6-130">由于始终会提示你添加绑定重定向，因此你不需要为 Web 应用显式禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="cccf6-130">Because you are always prompted to add binding redirects, you do not need to explicitly disable this feature for a web app.</span></span>  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a><span data-ttu-id="cccf6-131">向 web.config 文件添加绑定重定向</span><span class="sxs-lookup"><span data-stu-id="cccf6-131">To add binding redirects to a web.config file</span></span>  
  
1.  <span data-ttu-id="cccf6-132">在 Visual Studio 中，编译应用，然后检查生成警告。</span><span class="sxs-lookup"><span data-stu-id="cccf6-132">In Visual Studio, compile the app, and check for build warnings.</span></span>  
  
     <span data-ttu-id="cccf6-133">![生成程序集引用冲突的警告](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span><span class="sxs-lookup"><span data-stu-id="cccf6-133">![Build warning for assembly reference conflicts](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")</span></span>  
  
2.  <span data-ttu-id="cccf6-134">如果存在程序集绑定冲突，则将显示警告。</span><span class="sxs-lookup"><span data-stu-id="cccf6-134">If there are assembly binding conflicts, a warning appears.</span></span> <span data-ttu-id="cccf6-135">双击警告。</span><span class="sxs-lookup"><span data-stu-id="cccf6-135">Double-click the warning.</span></span> <span data-ttu-id="cccf6-136">(键盘： 选择警告，然后按**Enter**。)</span><span class="sxs-lookup"><span data-stu-id="cccf6-136">(Keyboard: Select the warning and press **Enter**.)</span></span>  
  
     <span data-ttu-id="cccf6-137">此时将显示一个对话框，使你可以将必要的绑定重定向添加到源 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="cccf6-137">A dialog box that enables you to automatically add the necessary binding redirects to the source web.config file appears.</span></span>  
  
     <span data-ttu-id="cccf6-138">![绑定重定向权限对话框](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span><span class="sxs-lookup"><span data-stu-id="cccf6-138">![Binding redirect permission dialog](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccf6-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="cccf6-139">See Also</span></span>  
 [<span data-ttu-id="cccf6-140">\<bindingRedirect > 元素</span><span class="sxs-lookup"><span data-stu-id="cccf6-140">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="cccf6-141">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="cccf6-141">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
