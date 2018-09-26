---
title: 如何：启用和禁用自动绑定重定向
ms.date: 09/12/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 9b9c9cbdb89ccf67942dcccee37ea410c6fa39a5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208667"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>如何：启用和禁用自动绑定重定向

当你编译面向 Visual Studio 中的应用[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]和更高版本，绑定重定向可能会自动添加到应用程序配置文件以重写程序集统一。 如果你的应用或其组件引用同一程序集的多个版本，就会添加绑定重定向，即使你在应用的配置文件中手动指定绑定重定向。 自动绑定重定向功能会影响传统桌面应用和 web 应用面向[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]或更高版本中，虽然行为会略有不同的 web 应用。 如果你有面向较早版本 .NET Framework 的现有应用，则可以启用自动绑定重定向，如果要保留手动编写的绑定重定向，你可以将此功能禁用。

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>禁用自动绑定重定向在桌面应用程序

默认情况下，将为面向 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 及更高版本的传统桌面应用启用自动绑定重定向。 编译应用并重写可能发生的程序集统一时，绑定重定向将添加到输出配置 (app.config) 文件中。 不修改源 app.config 文件。 你可以通过修改应用的项目文件来禁用此功能。

1. 打开该项目文件进行编辑使用以下方法之一：

   - 在 Visual Studio 中，选择在项目**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。 在文件资源管理器，找到项目 （.csproj 或.vbproj） 文件，并在记事本中打开它。
   - 在 Visual Studio 中，在**解决方案资源管理器**，右键单击项目，然后选择**卸载项目**。 再次，右键单击已卸载的项目，然后选择**编辑 [项目名.csproj]**。

2. 在项目文件中，查找以下属性项：

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. 将 `true` 更改为 `false`：

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>手动启用自动绑定重定向

你可以面向旧版本的.NET Framework 中，或在其中你会不会自动提示你添加重定向的情况下启用现有应用中的自动绑定重定向。 如果你面向较新版本的 framework 但未自动提示以添加重定向，则可能会建议重新映射程序集的生成输出。

1. 打开该项目文件进行编辑使用以下方法之一：

   - 在 Visual Studio 中，选择在项目**解决方案资源管理器**，然后选择**在文件资源管理器中打开文件夹**从快捷菜单。 在文件资源管理器，找到项目 （.csproj 或.vbproj） 文件，并在记事本中打开它。
   - 在 Visual Studio 中，在**解决方案资源管理器**，右键单击项目，然后选择**卸载项目**。 再次，右键单击已卸载的项目，然后选择**编辑 [项目名.csproj]**。

2. 将以下元素添加到第一个配置属性组 (在\<PropertyGroup > 标记):

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   下面的示例项目文件具有插入元素：

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

3. 编译你的应用。

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>启用 web 应用中的自动绑定重定向

Web 应用的自动绑定重定向实现方式有所不同。 由于必须修改 Web 应用的源配置 (web.config) 文件，因此绑定重定向不会自动添加到配置文件。 但是，Visual Studio 会通知你绑定冲突，你可以添加绑定重定向来解决此冲突。 由于系统始终会提示添加绑定重定向，因此不需要显式禁用此功能的 web 应用。

若要将绑定重定向添加到 web.config 文件：

1. 在 Visual Studio 中，编译应用，然后检查生成警告。

   ![生成程序集引用冲突的警告](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. 如果存在程序集绑定冲突，则将显示警告。 双击该警告，或选择警告，然后按**Enter**。

   此时将显示一个对话框，使你可以将必要的绑定重定向添加到源 web.config 文件。

   ![绑定重定向权限对话框](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>请参阅

- [\<bindingRedirect > 元素](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [重定向程序集版本](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
