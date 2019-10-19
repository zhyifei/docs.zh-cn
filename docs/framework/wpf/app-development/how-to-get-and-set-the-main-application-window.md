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
# <a name="how-to-get-and-set-the-main-application-window"></a>如何：获取和设置主应用程序窗口
此示例演示如何获取和设置主应用程序窗口。  
  
## <a name="example"></a>示例  
 Windows Presentation Foundation （WPF）应用程序中实例化的第一个 <xref:System.Windows.Window> 将 <xref:System.Windows.Application> 作为主应用程序窗口自动设置。 要实例化的第一个 <xref:System.Windows.Window> 最有可能是指定为启动统一资源标识符（URI）的窗口（请参阅 <xref:System.Windows.Application.StartupUri%2A>）。  
  
 第一个 <xref:System.Windows.Window> 也可以使用代码实例化。 例如，在应用程序启动过程中打开一个窗口，如下所示：  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 有时，第一个实例化 <xref:System.Windows.Window> 实际上不是主应用程序窗口（例如，初始屏幕）。 在这种情况下，可以使用标记指定主应用程序窗口，如下所示：  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 无论是自动还是手动指定主窗口，都可以使用下面的代码从 <xref:System.Windows.Application.MainWindow%2A> 获取主窗口，如下所示：  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
