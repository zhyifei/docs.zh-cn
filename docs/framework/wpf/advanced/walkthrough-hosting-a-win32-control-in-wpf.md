---
title: 在 WPF 中托管 Win32 控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 5185e60640c652b79bd105db54830ac3acc57129
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186738"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>演练：在 WPF 中托管 Win32 控件
Windows 演示基础 （WPF） 为创建应用程序提供了丰富的环境。 但是，当您对 Win32 代码进行大量投资时，在 WPF 应用程序中至少重用其中一些代码，而不是完全重写它可能更有效。 WPF 提供了一种在 WPF 页面上托管 Win32 窗口的简单机制。  
  
 本主题将引导您完成一个应用程序，[在 WPF 示例中托管 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)，该应用程序托管 Win32 列表框控件。 此常规过程可以扩展到托管任何 Win32 窗口。  

<a name="requirements"></a>
## <a name="requirements"></a>要求  
 本主题假定对 WPF 和 Windows API 编程基本熟悉。 有关 WPF 编程的基本介绍，请参阅[入门](../getting-started/index.md)。 有关 Windows API 编程的介绍，请参阅有关该主题的众多书籍中的任何一本书，特别是查尔斯·佩佐德的*编程 Windows。*  
  
 由于本主题附带的示例在 C# 中实现，因此它利用平台调用服务 （PInvoke） 访问 Windows API。 对 PInvoke 的熟悉是有帮助的，但不是必须的。  
  
> [!NOTE]
> 本主题包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 您可以在[WPF 示例中从承载 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)获取或查看完整的代码。  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>基本过程  
 本节概述了在 WPF 页面上托管 Win32 窗口的基本过程。 其余各节介绍了每个步骤的详细内容。  
  
 基本的承载步骤如下：  
  
1. 实现 WPF 页以承载窗口。 一种技术是创建一<xref:System.Windows.Controls.Border>个元素来为托管窗口保留页面的一部分。  
  
2. 实现类以承载从<xref:System.Windows.Interop.HwndHost>继承的控件。  
  
3. 在该类中<xref:System.Windows.Interop.HwndHost>，重写类成员<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>。  
  
4. 将托管窗口创建为包含 WPF 页的窗口的子窗口。 尽管传统的 WPF 编程不需要显式使用它，但托管页是具有句柄 （HWND） 的窗口。 通过`hwndParent`<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>方法的参数接收页面 HWND。 应将所承载的窗口创建为此 HWND 的子窗口。  
  
5. 在创建宿主窗口之后，返回所承载的窗口的 HWND。 如果要承载一个或多个 Win32 控件，通常创建主机窗口作为 HWND 的子级，并创建该主机窗口的控件子级。 在主机窗口中包装控件为 WPF 页提供了一种从控件接收通知的简单方法，该控件处理 HWND 边界通知的一些特定 Win32 问题。  
  
6. 处理发送到宿主窗口的选定消息，例如，来自子控件的通知。 可通过两种方式来执行此操作。  
  
    - 如果希望处理托管类中的消息，请重写<xref:System.Windows.Interop.HwndHost.WndProc%2A><xref:System.Windows.Interop.HwndHost>类的方法。  
  
    - 如果希望 WPF 处理消息，请处理代码后面的<xref:System.Windows.Interop.HwndHost>类<xref:System.Windows.Interop.HwndHost.MessageHook>事件。 对于所承载的窗口收到的每条消息，都将发生此事件。 如果选择此选项，则仍必须重写<xref:System.Windows.Interop.HwndHost.WndProc%2A>，但只需要最少的实现。  
  
7. 重写<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>的<xref:System.Windows.Interop.HwndHost.WndProc%2A>和<xref:System.Windows.Interop.HwndHost> 您必须重写这些方法才能满足协定，<xref:System.Windows.Interop.HwndHost>但可能只需要提供最少的实现。  
  
8. 在代码背后的文件中，创建控件宿主类的实例，并将其使其成为旨在承载窗口<xref:System.Windows.Controls.Border>的元素的子级。  
  
