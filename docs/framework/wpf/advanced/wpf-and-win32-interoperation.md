---
title: WPF 和 Win32 互操作
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 8a0e27d46248bdfd782c2cf650faaf8f3bc29960
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="wpf-and-win32-interoperation"></a>WPF 和 Win32 互操作
本主题概述如何互操作 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 代码。 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，如果对 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 代码投入很大，重复使用部分此代码可能更有效。  
  

  
<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>WPF 和 Win32 互操作基础知识  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 代码间的互操作存在两种基本方法。  
  
-   在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 内容。 通过此方法，可在标准 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口和应用程序的框架内使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的高级图形功能。  
  
-   在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口。 通过此方法，可在其他 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的上下文中使用现有自定义 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 控件，并可跨边界传递数据。  
  
 本主题中对上述每种方法进行了概念性介绍。 有关在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的更具有代码针对性的说明，请参阅[演练：在 Win32 中承载 WPF 内容](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)。 有关在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中承载 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 的更具代码针对性的说明，请参阅[演练：在 WPF 中承载 Win32 控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)。  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>WPF 互操作项目  
 虽然 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 为托管代码，但大多数现有 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 程序是以非托管 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 编写而成。  无法从真正的非托管程序调用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]。 但是，通过使用 [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] 编译器的 `/clr` 选项，可创建托管与非托管混合的程序，在此程序中可无缝混合托管和非托管 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 调用。  
  
 存在的一个项目级问题是无法将 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件编译到 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 项目中。  可通过一些项目分离技术对此进行弥补。  
  
-   创建 C# DLL 包含所有你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]页为编译的程序集，然后让你[!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)]可执行文件包括[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]作为引用。  
  
-   创建 C# 的可执行文件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容，并将其引用[!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)][!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]包含[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]内容。  
  
-   使用<xref:System.Windows.Markup.XamlReader.Load%2A>加载任何[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在运行时，而不是编译你[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
-   不要使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，和写入所有你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]在代码中，从在元素树中向上生成<xref:System.Windows.Application>。  
  
 请使用最适合你的方法。  
  
> [!NOTE]
>  如果之前未使用过 [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]，在互操作代码示例中你可能会看到 `gcnew` 和 `nullptr` 等一些“新”关键字。 这些关键字取代旧版双下划线语法 (`__gc`)，为 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 中的托管代码提供了更加自然的语法。  若要详细了解 [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] 托管功能，请参阅[适用于运行时平台的组件扩展](/cpp/windows/component-extensions-for-runtime-platforms)和[了解 C++/CLI](http://go.microsoft.com/fwlink/?LinkId=98739)。  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>WPF 如何使用 Hwnd  
 若要充分利用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]“HWND 互操作”，需要了解 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 如何使用 HWND。 对于任何 HWND，无法将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 绘制与 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 绘制或 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] 绘制混合。 这具有许多影响。 首先，若要混合这些绘制模型，必须创建互操作解决方案，并对选择使用的每个绘制模型使用互操作的指定段。 此外，绘制行为会为互操作解决方案可实现的操作创建一个“空域”限制。 有关“空域”概念的详细信息，请参见[技术区概述](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)主题。  
  
 屏幕上的所有 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素最终受 HWND 支持。 当你创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]创建顶级 HWND，并使用<xref:System.Windows.Interop.HwndSource>将<xref:System.Windows.Window>及其[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]HWND 中的内容。  应用程序中的其余 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容共享单个 HWND。 菜单、组合框下拉列表和其他弹出窗口例外。 这些元素会创建自己的顶层窗口，因此 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 菜单可能超出所在窗口 HWND 的边缘。 当你使用<xref:System.Windows.Interop.HwndHost>将内部 HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通知[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]如何定位到的新子 HWND 相对[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND。  
  
 与之相关的 HWND 概念是每个 HWND 内及其之间的透明度。 [技术区概述](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)主题中对此也有相关介绍。  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>在 Microsoft Win32 窗口中承载 WPF 内容  
 承载的关键[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]上[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口<xref:System.Windows.Interop.HwndSource>类。 此类在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 窗口中包装 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容，以便 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容可作为子窗口并入 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 以下方法在单个应用程序中合并 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  
  
1.  将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容（内容根元素）作为托管类实现。 通常情况下，类继承自的类可以包含多个子元素和/或使用的根元素，如之一<xref:System.Windows.Controls.DockPanel>或<xref:System.Windows.Controls.Page>。 后续步骤中，此类被称为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类，此类的实例被称为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象。  
  
2.  使用 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 实现 [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)] 应用程序。 若要以现有非托管 [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] 应用程序开始，可更改项目设置将 `/clr` 编译器标志包括在内，以此来允许应用程序调用托管代码（本主题中未介绍支持 `/clr` 编译可能所需内容的完整范围）。  
  
3.  将线程处理模型设置为单线程单元 (STA)。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 使用此线程模型。  
  
4.  处理窗口过程中的 WM_CREATE 通知。  
  
5.  在处理程序（或处理程序调用的函数）中，执行以下操作：  
  
    1.  创建一个新<xref:System.Windows.Interop.HwndSource>与父窗口 HWND 对象作为其`parent`参数。  
  
    2.  创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类的一个实例。  
  
    3.  为分配一个引用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]到的内容对象<xref:System.Windows.Interop.HwndSource>对象<xref:System.Windows.Interop.HwndSource.RootVisual%2A>属性。  
  
    4.  <xref:System.Windows.Interop.HwndSource>对象<xref:System.Windows.Interop.HwndSource.Handle%2A>属性包含的窗口句柄 (HWND)。 要获取可在应用程序的非托管部分中使用的 HWND，需将 `Handle.ToPointer()` 强制装换为 HWND。  
  
