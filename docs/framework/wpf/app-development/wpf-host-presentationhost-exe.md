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
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="9d9d6-102">WPF 호스트(PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9d9d6-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="9d9d6-103">Windows Presentation Foundation （WPF）宿主（Presentationhost.exe）是一种允许在兼容的浏览器（包括 Microsoft Internet Explorer 6 及更高版本）中承载 WPF 应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables WPF applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="9d9d6-104">默认情况下，Windows Presentation Foundation （WPF）主机注册为浏览器承载的 WPF 内容的 shell 和 MIME 处理程序，其中包括：</span><span class="sxs-lookup"><span data-stu-id="9d9d6-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted WPF content, which includes:</span></span>  
  
- <span data-ttu-id="9d9d6-105">느슨하게 압축되지 않은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일(.xaml).</span><span class="sxs-lookup"><span data-stu-id="9d9d6-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- <span data-ttu-id="9d9d6-106">XAML 浏览器应用程序（XBAP）（xbap）。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-106">XAML browser application (XBAP) (.xbap).</span></span>  
  
 <span data-ttu-id="9d9d6-107">对于这些类型的文件，Windows Presentation Foundation （WPF）主机：</span><span class="sxs-lookup"><span data-stu-id="9d9d6-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="9d9d6-108">启动已注册的 HTML 处理程序以承载 Windows Presentation Foundation （WPF）内容。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="9d9d6-109">加载所需的公共语言运行时（CLR）和 Windows Presentation Foundation （WPF）程序集的正确版本。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="9d9d6-110">배포 영역에 대해 적절한 권한 수준이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="9d9d6-111">이 항목에서는 PresentationHost.exe에서 사용할 수 있는 명령줄 매개 변수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="9d9d6-112">용도</span><span class="sxs-lookup"><span data-stu-id="9d9d6-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="9d9d6-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d9d6-113">Parameters</span></span>  
  
|<span data-ttu-id="9d9d6-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d9d6-114">Parameter</span></span>|<span data-ttu-id="9d9d6-115">설명</span><span class="sxs-lookup"><span data-stu-id="9d9d6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d9d6-116">파일 이름</span><span class="sxs-lookup"><span data-stu-id="9d9d6-116">filename</span></span>|<span data-ttu-id="9d9d6-117">활성화할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-117">The path of the file to be activated.</span></span> <span data-ttu-id="9d9d6-118">也可以是 URI。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-118">Can also be a URI.</span></span>|  
|<span data-ttu-id="9d9d6-119">-debug</span><span class="sxs-lookup"><span data-stu-id="9d9d6-119">-debug</span></span>|<span data-ttu-id="9d9d6-120">애플리케이션을 활성화할 때 저장소에서 커밋하거나 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="9d9d6-121">이는 로컬 파일이 활성화된 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="9d9d6-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="9d9d6-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="9d9d6-123">与 URL 值一起使用，以指示 Presentationhost.exe 应该调试应用程序，就像它是从指定的 URL 部署的一样。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-123">Used with a URL value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified URL.</span></span> <span data-ttu-id="9d9d6-124">이를 통해 배포 영역과 원본 사이트가 모두 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="9d9d6-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="9d9d6-125">-embedding</span></span>|<span data-ttu-id="9d9d6-126">OLE에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-126">Required by OLE.</span></span> <span data-ttu-id="9d9d6-127">`-event` 또는 `-debug` 매개 변수가 지정된 경우 `-embedding` 매개 변수가 내부적으로 설정되기 때문에 해당 매개 변수를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="9d9d6-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="9d9d6-128">-event \<eventname></span></span>|<span data-ttu-id="9d9d6-129">用此名称打开事件，并在 Presentationhost.exe 初始化并准备好承载 WPF 内容时发出信号。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host WPF content.</span></span> <span data-ttu-id="9d9d6-130">이벤트가 아직 만들어지지 않은 등의 이유로 인해 이벤트를 여는 데 오류가 발생하면 PresentationHost.exe가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d9d6-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="9d9d6-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="9d9d6-131">-launchApplication \<url></span></span>|<span data-ttu-id="9d9d6-132">从指定的 URL 启动独立的 ClickOnce 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="9d9d6-133">应用与 .NET 应用程序有关的 Internet Explorer 和 WinINet 安全策略。</span><span class="sxs-lookup"><span data-stu-id="9d9d6-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="9d9d6-134">시나리오</span><span class="sxs-lookup"><span data-stu-id="9d9d6-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="9d9d6-135">셸 처리기</span><span class="sxs-lookup"><span data-stu-id="9d9d6-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="9d9d6-136">MIME 처리기</span><span class="sxs-lookup"><span data-stu-id="9d9d6-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="9d9d6-137">Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="9d9d6-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="9d9d6-138">영역에서 Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="9d9d6-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="9d9d6-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d9d6-139">See also</span></span>

- [<span data-ttu-id="9d9d6-140">Security</span><span class="sxs-lookup"><span data-stu-id="9d9d6-140">Security</span></span>](../security-wpf.md)
