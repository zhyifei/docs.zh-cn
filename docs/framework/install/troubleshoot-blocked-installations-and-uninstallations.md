---
title: "阻止安装和卸载 .NET Framework 疑难解答 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, 阻止安装疑难解答"
  - "阻止安装 .NET Framework, 疑难解答"
ms.assetid: c3fdfbc1-ed99-4202-a2b0-8c4f1646385d
caps.latest.revision: 57
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 39
---
# 阻止安装和卸载 .NET Framework 疑难解答
运行 .NET Framework 4.5、4.5.1、4.5.2、4.6 或 4.6.1 的 [Web 或脱机安装程序](../../../docs/framework/install/guide-for-developers.md)时，你可能会遇到禁止或阻止 .NET Framework 安装的问题。 下表列出了可能产生的阻碍问题，并提供了指向疑难解答信息的链接。  
  
 在此表中，4.5.*x* 指 .NET Framework 4.5 及其后续版本 4.5.1、4.5.2、4.6 或 4.6.1。  
  
|阻止消息|了解更多信息或解决此问题|  
|----------|------------------|  
|卸载 Microsoft .NET Framework 可能会导致某些应用程序无法正常工作。|通常，你不应卸载计算机上安装的 .NET Framework 的任何版本，因为你使用的应用程序可能取决于 .NET Framework 的特定版本。 有关详细信息，请参阅*入门*指南中的[面向用户的 .NET Framework](../../../docs/framework/get-started/index.md#ForUsers)。|  
|.NET Framework 4.5*.x*\/4.6*.x* \(*语言*\) 需要 .NET Framework 4.5*.x*\/4.6*.x*。 请从下载中心安装 .NET Framework 4.5*.x*\/4.6*.x*，然后重新运行安装程序。|你必须先安装 .NET Framework 指定版本的英文版，然后再安装语言包。 有关详细信息，请参阅安装指南中有关[安装语言包](../../../docs/framework/install/guide-for-developers.md#standalone_language_packs)的部分。|  
|无法安装 .NET Framework 4.5*.x*\/4.6*.x*。 你的计算机上的其他应用程序与此程序不兼容。<br /><br /> \- 或 \-<br /><br /> 你的计算机上的其他应用程序与此程序不兼容。|导致出现此消息的最可能的原因是安装了 .NET Framework 的预览版或 RC 版。 卸载预览版或 RC 版，然后重新运行安装程序。|  
|无法使用此程序包卸载 .NET Framework 4.5*.x*\/4.6*.x*。 若要卸载计算机中的 .NET Framework 4.5*.x*\/4.6*.x*，请转到“控制面板”，然后依次选择“程序和功能”、“查看已安装的更新”、“Microsoft Windows \(KB2828152\) 的更新”和“卸载”。|你正在安装的程序包不会卸载 .NET Framework 的预览版或 RC 版。<br /><br /> 从“控制面板”卸载预览版或 RC 版。|  
|无法卸载 .NET Framework 4.5*.x*\/4.6*.x*。 计算机上的其他应用程序依赖于此程序。|通常，你不应该从计算机卸载 .NET Framework 的任何版本，因为你使用的应用程序可能基于 .NET Framework 的特定版本。 有关详细信息，请参阅*入门*指南中的[面向用户的 .NET Framework](../../../docs/framework/get-started/index.md#ForUsers)。|  
|.NET Framework 4.5*.x*\/4.6*.x* 可再发行组件不适用于此操作系统。 请从 Microsoft 下载中心下载适合你的操作系统的 .NET Framework 4.5*.x*\/4.6*.x*。|你可能尝试在不受支持的平台上安装 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]、4.5.2、4.6 或 4.6.1，或者你已选择不包含适用于所支持全部操作系统的组件的安装程序包。 通过使用脱机安装程序（[用于 4.5.1](http://go.microsoft.com/fwlink/p/?LinkId=309493)、[用于 4.5.2](http://go.microsoft.com/fwlink/p/?LinkId=397706)、[用于 4.6](http://go.microsoft.com/fwlink/p/?LinkId=528233) 或 [用于 4.6.1](http://go.microsoft.com/fwlink/p/?LinkId=671744)）再次运行安装。 有关详细信息，请参见适用于支持的操作系统的[安装指南](../../../docs/framework/install/guide-for-developers.md)和[系统要求](../../../docs/framework/get-started/system-requirements.md)。|  
|你的计算机当前正在运行 Windows Server 2008 操作系统的服务器核心安装。 .NET Framework 4.5.*x* 需要操作系统的更高版本。 请安装 Windows Server 2008 R2 SP1 或更高版本并重新运行 .NET Framework 4.5.*x* 安装程序。|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 和 4.5.2 在带有 Windows Server 2008 R2 SP1 或更高版本的服务器核心角色中受支持。 请参阅 [系统需求](../../../docs/framework/get-started/system-requirements.md)。|  
|你没有足够的权限为此计算机的所有用户完成此操作。 以管理员身份登录，然后重新运行**“安装程序”**。|若要安装 .NET Framework，你必须是计算机的管理员。|  
|前一次安装要求重新启动计算机，所以安装程序无法继续。 请重新启动计算机，然后重新运行安装程序。|有时需要重新启动以完全完成一次安装。 根据说明重新启动计算机并重新运行安装程序。|  
|此计算机上已安装 .NET Framework 4.5*.x*\/4.6*.x* \(简体中文\) 或更高版本的更新。|无需执行任何操作。|  
|.NET Framework 安装程序无法在程序兼容性模式下运行。|请参阅本文后面的[程序兼容性问题](#compat)一节。|  
|.NET Framework 4.5*.x*\/4.6*.x* 未安装，因为组件存储已损坏。|有关详细信息，请参阅[使用 DISM 或 System Update Readiness 工具修复 Windows Update 错误](https://support.microsoft.com/en-us/kb/947821)。|  
|安装程序无法运行，因为 Windows Installer 服务在此计算机上不可用。|请参阅 Microsoft 支持网站上的[安装或更新程序时出现的 Windows Installer 服务错误](http://go.microsoft.com/fwlink/p/?LinkId=248684)。|  
|安装程序可能无法正常运行，因为 Windows Update 服务在此计算机上不可用。|可将计算机配置为使用 Windows Server Update Services \(WSUS\) 而非 Microsoft Windows Update。 有关详细信息，请参阅[尝试在 Windows 8 或 Windows Server 2012 上安装 .NET Framework 3.5 时出现的错误代码](http://support.microsoft.com/kb/2734782)中有关错误代码 0x800F0906 的部分。<br /><br /> 另请参阅 Microsoft 支持网站上的[如何获取 Windows Update 代理的最新版本以帮助管理计算机上的更新](http://go.microsoft.com/fwlink/p/?LinkId=248437)。|  
|安装程序可能无法正常运行，因为后台智能传输服务 \(BITS\) 在此计算机上不可用。|请参阅 Microsoft 支持网站上的[用于防止 Windows Vista 计算机上的后台智能传输服务 \(BITS\) 发生崩溃的更新](http://go.microsoft.com/fwlink/p/?LinkId=248680)。|  
|.NET Framework 4.5.*.x*\/4.6 已是此操作系统的一部分。 你无需安装 .NET Framework 4.5*.x*\/4.6 可再发行组件。|不执行任何操作。 有关受支持的操作系统，请参阅 [系统需求](../../../docs/framework/get-started/system-requirements.md)。|  
|.NET Framework 4.5*.x*\/4.6*.x* 在此操作系统上不受支持。|有关受支持的操作系统，请参阅 [系统需求](../../../docs/framework/get-started/system-requirements.md)。<br /><br /> Windows 7 上安装 .NET Framework 失败时，此消息通常会指示未安装 Windows 7 SP1。 在 Windows 7 系统上，.NET Framework 要求安装 Windows 7 SP1。 如果你使用的是 Windows 7 系统，但尚未安装 Service Pack 1，则需要先安装 SP1，然后才能安装 .NET Framework。|  
|你的计算机当前正在运行 Windows Server 2008 操作系统的服务器核心安装。 .NET Framework 4.5.*x* 需要操作系统或 Server Core 2008 R2 SP1 的完整版本。 请安装完整版的 Windows Server 2008 SP2 或 Windows Server 2008 R2 SP1 或者 Server Core 2008 R2 SP1，然后重新运行 .NET Framework 4.5.*x* 安装程序。|.NET Framework 在带有 Windows Server 2008 R2 SP1 或更高版本的服务器核心角色中受支持。 请参阅 [系统需求](../../../docs/framework/get-started/system-requirements.md)。|  
|.NET Framework 4.5.*x* 已是此操作系统的一部分，但当前已将其关闭（仅限 [!INCLUDE[winserver8](../../../includes/winserver8-md.md)]）。|请参阅 Windows 网站上的[启用或禁用 Windows 功能](http://go.microsoft.com/fwlink/p/?LinkId=248438)。|  
|此安装程序要求使用 x86 计算机。 不能在 x64 或 IA64 计算机上安装此程序。|请参见 MSDN 库中的[系统需求](../../../docs/framework/get-started/system-requirements.md)。|  
|此安装程序要求使用 x64 或 x86 计算机。 不能在 IA64 计算机上安装此程序。|请参见 MSDN 库中的[系统需求](../../../docs/framework/get-started/system-requirements.md)。|  
  
<a name="compat"></a>   
### 程序兼容性问题  
 .NET Framework 4.5 及其单点版本的安装失败并显示 1603 错误，或在 Windows 程序兼容性模式下运行时受到阻止。**“程序兼容性助手”**指示可能未正确安装 .NET Framework，并提示你使用建议的设置（程序兼容性模式）重新安装它。 以前，在运行 .NET Framework 安装程序失败或取消尝试时，程序兼容性模式还可能已由“程序兼容性助手”进行了设置。  
  
 .NET Framework 安装程序无法在程序兼容性模式下运行。 若要解决此阻碍问题，你必须确保未在注册表编辑器的系统范围内启用兼容性模式设置：  
  
1.  选择**“开始”**按钮，然后选择**“运行”**。  
  
2.  在“运行”对话框中，键入 `regedit`，然后选择“确定”。  
  
3.  在注册表编辑器中，浏览到以下子项：  
  
    -   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Compatibility Assistant\\Persisted  
  
    -   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers  
  
4.  在“名称”列中，查找 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]、4.5.1、4.5.2、4.6 或 4.6.1 下载名称（具体取决于要安装的版本），然后删除这些条目。 有关下载名称，请参阅[安装指南](../../../docs/framework/install/guide-for-developers.md) 一文。  
  
5.  重新运行版本 4.5、4.5.1、4.5.2、4.6 或 4.6.1 的 .NET Framework 安装程序。  
  
## 请参阅  
 [安装指南](../../../docs/framework/install/guide-for-developers.md)