6.  实现一个托管类，该类包含一个用于保存对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的引用的静态字段。 此类允许你获取对引用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容对象从你[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]代码，但是更为重要的是它可以防止你<xref:System.Windows.Interop.HwndSource>无意中进行垃圾回收。  
  
7.  通过将处理程序附加到一个或多个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象事件，接收 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象的通知。  
  
8.  通过使用存储在静态字段中的引用设置属性、调用方法等，与 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容对象进行通信。  
  
> [!NOTE]
>  如果生成一个单独的程序集然后对其进行引用，对于步骤 1，可使用内容类的默认分部类在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中完成部分或全部 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容类定义。 尽管通常包括<xref:System.Windows.Application>对象作为编译的一部分[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]成一个程序集，你没有停止使用该<xref:System.Windows.Application>作为间的互操作的一部分，你只需使用一个或多个用于根类[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]引用的文件到应用程序和引用其分部类。 该过程的其余部分基本与上述相似。  
>   
>  [演练：在 Win32 中承载 WPF 内容](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)主题中对这些每个步骤通过代码进行了说明。  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>在 WPF 中承载 Microsoft Win32 窗口  
 承载的关键[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口在其他[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容<xref:System.Windows.Interop.HwndHost>类。 该类在可添加到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素树的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素中包装窗口。 <xref:System.Windows.Interop.HwndHost> 此外支持[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]可用于执行任务，如所承载的窗口的处理消息。 基本过程：  
  
1.  为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序创建一个元素树（可通过代码或标记）。 元素树中查找合适且允许点其中<xref:System.Windows.Interop.HwndHost>实现可以作为子元素添加。 剩余步骤中，此元素称为保留元素。  
  
2.  派生自<xref:System.Windows.Interop.HwndHost>以创建对象包含你[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]内容。  
  
3.  在该主机类，重写<xref:System.Windows.Interop.HwndHost>方法<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>。 返回承载窗口的 HWND。 可能需要将实际控件包装为返回窗口的子窗口；在承载窗口中包装控件为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容从控件接收通知提供了一种简单的方式。 此方法有助于更正一些有关主机控件边界处消息处理的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 问题。  
  
4.  重写<xref:System.Windows.Interop.HwndHost>方法<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>和<xref:System.Windows.Interop.HwndHost.WndProc%2A>。 这样做的目的是处理清除和删除对承载内容的引用，尤其是在已创建对非托管对象的引用的情况下。  
  
5.  在代码隐藏文件中，创建控件承载类的一个实例，并使其成为保留元素的子元素。 通常将使用事件处理程序如<xref:System.Windows.FrameworkElement.Loaded>，或使用分部类构造函数。 但也可通过运行时行为添加互操作内容。  
  
6.  处理选择的窗口消息，例如控件通知。 方法有两种。 两种方法提供对消息流的相同访问权限，因此你的选择很大程度上取决于编程简便性。  
  
    -   实现消息处理中的所有消息 （而不仅仅是关闭消息） 的重写<xref:System.Windows.Interop.HwndHost>方法<xref:System.Windows.Interop.HwndHost.WndProc%2A>。  
  
    -   让承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]元素处理的消息，处理<xref:System.Windows.Interop.HwndHost.MessageHook>事件。 对发送到承载窗口的主窗口过程的每个消息都会引发该事件。  
  
    -   无法处理来自超出进程使用的 windows 消息<xref:System.Windows.Interop.HwndHost.WndProc%2A>。  
  
7.  通过使用平台调用来调用非托管 `SendMessage` 函数，与承载窗口通信。  
  
 按照这些步骤，创建一个处理鼠标输入的应用程序。 可以通过实现为承载的窗口添加跳格支持<xref:System.Windows.Interop.IKeyboardInputSink>接口。  
  
 [演练：在 WPF 中承载 Win32 控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)主题中对这些每个步骤通过代码进行了说明。  
  
### <a name="hwnds-inside-wpf"></a>WPF 内部的 Hwnd  
 你可以将<xref:System.Windows.Interop.HwndHost>为特殊控件。 (从技术上讲，<xref:System.Windows.Interop.HwndHost>是<xref:System.Windows.FrameworkElement>不派生类，<xref:System.Windows.Controls.Control>派生类，但它可以将其视为出于间的互操作的控件。)<xref:System.Windows.Interop.HwndHost>提取基础[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]性质所承载的内容以便的其余部分[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]考虑所承载的内容，为另一个类似于控件的对象，它应呈现并处理输入。 <xref:System.Windows.Interop.HwndHost> 行为通常类似于任何其他[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>，但有一些重要差异围绕输出 （绘制和图形） 和基于基础 Hwnd 的限制的输入 （鼠标和键盘） 可以支持。  
  
#### <a name="notable-differences-in-output-behavior"></a>输出行为的显著差异  
  
-   <xref:System.Windows.FrameworkElement>即<xref:System.Windows.Interop.HwndHost>基类、 具有相当多的属性，表示对 UI 的更改。 这些属性包括如<xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>的更改中该元素作为父级的元素的布局。 但是，这些属性大多数未映射到可能的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 等效项（即使这类等效项可能存在）。 过多这些属性及其含义具有过高的绘制技术针对性，这使得映射并不可行。 因此，如设置属性<xref:System.Windows.FrameworkElement.FlowDirection%2A>上<xref:System.Windows.Interop.HwndHost>不起作用。  
  
-   <xref:System.Windows.Interop.HwndHost> 不能为旋转、 缩放、 有偏差，或以其他方式受转换。  
  
-   <xref:System.Windows.Interop.HwndHost> 不支持<xref:System.Windows.UIElement.Opacity%2A>（alpha 混合） 的属性。 如果内容在<xref:System.Windows.Interop.HwndHost>执行<xref:System.Drawing>包含所本身就不算违规，alpha 信息的操作但<xref:System.Windows.Interop.HwndHost>因为整个仅支持不透明度 = 1.0 （100%)。  
  
-   <xref:System.Windows.Interop.HwndHost> 将显示在其他之上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]相同的顶级窗口中的元素。 但是，<xref:System.Windows.Controls.ToolTip>或<xref:System.Windows.Controls.ContextMenu>生成的菜单是单独的顶级窗口，并且因此的行为正确与<xref:System.Windows.Interop.HwndHost>。  
  
