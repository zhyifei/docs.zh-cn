---
title: WPF 호스트(PresentationHost.exe)
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: bda7efbb1b7a4760199215bdb58c12b3063e290c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743398"
---
# <a name="wpf-host-presentationhostexe"></a>WPF 호스트(PresentationHost.exe)
Windows Presentation Foundation （WPF）宿主（Presentationhost.exe）是一种允许在兼容的浏览器（包括 Microsoft Internet Explorer 6 及更高版本）中承载 WPF 应用程序的应用程序。 默认情况下，Windows Presentation Foundation （WPF）主机注册为浏览器承载的 WPF 内容的 shell 和 MIME 处理程序，其中包括：  
  
- 느슨하게 압축되지 않은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일(.xaml).  
  
- XAML 浏览器应用程序（XBAP）（xbap）。  
  
 对于这些类型的文件，Windows Presentation Foundation （WPF）主机：  
  
- 启动已注册的 HTML 处理程序以承载 Windows Presentation Foundation （WPF）内容。  
  
- 加载所需的公共语言运行时（CLR）和 Windows Presentation Foundation （WPF）程序集的正确版本。  
  
- 배포 영역에 대해 적절한 권한 수준이 설정되어 있는지 확인합니다.  
  
 이 항목에서는 PresentationHost.exe에서 사용할 수 있는 명령줄 매개 변수를 설명합니다.  
  
## <a name="usage"></a>용도  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|파일 이름|활성화할 파일의 경로입니다. 也可以是 URI。|  
|-debug|애플리케이션을 활성화할 때 저장소에서 커밋하거나 실행하지 않습니다. 이는 로컬 파일이 활성화된 경우에만 작동합니다.|  
|-debugSecurityZoneURL \<url>|与 URL 值一起使用，以指示 Presentationhost.exe 应该调试应用程序，就像它是从指定的 URL 部署的一样。 이를 통해 배포 영역과 원본 사이트가 모두 결정됩니다.|  
|-embedding|OLE에 필요합니다. `-event` 또는 `-debug` 매개 변수가 지정된 경우 `-embedding` 매개 변수가 내부적으로 설정되기 때문에 해당 매개 변수를 지정할 필요가 없습니다.|  
|-event \<eventname>|用此名称打开事件，并在 Presentationhost.exe 初始化并准备好承载 WPF 内容时发出信号。 이벤트가 아직 만들어지지 않은 등의 이유로 인해 이벤트를 여는 데 오류가 발생하면 PresentationHost.exe가 종료됩니다.|  
|-launchApplication \<url>|从指定的 URL 启动独立的 ClickOnce 应用程序。 应用与 .NET 应用程序有关的 Internet Explorer 和 WinINet 安全策略。|  
  
## <a name="scenarios"></a>시나리오  
  
### <a name="shell-handler"></a>셸 처리기  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>MIME 처리기  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Visual Studio 디버깅  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>영역에서 Visual Studio 디버깅  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>另请参阅

- [Security](../security-wpf.md)