9. 通过向托管窗口发送 Microsoft Windows 消息并处理来自其子窗口的消息（如控件发送的通知）与托管窗口通信。  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>实现页面布局  
 承载 ListBox 控件的 WPF 页的布局由两个区域组成。 页面的左侧承载多个 WPF 控件，这些控件提供[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]允许您操作 Win32 控件的 控件。 页面右上角具有一个正方形区域，用于放置所承载的 ListBox 控件。  
  
 实现此布局的代码非常简单。 根元素是<xref:System.Windows.Controls.DockPanel>具有两个子元素的 。 第一个是<xref:System.Windows.Controls.Border>承载 ListBox 控件的元素。 它在该页的右上角占据了一个大小为 200x200 的正方形。 第二个是包含<xref:System.Windows.Controls.StackPanel>一组 WPF 控件的元素，该控件显示信息，并允许您通过设置公开的互操作属性来操作 ListBox 控件。 对于 的每个元素都是<xref:System.Windows.Controls.StackPanel>的子元素，请参阅用于详细介绍这些元素是什么或它们做什么的各种元素的参考材料，这些元素列在下面的示例代码中，但此处不会解释（基本互操作模型不需要其中任何元素，它们提供是为了向示例添加一些交互性）。  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>实现类以承载 Microsoft Win32 控件  
 此示例的核心是实际承载控件的类，即 ControlHost.cs。 它继承自 <xref:System.Windows.Interop.HwndHost>。 构造函数采用两个参数，高度和宽度，对应于承载 ListBox 控件<xref:System.Windows.Controls.Border>的元素的高度和宽度。 这些值稍后用于确保控件的大小与<xref:System.Windows.Controls.Border>元素匹配。  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 还有一组常量。 这些常量大部分取自 Winuser.h，允许您在调用 Win32 函数时使用传统名称。  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>替代 BuildWindowCore 以创建 Microsoft Win32 窗口  
 重写此方法以创建将由页面承载的 Win32 窗口，并在窗口和页面之间建立连接。 由于此示例涉及承载 ListBox 控件，因此将创建两个窗口。 第一个是 WPF 页实际承载的窗口。 ListBox 控件被创建为该窗口的子窗口。  
  
 采用此方法的原因是为了简化接收来自控件的通知的过程。 该<xref:System.Windows.Interop.HwndHost>类允许您处理发送到它所承载的窗口的消息。 如果直接承载 Win32 控件，则会收到发送到控件的内部消息循环的消息。 你可以显示控件并向其发送消息，但不会收到该控件发送到其父窗口的通知。 这意味你没有办法检测用户何时与该控件进行交互，以及其他更多方面。 可改为创建一个宿主窗口，并使控件成为该窗口的子窗口。 这样，你便能够处理宿主窗口的消息，包括由该控件发送给它的通知。 由于宿主窗口只是控件的一个简单包装器而已，为了方便起见，以后将把该包称为 ListBox 控件。  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>创建宿主窗口和 ListBox 控件  
 可以使用 PInvoke 通过创建和注册窗口类等为控件创建主机窗口。 但是，更简单的一种方法是使用预定义的“静态”窗口类创建窗口。 这将为你提供所需窗口步骤，以接收来自控件的通知，但需要完成最少的编码工作。  
  
 控件的 HWND 通过一个只读属性公开，以便宿主页面可使用它向控件发送消息。  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 ListBox 控件被创建为宿主窗口的子窗口。 两个窗口的高度和宽度被设置为传递给构造函数的值（前面已讨论）。 这可确保宿主窗口和控件的大小与页面上的保留区域相同。  创建窗口后，该示例将返回包含<xref:System.Runtime.InteropServices.HandleRef>主机窗口的 HWND 的对象。  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>实现 DestroyWindow 和 WndProc  
 除了 之外<xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>，还必须重写 的<xref:System.Windows.Interop.HwndHost.WndProc%2A><xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A><xref:System.Windows.Interop.HwndHost>和 方法。 在此示例中，控件的消息由<xref:System.Windows.Interop.HwndHost.MessageHook>处理程序处理，因此 ，<xref:System.Windows.Interop.HwndHost.WndProc%2A><xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>的实现是最小的。 在 中<xref:System.Windows.Interop.HwndHost.WndProc%2A>，设置为`handled``false`指示消息未处理，并返回 0。 对于<xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>，只需破坏窗口。  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>在页面上承载控件  
 要在页面上承载控件，请首先创建`ControlHost`类的新实例。 将包含控件 （`ControlHostElement`） 的边框元素的高度和宽度传递给`ControlHost`构造函数。 这可确保 ListBox 具有正确的大小。 然后，通过将对象`ControlHost`<xref:System.Windows.Controls.Decorator.Child%2A>分配给主机<xref:System.Windows.Controls.Border>的属性，在页面上托管控件。  
  
 该示例将处理程序附加到<xref:System.Windows.Interop.HwndHost.MessageHook>`ControlHost`要从控件接收消息的事件。 对于每条发送到宿主窗口的消息，都将引发此事件。 在这种情况下，这些消息是发送到包装实际 ListBox 控件的窗口的消息，其中包括来自控件的通知。 此示例将调用 SendMessage 以从控件获取信息并修改其内容。 下一节将详细介绍页面如何与控件通信。  
  
