---
title: 扩展 Visual Basic 应用程序模型
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 02a964506d976cb10f3f28f83f0655fecc447e59
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582762"
---
# <a name="extending-the-visual-basic-application-model"></a>扩展 Visual Basic 应用程序模型

可以通过重写 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 类的 `Overridable` 成员，将功能添加到应用程序模型。 利用此方法，你可以自定义应用程序模型的行为，并在应用程序启动和关闭时添加对你自己的方法的调用。

## <a name="visual-overview-of-the-application-model"></a>应用程序模型的视觉对象概述

本节直观显示 Visual Basic 应用程序模型中的函数调用序列。 下一部分将详细介绍每个函数的用途。

下图显示了正常 Visual Basic Windows 窗体应用程序中的应用程序模型调用序列。 序列在 `Sub Main` 过程调用 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 方法时开始。

![显示应用程序模型调用序列的关系图。](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

Visual Basic 应用程序模型还提供 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 并 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 事件。 下图显示了引发这些事件的机制。

![显示引发 StartupNextInstance 事件的 OnStartupNextInstance 方法的关系图。](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![显示引发 UnhandledException 事件的 OnUnhandledException 方法的关系图。](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>重写基方法

@No__t_0 方法定义 `Application` 方法的运行顺序。 默认情况下，Windows 窗体应用程序的 `Sub Main` 过程将调用 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 方法。

如果应用程序是普通的应用程序（多实例应用程序）或单实例应用程序的第一个实例，则 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> 方法按以下顺序执行 `Overridable` 方法：

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 默认情况下，此方法设置应用程序主线程（如果应用程序使用 Windows 身份验证）的视觉样式、文本显示样式和当前主体，如果 `/nosplash` 和 `-nosplash` 都不用作命令行参数，则调用 `ShowSplashScreen`。

     如果此函数返回 `False`，则将取消应用程序启动顺序。 在某些情况下，如果应用程序不应运行，这会很有用。

     @No__t_0 方法调用以下方法：

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> 确定应用程序是否定义了初始屏幕，如果是，则在单独的线程上显示初始屏幕。

         @No__t_0 方法包含的代码显示初始屏幕，其中至少显示了 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> 属性指定的毫秒数。 若要使用此功能，必须使用**项目设计器**将初始屏幕添加到应用程序（这会将 `My.Application.MinimumSplashScreenDisplayTime` 属性设置为两秒钟），或在重写 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> 或 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 方法的方法中设置 `My.Application.MinimumSplashScreenDisplayTime` 属性。 有关更多信息，请参见<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>。

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 允许设计器发出初始化初始屏幕的代码。

         默认情况下，此方法不执行任何操作。 如果在 Visual Basic**项目设计器**中为应用程序选择了初始屏幕，则设计器会使用一个方法来重写 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> 方法，该方法将 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> 属性设置为初始屏幕窗体的新实例。

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> 提供用于引发 `Startup` 事件的扩展点。 如果此函数返回 `False`，应用程序启动序列将停止。

     默认情况下，此方法会引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 事件。 如果事件处理程序将事件参数的 <xref:System.ComponentModel.CancelEventArgs.Cancel> 属性设置为 `True`，则该方法返回 `False` 以取消应用程序启动。

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> 提供初始化完成后主应用程序准备开始运行的起始点。

     默认情况下，在进入 Windows 窗体消息循环之前，此方法调用 `OnCreateMainForm` （创建应用程序的主窗体）并 `HideSplashScreen` （以关闭初始屏幕）方法：

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 为设计器提供发出初始化主窗体的代码的方法。

         默认情况下，此方法不执行任何操作。 但是，当你在 Visual Basic**项目设计器**中选择应用程序的主窗体时，设计器将使用一个方法来重写 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> 方法，该方法将 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> 属性设置为主窗体的新实例。

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> 如果应用程序定义了初始屏幕并且它已打开，则此方法将关闭初始屏幕。

         默认情况下，此方法会关闭初始屏幕。

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> 提供一种方法，用于自定义应用程序的另一个实例启动时单实例应用程序的行为方式。

     默认情况下，此方法会引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> 事件。

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> 提供用于引发 `Shutdown` 事件的扩展点。 如果主应用程序中出现未经处理的异常，则此方法不会运行。

     默认情况下，此方法会引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 事件。

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> 在上述任何一种方法中发生未经处理的异常时执行。

     默认情况下，只要调试器未附加并且应用程序正在处理 `UnhandledException` 事件，此方法就会引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 事件。

 如果应用程序为单实例应用程序，并且该应用程序已在运行，则应用程序的后续实例将对该应用程序的原始实例调用 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> 方法，然后退出。

 @No__t_0 构造函数调用 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 属性，以确定要用于应用程序窗体的文本呈现引擎。 默认情况下，<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 属性返回 `False`，指示使用的是 GDI 文本呈现引擎，这是 Visual Basic 2005 及更高版本中的默认值。 您可以重写 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> 属性以返回 `True`，这表示使用的是 GDI + 文本呈现引擎，这是 Visual Basic .NET 2002 和 Visual Basic .NET 2003 中的默认值。

## <a name="configuring-the-application"></a>配置应用程序
 作为 Visual Basic 应用程序模型的一部分，<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 类提供了用于配置应用程序的受保护的属性。 应在实现类的构造函数中设置这些属性。

 在默认 Windows 窗体项目中，**项目设计器**将创建代码以使用设计器设置来设置属性。 属性仅在应用程序启动时使用;在应用程序启动后设置它们不起作用。

|Property|4|项目设计器的 "应用程序" 窗格中的设置|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|应用程序是作为单实例还是多实例应用程序运行。|"**生成单个实例应用程序**" 复选框|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|如果应用程序将使用与 Windows XP 匹配的视觉样式，则为。|"**启用 XP 视觉样式**" 复选框|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|当应用程序退出时，应用程序自动保存应用程序的用户设置更改。|"**关闭时设置**" 复选框|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|导致应用程序终止的原因，如启动窗体关闭或最后一个窗体关闭时。|**关机模式**列表|

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Visual Basic 应用程序模型概述](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [“项目设计器”->“应用程序”页 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
