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
ms.openlocfilehash: 1ef705fcf046af1f4136ddcf1b29f417c0d72c83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741852"
---
# <a name="wpf-security-strategy---platform-security"></a>WPF 보안 전략 - 플랫폼 보안
虽然 Windows Presentation Foundation （WPF）提供各种安全服务，但它还利用基础平台（包括操作系统、CLR 和 Internet Explorer）的安全功能。 这些层组合在一起为 WPF 提供强大的深层防御安全模型，尝试避免任何单点故障，如下图所示：  
  
 ![显示 WPF 安全模型的关系图。](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 本主题的其余部分将讨论专门适用于 WPF 的每个层中的功能。  

## <a name="operating-system-security"></a>운영 체제 보안  
Windows 的核心提供了几种安全功能，这些功能构成了所有 Windows 应用程序（包括用 WPF 构建的应用程序）的安全基础。 本主题讨论了对 WPF 重要的这些安全功能的广度，以及 WPF 如何与它们集成以提供进一步的深层防御。  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP SP2(서비스 팩 2)  
 除了对 Windows 进行一般检查和强化外，本主题还将讨论 [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] 三个关键功能：  
  
- /GS 컴파일  
  
- Microsoft Windows 更新。  
  
#### <a name="gs-compilation"></a>/GS 컴파일  
 [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] 通过重新编译许多核心系统库（包括所有 WPF 依赖项（如 CLR）来提供保护，以帮助缓解缓冲区溢出。 이 작업을 위해 /GS 매개 변수와 C/C++ 명령줄 컴파일러를 함께 사용합니다. 버퍼 오버런을 명시적으로 피해야 하지만 /GS 컴파일은 실수 또는 악의적으로 만들어진 잠재적인 취약성에 대한 심층 방어의 예를 제공합니다.  
  
 지금까지 버퍼 오버런은 많은 강력한 보안 익스플로이트의 원인이 되었습니다. 버퍼 오버런은 공격자는 버퍼의 경계를 지나서 쓰는 악성 코드의 삽입을 허용하는 코드 취약성을 활용하는 경우에 발생합니다. 이 경우 공격자의 코드가 실행되도록 함수의 반환 주소를 덮어써서 코드가 실행되는 프로세스를 공격자가 가로챌 수 있습니다. 그 결과, 가로챈 프로세스와 동일한 권한으로 임의 코드를 실행하는 악성 코드가 생깁니다.  
  
 在高级别上，-GS 编译器标志通过注入特殊安全 cookie 来保护具有本地字符串缓冲区的函数的返回地址，从而防止某些潜在的缓冲区溢出。 함수가 반환된 후 보안 쿠키를 이전 값과 비교합니다. 값이 변경된 경우 버퍼 오버런이 발생했을 수 있으며 프로세스가 오류 상태로 중지됩니다. 프로세스를 중지하면 잠재적인 악성 코드의 실행이 방지됩니다. 有关更多详细信息，请参阅[-GS （缓冲区安全检查）](/cpp/build/reference/gs-buffer-security-check) 。  
  
 WPF 用/GS 标志进行编译，以便向 WPF 应用程序添加另一层防御。  
  
### <a name="windows-vista"></a>Windows Vista  
Windows Vista 上的 WPF 用户将受益于操作系统的附加安全增强功能，其中包括 "最小特权用户访问权限"、代码完整性检查和特权隔离。  
  
#### <a name="user-account-control-uac"></a>UAC(사용자 계정 컨트롤)  
 目前，Windows 用户倾向于以管理员权限运行，因为许多应用程序都需要它们进行安装或执行，或者两者都需要。 한 가지 예로 기본 애플리케이션 설정을 레지스트리에 쓸 수 있습니다.  
  
 관리자 권한으로 실행은 실제로 관리자 권한이 부여된 프로세스에서 애플리케이션이 실행됨을 의미합니다. 이 경우 보안에 미치는 영향은 관리자 권한으로 실행되는 프로세스를 가로챈 악성 코드가 중요한 시스템 리소스에 대한 액세스를 포함하여 해당 권한을 자동으로 상속하게 된다는 것입니다.  
  
 이 보안 위협으로부터 보호하는 한 가지 방법은 필요한 최소한의 권한으로 애플리케이션을 실행하는 것입니다. 这称为最小特权原则，是 Windows 操作系统的核心功能。 此功能称为用户帐户控制（UAC），由 Windows UAC 用两种主要方式使用：  
  
- 사용자가 관리자인 경우에도 기본적으로 대부분의 애플리케이션을 UAC 권한으로 실행합니다. 관리자 권한이 필요한 애플리케이션만 관리자 권한으로 실행됩니다. 관리자 권한으로 실행하려면 애플리케이션 매니페스트에서 또는 보안 정책의 항목으로 애플리케이션에 명시적으로 표시해야 합니다.  
  
- 가상화와 같은 호환성 솔루션을 제공합니다. 예를 들어 많은 애플리케이션이 C:\Program Files와 같은 제한된 위치에 쓰려고 합니다. UAC로 실행되는 애플리케이션의 경우 쓰는 데 관리자 권한이 필요하지 않은 사용자별 대체 위치가 있습니다. UAC로 실행되는 애플리케이션의 경우 해당 위치에 쓰고 있다고 생각하는 애플리케이션이 실제로는 사용자별 대체 위치에 쓰도록 UAC에서 C:\Program Files를 가상화합니다. 이러한 종류의 호환성 작업을 통해 운영 체제가 UAC에서 이전에 실행할 수 없었던 많은 애플리케이션을 실행할 수 있습니다.  
  
#### <a name="code-integrity-checks"></a>코드 무결성 검사  
 Windows Vista 合并了更深入的代码完整性检查，以帮助防止恶意代码在负载/运行时注入到系统文件或内核中。 이는 시스템 파일 보호 수준을 벗어납니다.  
   
### <a name="limited-rights-process-for-browser-hosted-applications"></a>브라우저에서 호스트된 애플리케이션에 대한 제한된 권한 프로세스  
 浏览器承载的 WPF 应用程序在 Internet 区域沙箱内执行。 与 Microsoft Internet Explorer 的 WPF 集成扩展了此保护，并提供了更多支持。  
  
 由于 XAML 浏览器应用程序（Xbap）通常由 Internet 区域权限集进行沙盒处理，因此，删除这些权限不会损害 XAML 浏览器应用程序（Xbap）的兼容性。 대신, 추가 심층 방어 계층이 만들어집니다. 샌드박스 애플리케이션이 다른 계층을 악용하고 프로세스를 가로챌 수 있는 경우 프로세스에 여전히 제한된 권한만 포함됩니다.  
  
 请参阅[使用最低权限的用户帐户](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29)。  
  
## <a name="common-language-runtime-security"></a>공용 언어 런타임 보안  
 公共语言运行时（CLR）提供了许多重要的安全优势，包括验证和验证、代码访问安全性（CAS）和安全关键方法。  
    
### <a name="validation-and-verification"></a>유효성 검사 및 확인  
 为了提供程序集隔离和完整性，CLR 使用验证过程。 CLR 验证通过验证指向程序集外部地址的可移植可执行（PE）文件格式来确保程序集的隔离。 CLR 验证还验证嵌入到程序集内的元数据的完整性。  
  
 为了确保类型安全，帮助防止常见安全问题（例如缓冲区溢出），并通过子进程隔离启用沙盒，CLR 安全使用验证概念。  
  
 관리되는 애플리케이션은 MSIL(Microsoft Intermediate Language)로 컴파일됩니다. 관리되는 애플리케이션의 메서드를 실행하면 해당 MSIL이 JIT(Just-In-Time) 컴파일을 통해 네이티브 코드로 컴파일됩니다. JIT 컴파일에는 코드에서 다음이 발생하지 않도록 하는 다양한 안정성 및 견고성 규칙을 적용하는 검증 프로세스가 포함됩니다.  
  
- 형식 계약 위반  
  
- 버퍼 오버런 도입  
  
- 무분별한 메모리 액세스  
  
 검증 규칙을 준수하지 않는 관리 코드는 신뢰할 수 있는 코드로 간주되지 않을 경우 실행할 수 없습니다.  
  
 可验证代码的优点是 WPF 在 .NET Framework 上构建的主要原因。 검증할 수 있는 코드를 사용하면 가능한 취약성이 악용될 가능성이 훨씬 줄어듭니다.  
  
### <a name="code-access-security"></a>代码访问安全性  
 클라이언트 컴퓨터는 파일 시스템, 레지스트리, 인쇄 서비스, 사용자 인터페이스, 리플렉션 및 환경 변수를 포함하여 관리되는 애플리케이션이 액세스할 수 있는 다양한 리소스를 노출합니다. 在托管应用程序可以访问客户端计算机上的任何资源之前，它必须具有 .NET Framework 的权限。 CA 中的权限是 <xref:System.Security.CodeAccessPermission>的子类;CA 为托管应用程序可以访问的每个资源实现一个子类。  
  
 CA 在开始执行时授予托管应用程序的权限集称为权限集，由应用程序提供的证据确定。 对于 WPF 应用程序，提供的证据为从中启动应用程序的位置或区域。 CA 标识以下区域：  
  
- **내 컴퓨터** 클라이언트 컴퓨터에서 시작된 애플리케이션입니다(완전 신뢰).  
  
- **로컬 인트라넷** 인트라넷에서 시작된 애플리케이션입니다. (다소 신뢰).  
  
- **인터넷** 인터넷에서 시작된 애플리케이션입니다. (최소 신뢰).  
  
- **신뢰할 수 있는 사이트** 사용자가 신뢰할 수 있는 것으로 식별한 애플리케이션입니다. (최소 신뢰).  
  
- **신뢰할 수 없는 사이트** 사용자가 신뢰할 수 없는 것으로 식별한 애플리케이션입니다. (신뢰할 수 없음).  
  
 对于其中的每个区域，CA 都提供预定义的权限集，该权限集包含与每个相关联的信任级别相匹配的权限。 여기에는 다음이 포함됩니다.  
  
- **FullTrust** 对于从**我的电脑**区域启动的应用程序。 가능한 모든 권한은 부여됩니다.  
  
- **LocalIntranet** 对于从**本地 Intranet**区域启动的应用程序。 격리된 스토리지, 무제한 UI 액세스, 무제한 파일 대화 상자, 제한된 리플렉션, 환경 변수에 대한 제한된 액세스를 포함하여 클라이언트 머신의 리소스에 대해 보통 액세스 권한을 제공하도록 권한 하위 집합이 부여됩니다. 레지스트리와 같은 중요한 리소스에 대한 권한은 제공되지 않습니다.  
  
- **인터넷** 适用于从**Internet**或**受信任的站点**区域启动的应用程序。 격리된 스토리지, 파일 열기 전용 및 제한된 UI를 포함하여 클라이언트 머신의 리소스에 대해 제한된 액세스 권한을 제공하도록 권한 하위 집합이 부여됩니다. 实质上，此权限集将应用程序与客户端计算机隔离开来。  
  
 标识为来自**不受信任的站点**区域的应用程序将不会被 ca 授予任何权限。 따라서 미리 정의된 해당 권한 집합이 없습니다.  
  
 下图说明了区域、权限集、权限和资源之间的关系：  
  
 ![显示 CAS 权限集的关系图。](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Internet 区域安全沙盒的限制同样适用于 XBAP 从系统库导入的任何代码，包括 WPF。 这可确保代码的每个位都被锁定，甚至是 WPF。 遗憾的是，为了能够执行，XBAP 需要执行需要比 Internet 区域安全沙盒启用的权限更多的功能。  
  
 请考虑包含以下页面的 XBAP 应用程序：  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 若要执行此 XBAP，基础 WPF 代码必须执行比可用于调用 XBAP 的功能更多的功能，包括：  
  
- 创建用于呈现的窗口句柄（HWND）  
  
- 메시지 디스패치  
  
- Tahoma 글꼴 로드  
  
 샌드박스 애플리케이션에서 이러한 작업에 직접 액세스할 수 있도록 허용하면 보안상 치명적일 수 있습니다.  
  
 幸运的是，WPF 通过允许这些操作以提升的权限在代表沙盒应用程序的情况下执行来适用于这种情况。 尽管所有 WPF 操作都是针对 XBAP 的应用程序域的有限 Internet 区域安全权限检查的，但 WPF （与其他系统库一样）的权限集被授予了包括所有可能权限的权限集。
  
 这要求 WPF 接收提升的特权，同时阻止由主机应用程序域的 Internet 区域权限集来控制这些权限。  
  
 WPF 使用权限的**Assert**方法来实现此功能。 다음 코드에서는 이렇게 되는 방식을 보여 줍니다.  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 **断言**实质上是防止 WPF 要求的无限制权限受到 XBAP 的 Internet 区域权限限制。  
  
 从平台的角度来看，WPF 负责正确使用**Assert** ;**断言**的使用不当可能导致恶意代码提升特权。 因此，只需在需要时调用**断言**，并确保沙盒限制保持不变，这一点非常重要。 예를 들어 샌드박스 코드는 임의의 파일을 열 수 없지만 글꼴을 사용할 수 있습니다. WPF 使沙盒应用程序可以通过调用**Assert**来使用字体功能，wpf 使用它可以代表沙盒应用程序读取已知包含这些字体的文件。  
  
### <a name="clickonce-deployment"></a>ClickOnce 배포  
 ClickOnce 是一种全面的部署技术，随 .NET Framework 提供，并与 Visual Studio 集成（有关详细信息，请参阅[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)）。 独立 WPF 应用程序可使用 ClickOnce 进行部署，而浏览器承载的应用程序必须使用 ClickOnce 进行部署。  
  
 使用 ClickOnce 部署的应用程序在代码访问安全性（CAS）上给予了附加的安全层;实质上，ClickOnce 部署的应用程序会请求所需的权限。 애플리케이션이 배포된 소스 영역에 대한 권한 집합을 초과하지 않는 경우에만 해당 권한이 부여됩니다. 通过将权限集减少到仅需要的权限集，即使它们小于启动区域的权限集提供的权限集，应用程序有权访问的资源数也会降至最低。 따라서 애플리케이션을 가로채는 경우 클라이언트 컴퓨터의 손상 가능성이 줄어듭니다.  
  
### <a name="security-critical-methodology"></a>보안에 중요한 방법론  
 使用权限启用用于 XBAP 应用程序的 Internet 区域沙盒的 WPF 代码必须保持最高的安全审核和控制度。 为了满足此要求，.NET Framework 为管理提升特权的代码提供了新支持。 具体而言，CLR 使你能够识别提升特权的代码并将其标记为 <xref:System.Security.SecurityCriticalAttribute>;任何未标记为 <xref:System.Security.SecurityCriticalAttribute> 的代码都将使用此方法变得*透明*。 반대로, <xref:System.Security.SecurityCriticalAttribute>로 표시되지 않은 관리 코드는 권한을 높일 수 있습니다.  
  
 安全关键方法允许将提升特权的 WPF 代码的组织转换为*安全关键内核*，并使剩余部分透明。 隔离安全关键代码可使 WPF 工程团队将附加的安全分析和源控制重点放在安全关键内核之上，而不是标准安全实践（请参阅[WPF 安全策略-安全工程](wpf-security-strategy-security-engineering.md)）。  
  
 请注意，.NET Framework 允许受信任的代码通过允许开发人员编写标记为 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> （APTCA）并部署到用户的全局程序集缓存（GAC）的托管程序集来扩展 XBAP Internet 区域沙盒。 어셈블리에 APTCA로 표시하는 경우 인터넷의 악성 코드를 비롯한 모든 코드에서 해당 어셈블리를 호출할 수 있으므로 중요한 보안 작업입니다. 이 작업을 수행할 때는 주의해서 최선의 방법을 사용해야 하며, 사용자가 해당 소프트웨어를 신뢰해야 설치됩니다.  
  
## <a name="microsoft-internet-explorer-security"></a>Microsoft Internet Explorer 보안  
 除减少安全问题和简化安全配置外，Microsoft Internet Explorer 6 （SP2）还包含多个增强 XAML 浏览器应用程序（Xbap）用户安全性的功能。 이러한 기능은 사용자가 검색 환경을 보다 효율적으로 제어할 수 있도록 하기 위한 것입니다.  
  
 在 IE6 SP2 之前，用户可能会受到以下任意一项操作：  
  
- 무작위 팝업 창  
  
- 혼란스러운 스크립트 리디렉션  
  
- 일부 웹 사이트의 수많은 보안 대화 상자  
  
 在某些情况下，不受信任的网站将尝试通过欺骗安装 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 或重复显示 Microsoft ActiveX 安装对话框（即使用户可能已将其取消）来欺骗用户。 이러한 기술을 사용하면 다수의 사용자가 속아서 잘못된 결정을 내리고 스파이웨어 애플리케이션을 설치할 수 있습니다.  
  
 IE6 SP2 包含多项功能，可用于减少这些类型的问题，这些问题涉及用户启动的概念。 当用户在操作之前单击了某个链接或页面元素时，IE6 SP2 会检测到该操作（称为*用户启动*），并将其视为不同于页面上脚本触发的类似操作。 例如，IE6 SP2 合并了一个**弹出窗口阻止**程序，用于检测用户在页面创建弹出窗口之前单击按钮的时间。 这样一来，IE6 SP2 便可允许最无害的弹出窗口，同时阻止用户既不需要也不需要的弹出窗口。 阻止的弹出窗口会在新的**信息栏**下捕获，这允许用户手动替代块并查看弹出窗口。  
  
 相同的用户启动逻辑也适用于**打开**/**保存**安全提示。 始终在信息栏下捕获 ActiveX 安装对话框，除非它们表示从以前安装的控件进行升级。 이러한 조치가 결합되어 사용자에게 더 안전하고 제어된 사용자 환경을 제공합니다. 사용자가 원하지 않는 소프트웨어나 악성 소프트웨어를 설치하도록 유인하는 사이트로부터 보호되기 때문입니다.  
  
 这些功能还可保护使用 IE6 SP2 浏览网站的客户，使他们能够下载和安装 WPF 应用程序。 具体来说，这是因为 IE6 SP2 提供了更好的用户体验，可减少用户安装恶意或狡猾应用程序的可能性，而不考虑使用哪种技术来构建应用程序（包括 WPF）。 WPF 通过使用 ClickOnce 增加了这些保护，以便通过 Internet 下载其应用程序。 由于 XAML 浏览器应用程序（Xbap）在 Internet 区域安全沙盒中执行，因此可以无缝地启动它们。 另一方面，独立的 WPF 应用程序需要完全信任才能执行。 对于这些应用程序，ClickOnce 将在启动过程中显示一个安全对话框，以通知使用应用程序的其他安全要求。 그러나 사용자가 시작해야 하고, 사용자가 시작한 논리에 의해 제어되며, 취소할 수 있습니다.  
  
 Internet Explorer 7 结合并扩展了 IE6 SP2 的安全功能，作为对安全性的不断承诺的一部分。  
  
## <a name="see-also"></a>另请参阅

- [코드 액세스 보안](../misc/code-access-security.md)
- [Security](security-wpf.md)
- [WPF 부분 신뢰 보안](wpf-partial-trust-security.md)
- [WPF 보안 전략 - 보안 엔지니어링](wpf-security-strategy-security-engineering.md)
