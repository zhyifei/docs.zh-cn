---
title: 扩展 Visual Basic 应用程序模型
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 64c175216cf21b7947462cf79e4b88ab6fcd6d86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="extending-the-visual-basic-application-model"></a>扩展 Visual Basic 应用程序模型
你可以向应用程序模型添加功能，通过重写`Overridable`的成员<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>类。 此技术，可自定义应用程序模型的行为并添加对你自己的方法的调用，如应用程序启动和关闭。  
  
## <a name="visual-overview-of-the-application-model"></a>应用程序模型的视觉概览  
 本节直观地在 Visual Basic 应用程序模型提供函数调用的序列。 下一部分将描述详细信息中每个函数的用途。  
  
 下图显示正常的 Visual Basic Windows 窗体应用程序中的应用程序模型调用序列。 序列开始时`Sub Main`过程调用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>方法。  
  
 ![Visual Basic 应用程序模型&#45;&#45;运行](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 Visual Basic 应用程序模型还提供了<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>和<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>事件。 下图显示中用于引发这些事件的机制。  
  
 ![Visual Basic 应用程序模型&#45;&#45;下一步实例](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Visual Basic 应用程序模型的未经处理的异常](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>重写基方法  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>方法在其中定义顺序`Application`运行的方法。 默认情况下， `Sub Main` Windows 窗体应用程序的过程调用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>方法。  
  
 应用程序是否正常的应用程序 （多个实例应用程序） 或单实例应用程序的第一个实例<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>方法执行`Overridable`方法按以下顺序：  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>。 默认情况下，此方法设置的视觉样式、 文本显示样式和当前线程的主体主应用程序 （如果应用程序使用 Windows 身份验证），并调用`ShowSplashScreen`如果既没有`/nosplash`也不`-nosplash`用作命令行自变量。  
  
     如果此函数返回，则取消此应用程序启动序列`False`。 这可以在其中应用程序不应运行的情况下是否有用。  
  
     <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>方法调用以下方法：  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>。 确定应用程序是否具有定义的初始屏幕和如果是这样，在单独线程上显示初始屏幕。  
  
         <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>方法包含的代码显示初始屏幕的至少由指定的毫秒数<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>属性。 若要使用此功能，必须将初始屏幕添加到你的应用程序使用**项目设计器**(哪些集`My.Application.MinimumSplashScreenDisplayTime`属性设置为两秒)，或设置`My.Application.MinimumSplashScreenDisplayTime`替代的方法中的属性<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>或<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>方法。 有关详细信息，请参阅<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>。  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>。 允许设计器发出初始化初始屏幕的代码。  
  
         默认情况下，此方法没有任何影响。 如果你选择在 Visual Basic 中的应用程序初始屏幕**项目设计器**，设计器重写<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>方法与设置方法<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>初始屏幕窗体的新实例属性.  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>。 提供一个扩展点，用于引发`Startup`事件。 如果此函数返回，将停止应用程序启动序列`False`。  
  
     默认情况下，此方法将引发<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>事件。 如果事件处理程序将设置<xref:System.ComponentModel.CancelEventArgs.Cancel>属性的事件自变量`True`，该方法返回`False`取消应用程序启动。  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>。 当主应用程序已准备好开始运行，在初始化完成后提供起始点。  
  
     默认情况下，它将进入 Windows 窗体消息循环之前, 此方法调用`OnCreateMainForm`（用于创建应用程序的主窗体） 和`HideSplashScreen`（若要关闭初始屏幕） 方法：  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>。 提供为设计器发出初始化主窗体的代码的方法。  
  
         默认情况下，此方法没有任何影响。 但是，当你选择主窗体应用程序在 Visual Basic 中**项目设计器**，设计器重写<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>方法与设置方法<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>到主窗体的新实例的属性。  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>。 如果应用程序定义的初始屏幕，并且它已打开，则此方法关闭初始屏幕。  
  
         默认情况下，此方法关闭初始屏幕。  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>。 使您能够自定义应用程序的另一个实例启动时，单实例应用程序的行为方式。  
  
     默认情况下，此方法将引发<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>事件。  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>。 提供一个扩展点，用于引发`Shutdown`事件。 如果在主应用程序中出现未经处理的异常，此方法不会运行。  
  
     默认情况下，此方法将引发<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>事件。  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>。 如果未经处理的异常发生则任何上面列出的方法中，执行。  
  
     默认情况下，此方法将引发<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>前提是不连接调试器并处理应用程序的事件`UnhandledException`事件。  
  
 如果应用程序是单实例应用程序，并且已运行应用程序，应用程序的后续实例调用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>方法的原始实例应用程序，然后退出。  
 
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)>构造函数调用<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>属性来确定要用于应用程序的窗体的文本呈现引擎。 默认情况下，<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>属性返回`False`，这是中的默认值，该值指示使用 GDI 文本呈现引擎， [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]。 您可以重写<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>属性以返回`True`，这指示使用 GDI + 文本呈现引擎，这是在 Visual Basic.NET 2002年和 Visual Basic.NET 2003年中的默认设置。  
  
## <a name="configuring-the-application"></a>配置应用程序  
 Visual Basic 应用程序模型中，一部分<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering>类提供的配置应用程序的受保护的属性。 应在实现类的构造函数中设置这些属性。  
  
 在默认 Windows 窗体项目中，**项目设计器**创建代码来设置与设计器设置的属性。 仅当应用程序正在启动; 时，将使用属性应用程序启动后将其设置不起作用。  
  
|属性|确定|在项目设计器的应用程序窗格中的设置|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|是否作为一个单实例或多个实例应用程序将运行应用程序。|**使单个实例的应用程序**复选框|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|如果应用程序将使用匹配 Windows XP 的视觉样式。|**启用 XP 视觉样式**复选框|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|如果应用程序退出时，应用程序自动保存应用程序的用户设置更改。|**在关闭上保存 My.Settings**复选框|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|什么因素会导致应用程序终止，如启动窗体关闭时或当最后一个窗体关闭。|**关闭模式**列表|  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 [Visual Basic 应用程序模型概述](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 [“项目设计器”->“应用程序”页 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