> [!NOTE]
> 请注意，有两个 PInvoke 声明用于发送消息。 这是必需的，因为一个使用`wParam`参数传递字符串，另一个使用它传递整数。 对于每个签名，都需要一个单独的声明，以确保正确封送数据。  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>在控件和页面之间的实现通信  
 通过向控件发送 Windows 消息来操作该控件。 当用户与控件交互时，控件会通过向其宿主窗口发送通知来通知你。 [在 WPF 示例中托管 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)包括一个 UI，它提供了几个示例，说明其工作原理：  
  
- 向列表中追加项。  
  
- 从列表中删除选定项  
  
- 显示当前选定项的文本。  
  
- 显示列表中的项数。  
  
 用户还可以通过单击列表框中的项目来选择该项目，就像对于传统的 Win32 应用程序一样。 每当用户通过选择、添加或追加项来更改列表框的状态时，都将更新所显示的数据。  
  
 要追加项目，请将列表框发送[`LB_ADDSTRING`一条消息](/windows/desktop/Controls/lb-addstring)。 要删除项目，请[`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel)发送以获取当前选择的索引，然后[`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring)删除该项目。 该示例还发送[`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)，并使用返回的值更新显示项数的显示。 这两个实例[`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage)都使用上一节中讨论的 PInvoke 声明之一。  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 当用户选择项目或更改其选择时，控件通过向宿主窗口[`WM_COMMAND`发送消息来通知](/windows/desktop/menurc/wm-command)主机窗口，这将引发页面<xref:System.Windows.Interop.HwndHost.MessageHook>的事件。 处理程序将接收到与宿主窗口的主窗口过程相同的信息。 它还传递对布尔值的`handled`引用。 您设置为`handled``true`指示已处理消息，无需进一步处理。  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command)发送的原因有多种，因此您必须检查通知 ID 以确定它是否是您希望处理的事件。 ID 包含在`wParam`参数的高字中。 该示例使用位运算符提取 ID。 如果用户已创建或更改其选择，则 ID 将为[`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)。  
  
 收到[`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)时，示例通过向控件[`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel)发送消息来获取所选项的索引。 要获取文本，请首先创建 一<xref:System.Text.StringBuilder>个 。 然后，向控件[`LB_GETTEXT`发送消息。](/windows/desktop/Controls/lb-gettext) 将空<xref:System.Text.StringBuilder>对象作为参数传递`wParam`。 返回[`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage)时，<xref:System.Text.StringBuilder>将包含所选项的文本。 这种使用[`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage)需要另一个 PInvoke 声明。  
  
 最后，设置为`handled``true`指示消息已处理。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndHost>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
- [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