-   <xref:System.Windows.Interop.HwndHost> 不遵从其父级的剪辑区域<xref:System.Windows.UIElement>。 这可能是问题，如果你尝试将<xref:System.Windows.Interop.HwndHost>滚动区域内的类或<xref:System.Windows.Controls.Canvas>。  
  
#### <a name="notable-differences-in-input-behavior"></a>输入行为的显著差异  
  
-   通常，而输入的设备的作用域内<xref:System.Windows.Interop.HwndHost>托管[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]区域中，输入的事件直接转到[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]。  
  
-   鼠标位于<xref:System.Windows.Interop.HwndHost>，你的应用程序不会收到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]鼠标事件和的值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性<xref:System.Windows.UIElement.IsMouseOver%2A>将`false`。  
  
-   虽然<xref:System.Windows.Interop.HwndHost>具有键盘焦点，你的应用程序将不会收到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]键盘事件和的值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]属性<xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>将`false`。  
  
-   当焦点是否位于内<xref:System.Windows.Interop.HwndHost>和更改到另一个控件内<xref:System.Windows.Interop.HwndHost>，你的应用程序将不会收到[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]事件<xref:System.Windows.UIElement.GotFocus>或<xref:System.Windows.UIElement.LostFocus>。  
  
-   相关触笔属性和事件类似，并且不报告信息时该触笔位于<xref:System.Windows.Interop.HwndHost>。  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>Tab 键、助记键和加速键  
 <xref:System.Windows.Interop.IKeyboardInputSink>和<xref:System.Windows.Interop.IKeyboardInputSite>接口使你可以创建无缝键盘体验，为混合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]和[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]应用程序：  
  
-   [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 和 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 组件之间的 Tab 键  
  
-   焦点位于 Win32 组件内和 WPF 组件内时皆起作用的助记键和加速键。  
  
 <xref:System.Windows.Interop.HwndHost>和<xref:System.Windows.Interop.HwndSource>类都提供的实现<xref:System.Windows.Interop.IKeyboardInputSink>，但它们可能不会处理用于更高级方案所需的所有输入的消息。 替换为适当方法，获取所需的键盘行为。  
  
 接口仅对 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 和 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 区域间的转换过程中发生的事件提供支持。 在 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 区域内，Tab 键行为完全受 Tab 键的 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 实现逻辑（若有）控制。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Interop.HwndHost>  
 <xref:System.Windows.Interop.HwndSource>  
 <xref:System.Windows.Interop>  
 [演练：在 WPF 中托管 Win32 控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)  
 [演练：在 Win32 中承载 WPF 内容](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)
