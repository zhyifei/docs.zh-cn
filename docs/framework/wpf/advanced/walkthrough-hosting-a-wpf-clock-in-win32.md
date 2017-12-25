---
title: "演练：在 Win32 中承载 WPF 时钟"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55e5aa633e3d788ac8acaa09684c92b8608e7cfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>演练：在 Win32 中承载 WPF 时钟
将[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]应用程序，使用<xref:System.Windows.Interop.HwndSource>，它提供了包含 HWND 你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容。 首先创建<xref:System.Windows.Interop.HwndSource>，并向其提供类似于 CreateWindow 的参数。  然后，通知<xref:System.Windows.Interop.HwndSource>有关[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]你要在其中包含内容。  最后，获取外的 HWND <xref:System.Windows.Interop.HwndSource>。 本演练阐释了如何创建混合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]重新实现操作系统的应用程序**日期和时间属性**对话框。  
  
## <a name="prerequisites"></a>先决条件  
 请参阅[WPF 和 Win32 间的互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)。  
  
## <a name="how-to-use-this-tutorial"></a>如何使用本教程  
 本教程重点介绍生成互操作应用程序的重要步骤。 本教程支持通过一个示例中， [Win32 时钟间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=160051)，但该示例是最终产品的反射。 本教程介绍的步骤，就像已启动与现有[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]你自己的项目，可能是一个预先存在的项目，和你正将添加一个承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]到你的应用程序。 你可以比较与你最终产品[Win32 时钟间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=160051)。  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Win32 中的 Windows Presentation Framework 的演练 (HwndSource)  
 下图显示了本教程的预期最终产品：  
  
 ![“日期和时间属性”对话框](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")  
  
 可以通过创建 c + + 重新创建此对话框[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目中[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，并使用对话框编辑器创建以下：  
  
 ![“日期和时间属性”对话框](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")  
  
 (不需要使用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]使用<xref:System.Windows.Interop.HwndSource>，且不需要使用 c + + 编写[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]程序，但这的相当典型的方式做到这一点，并且适于本身非常好的分步说明教程)。  
  
 您需要实现五个特定的子步骤才能将放置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟在对话框：  
  
1.  启用你[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目以调用托管的代码 (**/clr**) 通过更改中的项目设置[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]。  
  
2.  创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>中单独的 DLL。  
  
3.  将它放[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>内<xref:System.Windows.Interop.HwndSource>。  
  
4.  为此获取 HWND<xref:System.Windows.Controls.Page>使用<xref:System.Windows.Interop.HwndSource.Handle%2A>属性。  
  
5.  使用[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]来决定在何处放置在较大 HWND[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]应用程序  
  
## <a name="clr"></a>/clr  
 第一步是将此非托管[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目到一个可以调用托管代码。  使用 /clr 编译器选项，将其链接到你想要使用，并调整与一起使用的 Main 方法的所需 Dll [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  
  
 若要启用 c + + 项目中的托管代码的使用： win32clock 项目右键单击并选择**属性**。  上**常规**属性页 （默认值）、 公共语言运行时将支持更改为`/clr`。  
  
 接下来，添加对所需的 Dll 的引用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll、 PresentationFramework.dll、 System.dll、 WindowsBase.dll、 UIAutomationProvider.dll 和 UIAutomationTypes.dll。 （以下说明假定操作系统安装在 C: 驱动器上。）  
  
1.  右键单击 win32clock 项目并选择**引用...**，该对话框中：  
  
2.  右键单击 win32clock 项目并选择**引用...**.  
  
3.  单击**添加新引用**，单击浏览卡，输入 C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll，然后单击确定。  
  
4.  对 PresentationFramework.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll。  
  
5.  对 WindowsBase.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll。  
  
6.  对 UIAutomationTypes.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll。  
  
7.  对 UIAutomationProvider.dll 重复相同步骤：C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll。  
  
8.  单击**添加新引用**，选择 System.dll，然后单击**确定**。  
  
9. 单击**确定**退出 win32clock 属性页中添加引用。  
  
 最后，添加`STAThreadAttribute`到`_tWinMain`方法用于[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 此特性告知[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]，当它初始化[!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]，它应使用单线程的单元模型 (STA)，进行所需[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (和[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)])。  
  
## <a name="create-a-windows-presentation-framework-page"></a>创建 Windows Presentation Framework 页  
 接下来，创建一个 DLL，它定义[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>。 通常很容易创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>作为独立的应用程序，并编写并调试[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]部分通过这种方式。  完成后，该项目均可转换为 DLL，请右键单击该项目，单击**属性**，转到应用程序，并将输出类型更改为 Windows 类库。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]然后可以与组合 dll 项目[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目 （一个解决方案包含两个项目） – 右击该解决方案，选择**添加 \ 现有项目**。  
  
 使用该[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dll[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]项目中，你需要添加的引用：  
  
1.  右键单击 win32clock 项目并选择**引用...**.  
  
2.  单击**添加新引用**。  
  
3.  单击“项目”选项卡。选择 WPFClock，单击“确定”。  
  
4.  单击**确定**退出 win32clock 属性页中添加引用。  
  
## <a name="hwndsource"></a>HwndSource  
 接下来，使用<xref:System.Windows.Interop.HwndSource>以便[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>如下所示 HWND。  将此代码块添加到 C++ 文件中：  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 这是一长段代码，可以作一些解释。  第一部分是各种子句，无需完全限定所有调用：  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 然后，定义一个函数来创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容，将<xref:System.Windows.Interop.HwndSource>解决它，并返回 HWND:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 首先创建<xref:System.Windows.Interop.HwndSource>，其参数位于类似于 CreateWindow:  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 则你创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容类通过调用其构造函数：  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 然后连接到页<xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 和中的最后一行，返回的 HWND <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a>放置 Hwnd  
 既然你已包含 HWND[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟，你必须将在该 HWND[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]对话框。  如果你知道只需在何处放置 HWND，只需将该大小和位置`GetHwnd`前面定义的函数。  但是，由于已使用资源文件来定义对话框，因此你不完全确定任何 HWND 的放置位置。  你可以使用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]对话框编辑器将[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]静态控制想时钟转 （"插入时钟此处"），并使用它来定位[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟。  
  
 哪里处理 WM_INITDIALOG，因此，使用`GetDlgItem`占位符静态检索 HWND:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 您然后计算的大小和位置的占位符静态，以便您可以放入[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟在该位置：  
  
 RECT 矩形；  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 然后，你隐藏占位符 STATIC：  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 并创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟 HWND 在该位置：  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 使教程生动有趣，并生成一个真实[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]时钟，你将需要创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]此时时钟控件。 你可以在标记中执行大部分操作，代码隐藏中只有几个事件处理程序。 由于本教程是有关间的互操作而不是考虑控件的设计，完成代码[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供时钟此处代码块，而不离散说明如何生成或每个部分的含义。 随意尝试此代码来更改控件的外观或功能。  
  
 此处为标记：  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 以下是附带的代码隐藏：  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 最终结果如下所示：  
  
 ![“日期和时间属性”对话框](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")  
  
 若要比较的代码生成此屏幕截图中，你最终结果，请参阅[Win32 时钟间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=160051)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Interop.HwndSource>  
 [WPF 和 Win32 互操作](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Win32 时钟互操作示例](http://go.microsoft.com/fwlink/?LinkID=160051)
