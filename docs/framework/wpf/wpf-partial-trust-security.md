---
title: 部分信任安全
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- partial trust security [WPF]
- detecting permissions [WPF]
- security settings for Internet Explorer [WPF]
- partial trust applications [WPF], debugging
- permissions [WPF], managing
- debugging partial trust applications [WPF]
- permissions [WPF], detecting
- feature security requirements [WPF]
- managing permissions [WPF]
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
ms.openlocfilehash: 0d9bbcc32eea49afc6ecc713b0cf005b4434a67d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743342"
---
# <a name="wpf-partial-trust-security"></a>WPF 부분 신뢰 보안
<a name="introduction"></a> 일반적으로 악의적인 손상을 방지하기 위해 중요한 시스템 리소스에 직접 액세스하지 않도록 인터넷 애플리케이션을 제한해야 합니다. 默认情况下，HTML 和客户端脚本语言不能访问关键系统资源。 由于可以从浏览器启动 Windows Presentation Foundation （WPF）浏览器承载的应用程序，因此它们应符合一组类似的限制。 若要强制实施这些限制，WPF 依赖于代码访问安全性（CAS）和 ClickOnce （请参阅[Wpf 安全策略-平台安全性](wpf-security-strategy-platform-security.md)）。 默认情况下，浏览器承载的应用程序请求 Internet 区域 CA 权限集，不管它们是从 Internet、本地 intranet 还是本地计算机启动。 전체 권한 집합보다 적은 권한으로 실행하는 애플리케이션은 부분 신뢰로 실행된다고 할 수 있습니다.  
  
 WPF 提供了广泛的支持，以确保在部分信任环境中可以安全地使用尽可能多的功能，并与 CA 一起为部分信任编程提供附加支持。  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
