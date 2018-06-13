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
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>如何：启用和禁用自动绑定重定向
从 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] 开始，当你编译面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 的应用程序时，绑定重定向可能会自动添加到应用配置文件，以便重写程序集统一。 如果你的应用或其组件引用同一程序集的多个版本，就会添加绑定重定向，即使你在应用的配置文件中手动指定绑定重定向。 自动绑定重定向功能会影响面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 的传统桌面应用和 Web 应用，但对于 Web 应用来说，行为略有不同。 如果你有面向较早版本 .NET Framework 的现有应用，则可以启用自动绑定重定向，如果要保留手动编写的绑定重定向，你可以将此功能禁用。  
  
## <a name="disabling-automatic-binding-redirects-in-desktop-apps"></a>在桌面应用中禁用自动绑定重定向  
 默认情况下，将为面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 及更高版本的传统桌面应用启用自动绑定重定向。 编译应用并重写可能发生的程序集统一时，绑定重定向将添加到输出配置 (app.config) 文件中。 不修改源 app.config 文件。 你可以通过修改应用的项目文件来禁用此功能。  
  
#### <a name="to-disable-automatic-binding-redirects"></a>禁用自动绑定重定向  
  
1.  在 Visual Studio 中，选择的项目中**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。  
  
2.  在文件资源管理器中，找到项目（.csproj 或 .vbproj）文件，并用记事本将其打开。  
  
3.  在项目文件中，查找以下属性项：  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
4.  将 `true` 更改为 `false`：  
  
     `<AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>`  
  
## <a name="enabling-automatic-binding-redirects-manually"></a>手动启用自动绑定重定向  
 你可以在面向旧版本 .NET Framework 的现有应用中，或在不会自动提示你添加重定向的情况下，启用自动绑定重定向。 如果你面向较新版本的框架，但没有获得自动提示以添加重定向，你可能会获得建议你重新映射程序集的生成输出。  
  
#### <a name="to-manually-add-an-automatic-binding-redirect-property"></a>手动添加自动绑定重定向属性  
  
1.  在 Visual Studio 中，选择的项目中**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。  
  
2.  在文件资源管理器中，找到项目（.csproj 或 .vbproj）文件，并用记事本将其打开。  
  
3.  将以下元素添加到第一个配置属性组 (下\<PropertyGroup > 标记):  
  
     `<AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>`  
  
     下面显示具有插入元素的示例项目文件。  
  
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
  
4.  编译你的应用。  
  
## <a name="enabling-automatic-binding-redirects-in-web-apps"></a>在 Web 应用中启用自动绑定重定向  
 Web 应用的自动绑定重定向实现方式有所不同。 由于必须修改 Web 应用的源配置 (web.config) 文件，因此绑定重定向不会自动添加到配置文件。 但是，Visual Studio 会通知你绑定冲突，你可以添加绑定重定向来解决此冲突。 由于始终会提示你添加绑定重定向，因此你不需要为 Web 应用显式禁用此功能。  
  
#### <a name="to-add-binding-redirects-to-a-webconfig-file"></a>向 web.config 文件添加绑定重定向  
  
1.  在 Visual Studio 中，编译应用，然后检查生成警告。  
  
     ![生成程序集引用冲突的警告](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")  
  
2.  如果存在程序集绑定冲突，则将显示警告。 双击警告。 (键盘： 选择警告，然后按**Enter**。)  
  
     此时将显示一个对话框，使你可以将必要的绑定重定向添加到源 web.config 文件。  
  
     ![绑定重定向权限对话框](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")  
  
## <a name="see-also"></a>请参阅  
 [\<bindingRedirect > 元素](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [重定向程序集版本](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
