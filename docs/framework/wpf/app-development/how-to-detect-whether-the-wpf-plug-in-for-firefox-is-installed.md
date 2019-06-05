---
title: 如何：检测是否安装了适用于 Firefox 的 WPF 插件
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: f84a0a2af43931b3ada1f674390ec5d841b79a1c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690431"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>如何：检测是否安装了适用于 Firefox 的 WPF 插件

Windows Presentation Foundation (WPF) Firefox 的插件使[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]和松散 XAML 文件 Mozilla Firefox 浏览器中运行。 本主题提供了用 HTML 和 JavaScript，管理员可以用于确定是否已安装 Firefox 的插件的 WPF 编写的脚本。

> [!NOTE]
> 有关安装的详细信息，部署和检测.NET Framework，请参阅[安装面向开发人员的.NET Framework](../../install/guide-for-developers.md)。

## <a name="example"></a>示例

安装.NET Framework 3.5 时，客户端计算机配置与 WPF 插件 firefox。 以下示例脚本检查 firefox 的 WPF 插件，然后显示相应的状态消息。

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

如果 Firefox 的 wpf 插件检查成功，显示以下状态消息：

`The WPF plug-in for Firefox is installed.`

否则，会显示以下状态消息：

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>请参阅

- [检测是否安装了 .NET Framework 3.0](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [检测是否安装了 .NET Framework 3.5](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md)（WPF XAML 浏览器应用程序概述）
