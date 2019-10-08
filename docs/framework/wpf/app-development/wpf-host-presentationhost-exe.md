---
title: WPF 主机 (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: c1c26b49a33a58189f66e7b938333f362e467853
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002160"
---
# <a name="wpf-host-presentationhostexe"></a>WPF 主机 (PresentationHost.exe)
Windows Presentation Foundation （WPF）宿主（Presentationhost.exe）是一种允许在兼容的浏览器（包括 Microsoft Internet Explorer 6 及更高版本）中承载 @no__t 0 应用程序的应用程序。 默认情况下，Windows Presentation Foundation （WPF）主机注册为浏览器承载的 @no__t 0 内容的 shell 和 MIME 处理程序，其中包括：  
  
- 松散（未编译）[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文件 (.xaml)。  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap)。  
  
 对于这些类型的文件，Windows Presentation Foundation （WPF）主机：  
  
- 启动已注册的 HTML 处理程序以承载 Windows Presentation Foundation （WPF）内容。  
  
- 加载所需的公共语言运行时（CLR）和 Windows Presentation Foundation （WPF）程序集的正确版本。  
  
- 确保部署区域具有适当的权限级别。  
  
 本主题介绍了可以与 PresentationHost.exe 一起使用的命令行参数。  
  
## <a name="usage"></a>用法  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>Parameters  
  
|参数|描述|  
|---------------|-----------------|  
|filename|要激活的文件的路径。 也可以为 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]。|  
|-debug|激活应用程序时，不要从存储中提交或运行它。 此参数仅在激活本地文件时才起作用。|  
|-debugSecurityZoneURL \<url>|与 URL 值一起使用，以指示 Presentationhost.exe 应该调试应用程序，就像它是从指定的 URL 部署的一样。 此参数可确定部署区域和源站点。|  
|-embedding|OLE 的必需参数。 如果已指定 `-event` 或 `-debug` 参数，则无需指定 `-embedding` 参数，因为该参数已在内部设置。|  
|-event \<eventname>|打开具有此名称的事件，并在 PresentationHost.exe 初始化并准备好承载 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 内容时向该事件发出信号。 如果打开事件时发生错误（例如该事件尚未创建），则 PresentationHost.exe 将终止。|  
|-launchApplication \<url>|从指定的 URL 启动独立的 ClickOnce 应用程序。 应用与 .NET 应用程序有关的 Internet Explorer 和 WinINet 安全策略。|  
  
## <a name="scenarios"></a>方案  
  
### <a name="shell-handler"></a>Shell 处理程序  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>MIME 处理程序  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Visual Studio 调试  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>在区域中进行 Visual Studio 调试  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>请参阅

- [安全性](../security-wpf.md)
