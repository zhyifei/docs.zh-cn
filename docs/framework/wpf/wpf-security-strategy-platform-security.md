---
title: 平台安全策略
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform security model [WPF]
- Common Language Runtime (CLR) security features
- operating system security model [WPF]
- Internet Explorer security features [WPF]
- Security-Critical method
- CLR security features [WPF]
- security model [WPF]
- security model [WPF], platform
- WPF [WPF], about security model
- Windows Presentation Foundation [WPF], about security model
- security model [WPF], operating system
ms.assetid: 2a39a054-3e2a-4659-bcb7-8bcea490ba31
ms.openlocfilehash: 258fcd7c51ea59de03fe60a4eeb9a82dd1c7efca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174597"
---
# <a name="wpf-security-strategy---platform-security"></a>WPF 安全策略 - 平台安全性
虽然 Windows 演示基础 （WPF） 提供各种安全服务，但它也利用了底层平台的安全功能，其中包括操作系统、CLR 和 Internet 资源管理器。 这些层组合为 WPF 提供强大的纵深防御安全模型，可尝试避免任何单点故障，如下图所示：  
  
 ![显示 WPF 安全模型的图表。](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 本主题的其余部分将讨论每个层中专门与 WPF 相关的功能。  

## <a name="operating-system-security"></a>操作系统安全性  
Windows 的核心提供了几个安全功能，这些功能构成了所有 Windows 应用程序的安全基础，包括使用 WPF 构建的应用程序。 本主题讨论这些对 WPF 重要的安全功能的广度，以及 WPF 如何与这些功能集成以提供更深入的防御。  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 除了对 Windows 的一般回顾和加强外，本主题中还将讨论 Windows XP SP2 中的三个关键功能：  
  
- /GS 编译  
  
- 微软视窗更新。  
  
#### <a name="gs-compilation"></a>/GS 编译  
 Windows XP SP2 通过重新编译许多核心系统库（包括 CLR 等所有 WPF 依赖项）来提供保护，以帮助缓解缓冲区溢出。 通过使用/GS 形参和 C/C++ 命令行编译器可实现这一点。 虽然应显式避免缓冲区溢出，但 /GS 编译针对由它们无意或恶意创建的潜在漏洞提供了深层防御示例。  
  
 以前，缓冲区溢出已导致出现了许多影响较大的安全漏洞。 当攻击者利用代码漏洞时就会发生缓冲区溢出，代码漏洞可让注入的恶意代码通过缓冲区边界写入。 从而让攻击者可以通过重写导致执行攻击者代码的函数返回地址执行代码进程。 结果，恶意代码可以执行具有截获进程相同特权的任意代码。  
  
 在高级别上，-GS 编译器标志通过注入特殊安全 Cookie 来保护具有本地字符串缓冲区的函数的返回地址，从而防止某些潜在的缓冲区溢出。 函数返回后，安全 cookie 将与其上一个值进行比较。 如果值已更改，可能已发生缓冲区溢出，并且该进程已停止并显示错误条件。 停止的进程将阻止执行潜在的恶意代码。 有关详细信息，请参阅[-GS（缓冲区安全检查）。](/cpp/build/reference/gs-buffer-security-check)  
  
 WPF 使用 /GS 标志编译，以便为 WPF 应用程序添加另一层防御。  
  
### <a name="windows-vista"></a>Windows Vista  
Windows Vista 上的 WPF 用户将受益于操作系统的其他安全增强功能，包括"最低权限用户访问"、代码完整性检查和权限隔离。  
  
#### <a name="user-account-control-uac"></a>用户帐户控制 (UAC)  
 如今，Windows 用户倾向于使用管理员权限运行，因为许多应用程序需要安装或执行，或者两者兼而有之。 其中一个示例就是，可以将默认应用程序设置写入到注册表。  
  
 使用管理员特权运行实际上就是指应用程序从授予管理员特权的进程执行。 此方法的安全影响在于，可截获使用管理员特权运行的进程的任何恶意代码都将自动继承这些特权，包括对关键系统资源的访问权限。  
  
 保护计算机免受此安全威胁的一种方法就是使用所需的最少特权数运行应用程序。 这称为最小特权原则，是 Windows 操作系统的核心功能。 此功能称为用户帐户控制 （UAC），Windows UAC 以两种关键方式使用：  
  
- 若要在默认情况下使用 UAC 特权运行大多数应用程序，即使用户是管理员，也只有需要使用管理员特权的应用程序才会使用管理员特权运行。 要使用管理特权运行，必须以应用程序清单形式或作为安全策略中的一个条目显式标记应用程序。  
  
- 提供兼容性解决方案(如虚拟化)。 例如，许多应用程序尝试写入受限位置，例如 C:\Program Files。 对于在 UAC 中执行的应用程序，存在基于用户的可选位置无需管理员特权就能写入。 对于在 UAC 中运行的应用程序，UAC 可虚拟化 C:\Program Files，这样认为其写入到其中的应用程序实际上是写入到基于用户的可选位置。 这种兼容性工作可使操作系统来运行许多以前无法在 UAC 中运行的应用程序。  
  
#### <a name="code-integrity-checks"></a>代码完整性检查  
 Windows Vista 集成了更深入的代码完整性检查，以帮助防止恶意代码在加载/运行时注入到系统文件或内核中。 这超出了系统文件保护。  

### <a name="limited-rights-process-for-browser-hosted-applications"></a>浏览器承载的应用程序的受限权限进程  
 浏览器托管的 WPF 应用程序在 Internet 区域沙盒中执行。 WPF 与 Microsoft IExplorer 的集成提供了额外的支持，扩展了此保护。  
  
 由于 XAML 浏览器应用程序 （XBAPs） 通常由 Internet 区域权限集进行沙盒处理，因此从兼容性角度删除这些特权不会损害 XAML 浏览器应用程序 （XBAPs）。 反而会创建一个附加的深层防御层；如果经过沙箱处理的应用程序能够利用其他层截获此进程，该进程将仍然只有有限特权。  
  
 请参阅[使用最低权限的用户帐户](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29)。  
  
## <a name="common-language-runtime-security"></a>公共语言运行时的安全性  
 通用语言运行时 （CLR） 提供了许多关键安全优势，包括验证和验证、代码访问安全 （CAS） 和安全关键方法。  

### <a name="validation-and-verification"></a>确认和验证  
 为了提供程序集隔离和完整性，CLR 使用验证过程。 CLR 验证通过验证程序集的可移植可执行 （PE） 文件格式来验证在程序集外部点的地址，从而隔离程序集。 CLR 验证还验证嵌入在程序集中的元数据的完整性。  
  
 为了确保类型安全，有助于防止常见的安全问题（例如缓冲区溢出），并通过子进程隔离启用沙盒，CLR 安全部门使用验证概念。  
  
 托管应用程序被编译为 Microsoft 中间语言 (MSIL)。 当执行托管应用程序中的方法时，将采用实时 (JIT) 编译方式把 MSIL 编译为本机代码。 JIT 编译包括的验证过程将应用许多众多安全和可靠规则，从而确保代码不会：  
  
- 违反类型合约  
  
- 引入缓冲区溢出  
  
- 随意访问内存。  
  
 不允许不符合验证规则的托管代码执行，除非它被视为受信任代码。  
  
 可验证代码的优点是 WPF 在 .NET 框架上构建的一个关键原因。 从使用验证代码而言，利用潜在漏洞的可能性明显降低。  
  
### <a name="code-access-security"></a>代码访问安全性  
 客户端计算机公开了托管应用程序可以访问的各种资源，包括文件系统、注册表、打印服务、用户界面、反射和环境变量。 在托管应用程序可以访问客户端计算机上的任何资源之前，它必须具有 .NET Framework 权限才能执行此操作。 CAS 中的权限是 中的<xref:System.Security.CodeAccessPermission>子类。CAS 为托管应用程序可以访问的每个资源实现一个子类。  
  
 托管应用程序开始执行时授予的一组权限称为权限集，由应用程序提供的证据确定。 对于 WPF 应用程序，提供的证据是启动应用程序的位置或区域。 CAS 标识以下区域：  
  
- **我的电脑**。 从客户端计算机（完全受信任）上启动的应用程序。  
  
- **本地 Intranet**。 从 Intranet 启动的应用程序。 （某种程度上受信任）。  
  
- **互联网**. 从 Intranet 启动的应用程序。 （最不受信任）。  
  
- **受信任的站点**。 由受信任用户标识的应用程序。 （最不受信任）。  
  
- **不受信任的站点**。 由不受信任的用户标识的应用程序。 （不受信任）。  
  
 对于每个区域，CAS 提供了一个预定义的权限集，其中包含与每个区域关联的信任级别相匹配的权限。 其中包括：  
  
- **FullTrust**。 对于从 **"我的计算机"** 区域启动的应用程序。 将授予全部可能的权限。  
  
- **本地内联网**。 适用于从**本地 Intranet**区域启动的应用程序。 将授予权限的子集，以提供对客户端计算机资源适度的访问权限，包括隔离存储、用户界面的无限制访问、无限制使用文件对话框、有限的反射和有限访问环境变量。 不提供对关键资源（如注册表）的权限。  
  
- **互联网**. 适用于从**Internet**或**受信任的站点**区域启动的应用程序。 将授予权限的子集，以提供对客户端计算机资源有限的访问权限，包括隔离存储、仅限打开文件和有限的用户界面。 从本质上讲，此权限集将应用程序与客户端计算机隔离。  
  
 CAS 不会授予来自**不受信任的站点**区域的应用程序。 因此，对它们而言，就不存在预定义的权限集。  
  
 下图说明了区域、权限集、权限和资源之间的关系：  
  
 ![显示 CAS 权限集的图表。](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Internet 区域安全沙盒的限制同样适用于 XBAP 从系统库中导入的任何代码，包括 WPF。 这可确保锁定代码的每个位，甚至 WPF。 遗憾的是，为了能够执行，XBAP 需要执行比 Internet 区域安全沙盒启用的权限更多的功能。  
  
 请考虑包含以下页面的 XBAP 应用程序：  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 要执行此 XBAP，基础 WPF 代码必须执行比调用 XBAP 可用的功能更多的功能，包括：  
  
- 创建用于渲染的窗口句柄 （HWND）  
  
- 调度消息  
  
- 加载 Tahoma 字体  
  
 从安全角度而言，允许从沙盒应用程序直接访问上述任何操作将会导致灾难性后果。  
  
 幸运的是，WPF 允许这些操作代表沙盒应用程序以提升的权限执行，从而满足这种情况。 虽然所有 WPF 操作都针对 XBAP 应用程序域的应用程序域的有限 Internet 区域安全权限进行检查，但 WPF（与其他系统库一样）被授予包含所有可能权限的权限集。
  
 这要求 WPF 接收提升的权限，同时防止这些特权受主机应用程序域的 Internet 区域权限集控制。  
  
 WPF 使用权限的**Assert**方法来这样做。 以下代码演示了这种方法。  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 **断言**基本上可以防止 WPF 所需的无限权限受到 XBAP 的 Internet 区域权限的限制。  
  
 从平台的角度来看，WPF 负责正确使用**Assert;** 对**Assert**的不正确使用可能会使恶意代码提升特权。 因此，重要的是，只有在需要时调用**Assert，** 并确保沙盒限制保持不变。 例如，禁止沙盒代码打开任意文件，但允许其使用字体。 WPF 使沙盒应用程序能够使用字体功能，通过调用**Assert**， 并使 WPF 能够读取已知代表沙盒应用程序包含这些字体的文件。  
  
### <a name="clickonce-deployment"></a>ClickOnce 部署  
 ClickOnce 是一种全面的部署技术，包含在 .NET 框架中，并与 Visual Studio 集成（有关详细信息，请参阅[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)）。 可以使用 ClickOnce 部署独立 WPF 应用程序，而浏览器托管的应用程序必须使用 ClickOnce 部署。  
  
 使用 ClickOnce 部署的应用程序在代码访问安全性 （CAS） 上获得了额外的安全层;实质上，ClickOnce部署的应用程序请求他们需要的权限。 如果它们不超过在其中部署应用程序的区域的权限集，几乎仅授予它们这些权限。 通过将权限集减少到仅需要的权限集（即使的权限小于启动区域的权限集提供的权限），应用程序有权访问的资源数量将减少到最低限度。 因此，如果截获到应用程序，将可以降低对客户端计算机的潜在损坏几率。  
  
### <a name="security-critical-methodology"></a>安全-关键方法  
 使用权限为 XBAP 应用程序启用 Internet 区域沙盒的 WPF 代码必须保持到最高程度的安全审核和控制。 为了方便此要求，.NET Framework 为管理提升特权的代码提供了新的支持。 具体而言，CLR 使您能够标识提升特权的代码，并将其标记为<xref:System.Security.SecurityCriticalAttribute>。使用此方法，任何未<xref:System.Security.SecurityCriticalAttribute>标记的代码都变得*透明*。 反之，禁止未标有 <xref:System.Security.SecurityCriticalAttribute> 的托管代码提升特权。  
  
 安全关键方法允许组织 WPF 代码，将特权提升到*安全关键型内核*，其余部分是透明的。 隔离安全关键代码使 WPF 工程团队能够将额外的安全分析和源代码控制重点放在标准安全实践之外的安全关键内核上（请参阅[WPF 安全策略 - 安全工程](wpf-security-strategy-security-engineering.md)）。  
  
 请注意，.NET Framework 允许受信任的代码通过允许开发人员编写标记为<xref:System.Security.AllowPartiallyTrustedCallersAttribute>（APTCA） 并部署到用户的全局程序集缓存 （GAC） 的托管程序集来扩展 XBAP Internet 区域沙盒。 将程序集标记为 APTCA 是高度敏感的安全操作，因为它允许任何代码调用该程序集，包括来自 Internet 的恶意代码。 执行此操作时，要特别注意并且必须采用最佳做法，用户必须选择信任该软件才能完成安装。  
  
## <a name="microsoft-internet-explorer-security"></a>Microsoft Internet Explorer 安全  
 除了减少安全问题和简化安全配置外，Microsoft IEE 6 （SP2） 还包含几个安全改进功能，这些功能增强了 XAML 浏览器应用程序 （XBAPs） 用户的安全性。 这些功能的主旨是尝试允许用户更好地控制它们的浏览体验。  
  
 在 IE6 SP2 之前，用户可能受以下任何情况的约束：  
  
- 随机弹出窗口。  
  
- 混淆的脚本重定向。  
  
- 某些网站上出现大量安全对话框。  
  
 在某些情况下，不可信的网站会尝试欺骗安装[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]或重复显示 Microsoft ActiveX 安装对话框来欺骗用户，即使用户可能已取消该对话框。 使用这些技术，有可能会有相当多的用户上当受骗，从而导致安装间谍软件应用程序。  
  
 IE6 SP2 包括几个功能来缓解这些类型的问题，这些功能围绕用户启动的概念展开。 IE6 SP2 检测用户在操作之前单击链接或页面元素（称为*用户启动*）时，它对待它的方式与页面上的脚本触发类似操作时不同。 例如，IE6 SP2 集成了一个**弹出窗口阻止程序**，用于检测用户在创建弹出窗口的页面之前单击按钮时。 这使得 IE6 SP2 能够允许大多数无害的弹出窗口，同时防止用户既不要求也不想要的弹出窗口。 阻止的弹出窗口被捕获到新的**信息栏**下，它允许用户手动覆盖该块并查看弹出窗口。  
  
 相同的用户启动逻辑也适用于**打开**/**保存**安全提示。 ActiveX 安装对话框始终受困在信息栏下，除非它们表示从以前安装的控件升级。 这些度量值组合在一起，可提供用户更安全、更可控的用户体验，因为诱导他们安装不需要的软件或恶意软件的站点受到了保护。  
  
 这些功能还保护使用 IE6 SP2 浏览到允许他们下载和安装 WPF 应用程序的网站的客户。 特别是，这是因为 IE6 SP2 提供了更好的用户体验，减少了用户安装恶意或狡猾应用程序的机会，而不管使用何种技术来构建它，包括 WPF。 WPF 通过使用 ClickOnce 来简化这些保护，以方便通过互联网下载其应用程序。 由于 XAML 浏览器应用程序 （XBAPs） 在 Internet 区域安全沙盒中执行，因此可以无缝启动它们。 另一方面，独立 WPF 应用程序需要完全信任才能执行。 对于这些应用程序，ClickOnce 将在启动过程中显示一个安全对话框，以通知应用程序的其他安全要求。 但是，必须由用户启动，必须由用户启动的逻辑进行管理并且可以取消。  
  
 Internet Explorer 7 整合并扩展了 IE6 SP2 的安全功能，作为持续致力于安全性的一部分。  
  
## <a name="see-also"></a>另请参阅

- [代码访问安全性](../misc/code-access-security.md)
- [安全性](security-wpf.md)
- [WPF 部分信任安全](wpf-partial-trust-security.md)
- [WPF 安全策略 - 安全工程](wpf-security-strategy-security-engineering.md)
