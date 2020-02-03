---
title: 检测是否已安装 Firefox 的 WPF 插件
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 91680859c1742e5d5443d626c81273a80504f4a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740399"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="926b6-102">如何：检测是否已安装 Firefox 的 WPF 插件</span><span class="sxs-lookup"><span data-stu-id="926b6-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="926b6-103">用于 Firefox 的 Windows Presentation Foundation （WPF）插件使得 XAML 浏览器应用程序（Xbap）和松散 XAML 文件可在 Mozilla Firefox 浏览器中运行。</span><span class="sxs-lookup"><span data-stu-id="926b6-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables XAML browser applications (XBAPs) and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="926b6-104">本主题提供以 HTML 和 JavaScript 编写的脚本，管理员可以使用该脚本来确定是否安装了 Firefox 的 WPF 插件。</span><span class="sxs-lookup"><span data-stu-id="926b6-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="926b6-105">有关安装、部署和检测 .NET Framework 的详细信息，请参阅[为开发人员安装 .NET Framework](../../install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="926b6-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="926b6-106">示例</span><span class="sxs-lookup"><span data-stu-id="926b6-106">Example</span></span>

<span data-ttu-id="926b6-107">安装 .NET Framework 3.5 后，将使用用于 Firefox 的 WPF 插件配置客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="926b6-107">When the .NET Framework 3.5 is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="926b6-108">下面的示例脚本检查 Firefox 的 WPF 插件，并显示相应的状态消息。</span><span class="sxs-lookup"><span data-stu-id="926b6-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

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

<span data-ttu-id="926b6-109">如果 Firefox 的 WPF 插件的检查成功，则会显示以下状态消息：</span><span class="sxs-lookup"><span data-stu-id="926b6-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="926b6-110">否则，将显示以下状态消息：</span><span class="sxs-lookup"><span data-stu-id="926b6-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="926b6-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="926b6-111">See also</span></span>

- [<span data-ttu-id="926b6-112">检测是否安装了 .NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="926b6-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="926b6-113">检测是否安装了 .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="926b6-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- <span data-ttu-id="926b6-114">[WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md)（WPF XAML 浏览器应用程序概述）</span><span class="sxs-lookup"><span data-stu-id="926b6-114">[WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md)</span></span>
