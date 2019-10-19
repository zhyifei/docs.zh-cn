---
title: 如何：获取和设置主应用程序窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582546"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="140de-102">如何：获取和设置主应用程序窗口</span><span class="sxs-lookup"><span data-stu-id="140de-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="140de-103">此示例演示如何获取和设置主应用程序窗口。</span><span class="sxs-lookup"><span data-stu-id="140de-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="140de-104">示例</span><span class="sxs-lookup"><span data-stu-id="140de-104">Example</span></span>  
 <span data-ttu-id="140de-105">Windows Presentation Foundation （WPF）应用程序中实例化的第一个 <xref:System.Windows.Window> 将 <xref:System.Windows.Application> 作为主应用程序窗口自动设置。</span><span class="sxs-lookup"><span data-stu-id="140de-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="140de-106">要实例化的第一个 <xref:System.Windows.Window> 最有可能是指定为启动统一资源标识符（URI）的窗口（请参阅 <xref:System.Windows.Application.StartupUri%2A>）。</span><span class="sxs-lookup"><span data-stu-id="140de-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup uniform resource identifier (URI) (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="140de-107">第一个 <xref:System.Windows.Window> 也可以使用代码实例化。</span><span class="sxs-lookup"><span data-stu-id="140de-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="140de-108">例如，在应用程序启动过程中打开一个窗口，如下所示：</span><span class="sxs-lookup"><span data-stu-id="140de-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="140de-109">有时，第一个实例化 <xref:System.Windows.Window> 实际上不是主应用程序窗口（例如，初始屏幕）。</span><span class="sxs-lookup"><span data-stu-id="140de-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="140de-110">在这种情况下，可以使用标记指定主应用程序窗口，如下所示：</span><span class="sxs-lookup"><span data-stu-id="140de-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="140de-111">无论是自动还是手动指定主窗口，都可以使用下面的代码从 <xref:System.Windows.Application.MainWindow%2A> 获取主窗口，如下所示：</span><span class="sxs-lookup"><span data-stu-id="140de-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
