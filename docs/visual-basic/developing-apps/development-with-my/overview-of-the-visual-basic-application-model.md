---
title: "Visual Basic 应用程序模型概述"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33b0e01317a6dab18ea03047c146def32b5675ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="overview-of-the-visual-basic-application-model"></a>Visual Basic 应用程序模型概述
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提供用于控制 Windows 窗体应用程序的行为定义完善的模型：[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]应用程序模型。 此模型包括事件，以处理应用程序的启动和关闭，以及用于捕获未经处理的异常事件。 它还提供有关在开发单实例应用程序的支持。 应用程序模型是可扩展的，因此需要更多控制权的开发人员可以自定义其可重写的方法。  
  
## <a name="uses-for-the-application-model"></a>使用应用程序模型  
 典型的应用程序需要对它启动和关闭时执行任务。 例如，当它启动时，应用程序可以显示初始屏幕、 建立数据库连接、 加载已保存的状态，依次类推。 当应用程序关闭时，它可以关闭数据库连接、 保存的当前状态，依次类推。 此外，应用程序可以执行特定的代码，应用程序关闭时意外，例如在下未经处理的异常。  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]应用程序模型，更加轻松地创建*单实例*应用程序。 单实例应用程序不同正常应用程序中，只有一个实例应用程序可以运行一次。 尝试启动单实例应用程序的另一个实例会导致在收到通知的原始实例 — 通过`StartupNextInstance`事件-另一次启动尝试所做的。 此通知包括后续实例的命令行自变量。 然后才能进行任何初始化，然后关闭应用程序的后续实例。  
  
 单实例应用程序启动，并且检查它是否为第一个实例或应用程序的后续实例：  
  
-   如果它是第一个实例，它将正常启动。  
  
-   每个后续尝试启动该应用程序，当运行时的第一个实例，将导致非常不同的行为。 后续尝试通知有关命令行自变量，第一个实例，并立即退出。 第一个实例句柄`StartupNextInstance`事件，以确定后续实例的命令行自变量，然后继续运行。  
  
     下图显示的后续实例发出的第一个实例的信号。  
  
     ![单实例应用程序映像](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 通过处理`StartupNextInstance`事件，您可以控制单实例应用程序的行为方式。 例如，Microsoft Outlook 通常运行作为单实例应用程序;当 Outlook 正在运行而您尝试启动 Outlook 同样，焦点切换到原始实例，但不会打开另一个实例。  
  
## <a name="events-in-the-application-model"></a>应用程序模型中的事件  
 应用程序模型中找到以下事件：  
  
-   **应用程序启动**。 应用程序将引发<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>事件启动时。 通过处理此事件，你可以添加初始化应用程序，然后再加载主窗体的代码。 `Startup`事件还提供了取消执行的应用程序在该阶段的启动过程中，如果需要。  
  
     你可以配置要显示的初始屏幕，应用程序启动代码运行时的应用程序。 默认情况下，应用程序模型将取消显示初始屏幕时请`/nosplash`或`-nosplash`使用命令行参数。  
  
-   **单实例应用程序**。 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>单实例应用程序的后续实例启动时引发事件。 该事件传递后续的实例的命令行参数。  
  
-   **未经处理的异常**。 如果应用程序遇到未经处理的异常，它会发出<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>事件。 你为该事件的处理程序可以检查异常，并确定是否要继续执行。  
  
     `UnhandledException`在某些情况下，不会引发事件。 有关更多信息，请参见<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>。  
  
-   **网络连接更改**。 如果计算机的网络可用性发生变化，应用程序将引发<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>事件。  
  
     `NetworkAvailabilityChanged`在某些情况下，不会引发事件。 有关更多信息，请参见<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>。  
  
-   **应用程序关闭**。 该应用程序提供<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>事件以发出信号时可以关闭它。 这种情况下处理程序中，你可以确保，操作你的应用程序需要执行-关闭并保存，例如-完成。 你可以配置你的应用程序关闭时关闭主窗体，或关闭仅当所有窗体关闭。  
  
## <a name="availability"></a>可用性  
 默认情况下，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]应用程序模型是适用于 Windows 窗体项目。 如果应用程序配置为使用不同的启动对象，或使用自定义启动应用程序代码`Sub Main`，则该对象或类可能需要提供的实现<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>类以使用应用程序模型。 有关更改的启动对象的信息，请参阅[应用程序页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [扩展 Visual Basic 应用程序模型](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
