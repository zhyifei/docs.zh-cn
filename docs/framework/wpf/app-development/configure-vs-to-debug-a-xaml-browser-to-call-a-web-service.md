---
title: 如何：将 Visual Studio 配置为通过调试 XAML 浏览器应用程序来调用 Web 服务
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: e41dd46e4ddbdcde6448c68b4f9fb2e073baca43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958691"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>如何：将 Visual Studio 配置为通过调试 XAML 浏览器应用程序来调用 Web 服务
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]在仅限 Internet 区域权限集的部分信任的安全沙盒中运行。 此权限集将 web 服务调用限制为仅位于[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]应用程序源站点上的 web 服务。 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]但是, 当从 Visual Studio 2005 调试时, 它不会被视为与其引用的 Web 服务具有相同的源站点。 这会导致在[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]尝试调用 Web 服务时引发安全异常。 但是, 可以将 Visual Studio [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 2005 项目配置为模拟与调试时所调用的 Web 服务具有相同的源站点。 这样, 就可以安全地调用 Web 服务, 而不会导致安全异常。 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]

## <a name="configuring-visual-studio"></a>配置 Visual Studio
 若要将 Visual Studio 2005 配置为[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]调试调用 Web 服务的, 请执行以下操作:

1. 在“解决方案资源管理器”中选择了项目的情况下，在“项目” 菜单上单击“属性”。

2. 在**项目设计器**中, 单击 "**调试**" 选项卡。

3. 在 "**启动操作**" 部分中, 选择 "**启动外部程序**", 并输入以下内容:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. 在 "**启动选项**" 部分, 在 "**命令行参数**" 文本框中输入以下内容:

     `-debug`  *名字*

     **-Debug**参数的*filename*值为 xbap 文件名;例如:

     `-debug c:\example.xbap`

> [!NOTE]
> 这是通过 Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)]项目模板创建的解决方案的默认配置。

1. 在“解决方案资源管理器”中选择了项目的情况下，在“项目” 菜单上单击“属性”。

2. 在**项目设计器**中, 单击 "**调试**" 选项卡。

3. 在 "**启动选项**" 部分, 将以下命令行参数添加到 "**命令行参数**" 文本框中:

     `-debugSecurityZoneURL` URL

     **-DebugSecurityZoneURL**参数的*URL*值是要作为应用[!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)]程序源站点模拟的位置的。

 例如, 请考虑[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]使用 Web 服务的, 其中包含以下[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]内容:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 此 Web 服务的[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]源站点是:

 `http://services.msdn.microsoft.com`

 因此, **debugSecurityZoneURL**命令行参数和值为:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>请参阅

- [WPF 主机 (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