- [WPF 기능 부분 신뢰 지원](#WPF_Feature_Partial_Trust_Support)  
  
- [부분 신뢰 프로그래밍](#Partial_Trust_Programming)  
  
- [권한 관리](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## <a name="wpf-feature-partial-trust-support"></a>WPF 기능 부분 신뢰 지원  
 下表列出了在 Internet 区域权限集限制内可以安全使用的 Windows Presentation Foundation （WPF）的高级功能。  
  
 표 1: 부분 신뢰에서 안전한 WPF 기능  
  
|기능 영역|기능|  
|------------------|-------------|  
|일반|브라우저 창<br /><br /> 원 사이트 액세스<br /><br /> IsolatedStorage(512KB 제한)<br /><br /> UIAutomation 공급자<br /><br /> 명령<br /><br /> IME(입력기)<br /><br /> 태블릿 스타일러스 및 잉크<br /><br /> 마우스 캡처 및 이동 이벤트를 사용하여 시뮬레이션된 끌어서 놓기<br /><br /> OpenFileDialog<br /><br /> XamlReader.Load를 통한 XAML Deserialization|  
|웹 통합|브라우저 다운로드 대화 상자<br /><br /> 사용자가 시작한 최상위 탐색<br /><br /> mailto:links<br /><br /> URI(Uniform Resource Identifier) 매개 변수<br /><br /> HTTPWebRequest<br /><br /> IFRAME에 호스팅되는 WPF 콘텐츠<br /><br /> 프레임을 사용하여 동일한 사이트 HTML 페이지 호스팅<br /><br /> WebBrowser를 사용하여 동일한 사이트 HTML 페이지 호스팅<br /><br /> 웹 서비스(ASMX)<br /><br /> 웹 서비스(Windows Communication Foundation 사용)<br /><br /> 스크립팅 중<br /><br /> 문서 개체 모델|  
|시각적 개체|2D 및 3D<br /><br /> 애니메이션<br /><br /> 미디어(원본 사이트 및 도메인 간)<br /><br /> 이미지/오디오/비디오|  
|읽기|FlowDocuments<br /><br /> XPS 문서<br /><br /> 포함된 시스템 글꼴<br /><br /> CFF & 트루타입 글꼴|  
|편집|맞춤법 검사<br /><br /> RichTextBox<br /><br /> 일반 텍스트 및 잉크 클립보드 지원<br /><br /> 사용자가 시작한 붙여넣기<br /><br /> 선택한 콘텐츠 복사|  
|컨트롤|일반 컨트롤|  
  
 此表包含高级别的 WPF 功能。 有关更多详细信息，Windows SDK 记录 WPF 中每个成员所需的权限。 또한 다음 기능에는 특별한 고려 사항을 포함하는 부분 신뢰 실행에 대한 자세한 정보가 있습니다.  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] （请参阅[XAML 概述（WPF）](../../desktop-wpf/fundamentals/xaml.md)）。  
  
- 弹出窗口（请参阅 <xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>）。  
  
- 拖放（请参阅[拖放概述](./advanced/drag-and-drop-overview.md)）。  
  
- 剪贴板（请参阅 <xref:System.Windows.Clipboard?displayProperty=nameWithType>）。  
  
- 映像（请参阅 <xref:System.Windows.Controls.Image?displayProperty=nameWithType>）。  
  
- 序列化（请参阅 <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>，<xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>）。  
  
- "打开文件" 对话框（请参阅 <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>）。  
  
 下表概述了在 Internet 区域权限集限制内不能安全运行的 WPF 功能。  
  
 표 2: 부분 신뢰에서 안전하지 않은 WPF 기능  
  
|기능 영역|기능|  
|------------------|-------------|  
|일반|창(애플리케이션 정의 창 및 대화 상자)<br /><br /> SaveFileDialog<br /><br /> 파일 시스템<br /><br /> 레지스트리 액세스<br /><br /> 끌어서 놓기<br /><br /> XamlWriter.Save를 통한 XAML 직렬화<br /><br /> UIAutomation 클라이언트<br /><br /> 소스 창 액세스(HwndHost)<br /><br /> 완전한 음성 지원<br /><br /> Windows Forms 상호 운용성|  
|시각적 개체|비트맵 효과<br /><br /> 이미지 인코딩|  
|편집|RTF(서식 있는 텍스트) 클립보드<br /><br /> 전체 XAML 지원|  
  
<a name="Partial_Trust_Programming"></a>   
## <a name="partial-trust-programming"></a>부분 신뢰 프로그래밍  
 对于 XBAP 应用程序，超过默认权限集的代码将具有不同的行为，具体取决于安全区域。 일부 경우에는 사용자가 설치를 시도할 때 경고를 받게 됩니다. 사용자는 설치를 계속하거나 취소하도록 선택할 수 있습니다. 다음 표에서 각 보안 영역의 동작 및 애플리케이션이 완전 신뢰를 받기 위해 수행해야 하는 작업을 설명합니다.  
  
|보안 영역|行为|완전 신뢰 얻기|  
|-------------------|--------------|------------------------|  
|로컬 컴퓨터|자동 완전 신뢰|작업이 필요하지 않습니다.|  
|인트라넷 및 신뢰할 수 있는 사이트|완전 신뢰 확인|사용자가 프롬프트에서 소스를 볼 수 있도록 인증서로 XBAP에 로그인합니다.|  
|인터넷|"신뢰할 수 없음"과 함께 실패|인증서로 XBAP를 서명합니다.|  
  
> [!NOTE]
> 위의 표에 설명된 동작은 ClickOnce 신뢰 배포 모델을 따르지 않는 완전 신뢰 XBAP에 대한 것입니다.  
  
 일반적으로 허용되는 권한을 초과하는 코드는, 독립 실행형 애플리케이션과 브라우저에서 호스트된 애플리케이션 간에 공유되는 일반적인 코드일 수 있습니다. CAS 和 WPF 提供了几种管理此方案的方法。  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### <a name="detecting-permissions-using-cas"></a>CAS를 사용하여 권한 검색  
 在某些情况下，独立应用程序和 Xbap 可以使用库程序集中的共享代码。 이러한 경우 코드는 애플리케이션에서 얻은 권한 집합이 허용하는 것보다 많은 권한이 필요할 수 있는 기능을 실행할 수 있습니다. 应用程序可以通过使用 Microsoft .NET 框架安全性来检测它是否具有特定权限。 具体而言，它可以通过对所需权限的实例调用 <xref:System.Security.CodeAccessPermission.Demand%2A> 方法来测试它是否有特定权限。 다음 예제는 로컬 디스크에 파일을 저장하는 기능이 있는지 여부에 대해 쿼리하는 코드입니다.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 如果应用程序没有所需的权限，则对 <xref:System.Security.CodeAccessPermission.Demand%2A> 的调用将引发安全异常。 그렇지 않은 경우 사용 권한이 부여됩니다. `IsPermissionGranted` 封装此行为，并根据需要返回 `true` 或 `false`。  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### <a name="graceful-degradation-of-functionality"></a>점진적인 기능 저하  
 코드에 필요한 작업을 수행할 권한이 있는지 확인하는 것은 다른 영역에서 실행될 수 있는 코드와 관련되어 있습니다. 영역 검색이 하나의 방법이지만, 가능한 경우 사용자를 위한 대안을 제공하는 것이 좋습니다. 예를 들어 부분 신뢰 애플리케이션은 격리된 스토리지에만 파일을 만들 수 있지만, 일반적으로 완전 신뢰 애플리케이션은 사용자가 원하는 모든 곳에 파일을 만들 수가 있습니다. 파일을 만드는 코드가 완전 신뢰(독립 실행형) 애플리케이션과 부분 신뢰(브라우저에서 호스트된) 애플리케이션에서 공유되는 어셈블리에 존재하고 두 애플리케이션에서 사용자가 파일을 만들도록 하는 경우, 공유 코드는 해당 위치에 파일을 만들기 전에 부분 또는 완전 신뢰에서 실행 중인지 감지해야 합니다. 다음 코드는 두 사항을 모두 보여줍니다.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 대부분의 경우, 부분 신뢰 대체 항목을 찾을 수 있어야 됩니다.  
  
 在受控环境（例如 intranet）中，可在客户端基础上将自定义托管框架安装到全局程序集缓存（GAC）中。 这些库可以执行需要完全信任的代码，并通过使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 仅允许部分信任的应用程序进行引用（有关详细信息，请参阅[安全性](security-wpf.md)和[WPF 安全策略-平台安全性](wpf-security-strategy-platform-security.md)）。  
  
<a name="Browser_Host_Detection"></a>   
### <a name="browser-host-detection"></a>브라우저 호스트 검색  
 当你需要按权限检查时，使用 CA 检查权限是一种合适的方法。 이 기술은 일반적인 프로세스의 일부인 예외 감지에 영향을 받으며, 일반적으로 권장되지 않고 성능 문제를 일으킬 수 있습니다. 相反，如果您的 XAML 浏览器应用程序（XBAP）仅在 Internet 区域沙盒中运行，则可以使用 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> 属性，该属性将为 XAML 浏览器应用程序（Xbap）返回 true。  
  
> [!NOTE]
> <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A> 仅区分应用程序是否在浏览器中运行，而不区分应用程序运行时使用的权限集。  
  
<a name="Managing_Permissions"></a>   
## <a name="managing-permissions"></a>Managing Permissions  
 默认情况下，Xbap 以部分信任的方式运行（默认 Internet 区域权限集）。 그러나 애플리케이션의 요구에 따라 기본값에서 권한 집합을 변경할 수 있습니다. 例如，如果从本地 intranet 启动 Xbap，它可以利用增加的权限集，如下表所示。  
  
 표 3: LocalIntranet 및 인터넷 권한  
  
|사용 권한|특성|LocalIntranet|인터넷|  
|----------------|---------------|-------------------|--------------|  
|DNS|DNS 서버 액세스|예|否|  
|환경 변수|읽기|예|否|  
|파일 대화 상자|Open|예|예|  
|파일 대화 상자|제한 없음|예|否|  
|独立存储|사용자가 어셈블리 격리|예|否|  
|独立存储|알 수 없는 격리|예|예|  
|独立存储|무제한 사용자 할당량|예|否|  
|Media|안전한 오디오, 비디오 및 이미지|예|예|  
|인쇄|기본 인쇄|예|否|  
|인쇄|안전 인쇄|예|예|  
|리플렉션|내보내기|예|否|  
|보안|관리되는 코드 실행|예|예|  
|보안|부여된 권한 어셜션|예|否|  
|사용자 인터페이스|제한 없음|예|否|  
|사용자 인터페이스|안전한 최상위 창|예|예|  
|사용자 인터페이스|소유 클립보드|예|예|  
|Web 浏览器|HTML 안전 프레임 탐색|예|예|  
  
> [!NOTE]
> 잘라내기 및 붙여넣기는 사용자가 시작한 경우 부분 신뢰에서만 허용됩니다.  
  
 권한을 높이는 경우 프로젝트 설정 및 ClickOnce 애플리케이션 매니페스트를 변경해야 합니다. 자세한 내용은 [WPF XAML 브라우저 애플리케이션 개요](./app-development/wpf-xaml-browser-applications-overview.md)를 참조하세요. 다음 문서도 유용할 수 있습니다.  
  
- [Mage.exe(매니페스트 생성 및 편집 도구)](../tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
- [MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
- [ClickOnce 애플리케이션 보안](/visualstudio/deployment/securing-clickonce-applications).  
  
 如果 XBAP 需要完全信任，则可以使用相同的工具来增加请求的权限。 虽然 XBAP 仅在以下情况下才会获得完全信任：在本地计算机、intranet 或从浏览器的受信任或允许的站点中列出的 URL 中安装和启动。 인트라넷 또는 신뢰할 수 있는 사이트에서 애플리케이션이 설치되면, 사용자는 상승된 권한을 알리는 표준 ClickOnce 프롬프트를 받습니다. 사용자는 설치를 계속하거나 취소하도록 선택할 수 있습니다.  
  
 또는 모든 보안 영역에서 완전 신뢰 배포를 위한 ClickOnce 신뢰 배포 모델을 사용할 수 있습니다. 有关详细信息，请参阅[受信任的应用程序部署概述](/visualstudio/deployment/trusted-application-deployment-overview)和[安全性](security-wpf.md)。  
  
## <a name="see-also"></a>另请参阅

- [Security](security-wpf.md)
- [WPF 보안 전략 - 플랫폼 보안](wpf-security-strategy-platform-security.md)
- [WPF 보안 전략 - 보안 엔지니어링](wpf-security-strategy-security-engineering.md)
