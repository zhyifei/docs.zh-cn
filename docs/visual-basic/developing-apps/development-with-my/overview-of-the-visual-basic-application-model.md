---
title: Visual Basic 应用程序模型概述
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: aa47304cf2bded93bdb95ffe7dfa35bb37d9a643
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976463"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Visual Basic 应用程序模型概述

Visual Basic 提供定义完善的模型来控制 Windows 窗体应用程序的行为： Visual Basic 应用程序模型。 此模型包含处理应用程序的启动和关闭的事件，以及用于捕获未经处理的异常的事件。 它还为开发单实例应用程序提供支持。 应用程序模型是可扩展的，因此需要更多控件的开发人员可以自定义其可重写的方法。  
  
## <a name="uses-for-the-application-model"></a>应用程序模型的用途  

 典型的应用程序在启动和关闭时需要执行任务。 例如，当启动时，应用程序可以显示初始屏幕、进行数据库连接、加载已保存状态等。 当应用程序关闭时，它可以关闭数据库连接，保存当前状态，等等。 此外，应用程序可以在应用程序意外关闭时（例如在未经处理的异常期间）执行特定代码。  
  
 使用 Visual Basic 应用程序模型，可以轻松创建*单实例*应用程序。 单实例应用程序不同于普通的应用程序，因为一次只能运行一个应用程序实例。 如果尝试启动单实例应用程序的另一个实例，则会通过 `StartupNextInstance` 事件来通知原始实例，即已进行了另一次启动尝试。 通知包括后续实例的命令行参数。 然后，应用程序的后续实例将关闭，然后才能进行任何初始化。  
  
 单实例应用程序启动并检查它是第一个实例还是应用程序的后续实例：  
  
- 如果它是第一个实例，则它会照常启动。  
  
- 每次启动应用程序时，如果第一个实例运行，都将产生不同的行为。 后续尝试会通知第一个实例有关命令行参数的信息，然后立即退出。 第一个实例处理 `StartupNextInstance` 事件，以确定后续实例的命令行参数是什么，并继续运行。  
  
     此图显示了后续实例如何向第一个实例发出信号：  
  
     ![显示单个实例应用程序映像的关系图。](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 通过处理 `StartupNextInstance` 事件，可以控制单实例应用程序的行为方式。 例如，Microsoft Outlook 通常作为单实例应用程序运行;当 Outlook 正在运行并且您尝试再次启动 Outlook 时，焦点将移到原始实例上，但其他实例不会打开。  
  
## <a name="events-in-the-application-model"></a>应用程序模型中的事件  

 在应用程序模型中找到以下事件：  
  
- **应用程序启动**。 应用程序在启动时会引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 事件。 通过处理此事件，您可以添加代码，以便在加载主窗体之前初始化该应用程序。 如果需要，`Startup` 事件还可用于在启动过程的该阶段取消执行应用程序。  
  
     你可以将应用程序配置为在应用程序启动代码运行时显示初始屏幕。 默认情况下，当使用 `/nosplash` 或 `-nosplash` 命令行参数时，应用程序模型会禁止初始屏幕。  
  
- **单实例应用程序**。 当单实例应用程序的后续实例启动时，将引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 事件。 事件传递后续实例的命令行参数。  
  
- **未经处理的异常**。 如果应用程序遇到未经处理的异常，则会引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 事件。 该事件的处理程序可以检查异常，并确定是否继续执行。  
  
     在某些情况下，不会引发 `UnhandledException` 事件。 有关更多信息，请参见<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>。  
  
- **网络连接性更改**。 如果计算机的网络可用性发生变化，应用程序会引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> 事件。  
  
     在某些情况下，不会引发 `NetworkAvailabilityChanged` 事件。 有关更多信息，请参见<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>。  
  
- **应用程序关闭**。 应用程序提供了 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 事件，以在即将关闭时发出信号。 在该事件处理程序中，可以确保应用程序需要执行的操作（例如，关闭和保存）已完成。 你可以将应用程序配置为在主窗体关闭时关闭，或仅在关闭所有窗体后关闭。  
  
## <a name="availability"></a>可用性  

 默认情况下，Visual Basic 应用程序模型可用于 Windows 窗体项目。 如果将应用程序配置为使用不同的启动对象，或使用自定义 `Sub Main`启动应用程序代码，则该对象或类可能需要提供 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 类的实现以使用应用程序模型。 有关更改启动对象的信息，请参阅[应用程序页、项目设计器（Visual Basic）](/visualstudio/ide/reference/application-page-project-designer-visual-basic)。  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [扩展 Visual Basic 应用程序模型](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
