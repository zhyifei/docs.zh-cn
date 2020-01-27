---
title: 承载 Win32 内容
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: b3113d9f3146e1590363dc9db6f751a429dda74b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747011"
---
# <a name="hosting-win32-content-in-wpf"></a>在 WPF 中承载 Win32 内容

## <a name="prerequisites"></a>先决条件

请参阅[WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)。

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Windows Presentation Framework 中的 Win32 演练（System.windows.interop.hwndhost>）

若要在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中重复使用 Win32 内容，请使用 <xref:System.Windows.Interop.HwndHost>，这是使 Hwnd 类似于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的控件。 与 <xref:System.Windows.Interop.HwndSource>一样，<xref:System.Windows.Interop.HwndHost> 简单易用：从 <xref:System.Windows.Interop.HwndHost> 派生并实现 `BuildWindowCore` 和 `DestroyWindowCore` 方法，然后实例化 <xref:System.Windows.Interop.HwndHost> 派生类并将其放置在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序内。

如果已将您的 Win32 逻辑打包为控件，则您的 `BuildWindowCore` 实现几乎不会调用 `CreateWindow`。 例如，若要在中C++创建 Win32 LISTBOX 控件：

```cpp
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {
    HWND handle = CreateWindowEx(0, L"LISTBOX",
    L"this is a Win32 listbox",
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY
    | WS_VSCROLL | WS_BORDER,
    0, 0, // x, y
    30, 70, // height, width
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd
    0, // hmenu
    0, // hinstance
    0); // lparam

    return HandleRef(this, IntPtr(handle));
}

virtual void DestroyWindowCore(HandleRef hwnd) override {
    // HwndHost will dispose the hwnd for us
}
```

但是，假设 Win32 代码不是很容易自包含？ 如果是这样，则可以创建一个 Win32 对话框，并将其内容嵌入更大的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。 此示例在 Visual Studio 和C++中显示了这种情况，虽然也可以使用不同的语言或在命令行中执行此操作。

首先，使用一个简单的对话框，该对话框编译C++为 DLL 项目。

接下来，将对话框引入更大的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序：

- 将 DLL 编译为托管（`/clr`）

- 将对话框变为控件

- 用 `BuildWindowCore` 和 `DestroyWindowCore` 方法定义 <xref:System.Windows.Interop.HwndHost> 的派生类

- 重写 `TranslateAccelerator` 方法来处理对话框键

- 重写 `TabInto` 方法以支持 tab 键

- 重写 `OnMnemonic` 方法以支持助记键

- 实例化 <xref:System.Windows.Interop.HwndHost> 子类，并将其放在右侧 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素的下方

### <a name="turn-the-dialog-into-a-control"></a>将对话框变为控件

您可以使用 WS_CHILD 和 DS_CONTROL 样式将对话框转换为子 HWND。 进入对话框定义的资源文件（.rc），并找到对话框定义的开头：

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

将第二行更改为：

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

此操作不会将其完全打包到独立的控件中;你仍需要调用 `IsDialogMessage()` 因此 Win32 可以处理某些消息，但是控件更改的确提供了将这些控件放在其他 HWND 中的一种简单方法。

## <a name="subclass-hwndhost"></a>子类 System.windows.interop.hwndhost>

导入下列命名空间：

```cpp
namespace ManagedCpp
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Input;
    using namespace System::Windows::Media;
    using namespace System::Runtime::InteropServices;
```

然后创建 <xref:System.Windows.Interop.HwndHost> 的派生类，并重写 `BuildWindowCore` 和 `DestroyWindowCore` 方法：

```cpp
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {
    private:
        HWND dialog;

    protected:
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {
            InitializeGlobals();
            dialog = CreateDialog(hInstance,
                MAKEINTRESOURCE(IDD_DIALOG1),
                (HWND) hwndParent.Handle.ToPointer(),
                (DLGPROC) About);
            return HandleRef(this, IntPtr(dialog));
        }

        virtual void DestroyWindowCore(HandleRef hwnd) override {
            // hwnd will be disposed for us
        }
```

在这里，可以使用 `CreateDialog` 创建真正是控件的对话框。 由于这是在 DLL 中调用的第一个方法，因此还应通过调用稍后定义的函数（称为 `InitializeGlobals()`）来执行一些标准 Win32 初始化：

```cpp
bool initialized = false;
    void InitializeGlobals() {
        if (initialized) return;
        initialized = true;

        // TODO: Place code here.
        MSG msg;
        HACCEL hAccelTable;

        // Initialize global strings
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);
        MyRegisterClass(hInstance);
```

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>重写 TranslateAccelerator 方法以处理对话框键

如果现在运行此示例，您将看到一个对话框控件，该控件将显示，但会忽略使对话框成为功能对话框的所有键盘处理。 你现在应该重写 `TranslateAccelerator` 实现（来自 `IKeyboardInputSink`，这是 <xref:System.Windows.Interop.HwndHost> 实现的接口）。 当应用程序收到 WM_KEYDOWN 和 WM_SYSKEYDOWN 时，将调用此方法。

```cpp
#undef TranslateAccelerator
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
            ModifierKeys modifiers) override
        {
            ::MSG m = ConvertMessage(msg);

            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know
            // what to do when it reaches the last tab stop
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
                TraversalRequest^ request = nullptr;

                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {
                    // this code should work, but there’s a bug with interop shift-tab in current builds
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);
                }
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);
                }

                if (request != nullptr)
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);

            }

            // Only call IsDialogMessage for keys it will do something with.
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {
                switch (m.wParam) {
                    case VK_TAB:
                    case VK_LEFT:
                    case VK_UP:
                    case VK_RIGHT:
                    case VK_DOWN:
                    case VK_EXECUTE:
                    case VK_RETURN:
                    case VK_ESCAPE:
                    case VK_CANCEL:
                        IsDialogMessage(dialog, &m);
                        // IsDialogMessage should be called ProcessDialogMessage --
                        // it processes messages without ever really telling you
                        // if it handled a specific message or not
                        return true;
                }
            }

            return false; // not a key we handled
        }
```

这是一个部分中的大量代码，因此它可以使用一些更详细的解释。 首先，使用C++和C++宏的代码;需要注意的是在 winuser.h 中定义的名为 `TranslateAccelerator`的宏：

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

因此，请确保定义 `TranslateAccelerator` 方法，而不是 `TranslateAcceleratorW` 方法。

同样，还存在非托管的 winuser.h 消息和托管 `Microsoft::Win32::MSG` 结构。 您可以使用C++ `::` 运算符来消除这两者之间的歧义。

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}

Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:

```cpp
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {
    ::MSG m;
    m.hwnd = (HWND) msg.hwnd.ToPointer();
    m.lParam = (LPARAM) msg.lParam.ToPointer();
    m.message = msg.message;
    m.wParam = (WPARAM) msg.wParam.ToPointer();

    m.time = msg.time;

    POINT pt;
    pt.x = msg.pt_x;
    pt.y = msg.pt_y;
    m.pt = pt;

    return m;
}
```

返回 `TranslateAccelerator`。 基本原则是调用 Win32 函数 `IsDialogMessage` 来执行尽可能多的工作，但 `IsDialogMessage` 无权访问对话框以外的任何内容。 在对话框周围的 "用户" 选项卡上，当 tab 键在对话框中的最后一个控件之后运行时，需要通过调用 `IKeyboardInputSite::OnNoMoreStops`将焦点设置到 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 部分。

```cpp
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know
// what to do when it reaches the last tab stop
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
    TraversalRequest^ request = nullptr;

    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);
    }
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);
    }

    if (request != nullptr)
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);
}
```

最后，调用 `IsDialogMessage`。 但 `TranslateAccelerator` 方法的责任之一就是告诉 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 是否已处理击键。 如果未处理，输入事件可以通过应用程序的其余部分进行隧道和冒泡。 在这里，你将公开奇怪的键盘 messange 处理和 Win32 中输入体系结构的性质。 遗憾的是，`IsDialogMessage` 不会以任何方式返回，无论是否处理特定的击键。 更糟的是，它会对它不应处理的击键调用 `DispatchMessage()`！  因此，你必须对 `IsDialogMessage`进行反向工程处理，并且仅为你知道它将处理的密钥调用它：

```cpp
// Only call IsDialogMessage for keys it will do something with.
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {
    switch (m.wParam) {
        case VK_TAB:
        case VK_LEFT:
        case VK_UP:
        case VK_RIGHT:
        case VK_DOWN:
        case VK_EXECUTE:
        case VK_RETURN:
        case VK_ESCAPE:
        case VK_CANCEL:
            IsDialogMessage(dialog, &m);
            // IsDialogMessage should be called ProcessDialogMessage --
            // it processes messages without ever really telling you
            // if it handled a specific message or not
            return true;
    }
```

### <a name="override-tabinto-method-to-support-tabbing"></a>重写 TabInto 方法以支持 Tab 键

现在，你已实现 `TranslateAccelerator`，用户可以在对话框内按 tab 键，然后将其移到更大的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中。 但是，用户不能通过 tab 键返回到对话框。 若要解决此情况，请重写 `TabInto`：

```cpp
public:
    virtual bool TabInto(TraversalRequest^ request) override {
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
            SetFocus(lastTabStop);
        }
        else {
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
            SetFocus(firstTabStop);
        }
        return true;
    }
```

`TraversalRequest` 参数告诉您选项卡操作是制表符还是 shift 选项卡。

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>重写 OnMnemonic 方法以支持助记键

键盘处理几乎完成，但有一件事丢失–助记键不起作用。 如果用户按下 alt-F，焦点将无法跳到 "First name：" 编辑框。 因此，请重写 `OnMnemonic` 方法：

```cpp
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {
    ::MSG m = ConvertMessage(msg);

    // If it's one of our mnemonics, set focus to the appropriate hwnd
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {
        int dialogitem = 9999;
        switch (m.wParam) {
            case 's': dialogitem = IDOK; break;
            case 'c': dialogitem = IDCANCEL; break;
            case 'f': dialogitem = IDC_EDIT1; break;
            case 'l': dialogitem = IDC_EDIT2; break;
            case 'p': dialogitem = IDC_EDIT3; break;
            case 'a': dialogitem = IDC_EDIT4; break;
            case 'i': dialogitem = IDC_EDIT5; break;
            case 't': dialogitem = IDC_EDIT6; break;
            case 'z': dialogitem = IDC_EDIT7; break;
        }
        if (dialogitem != 9999) {
            HWND hwnd = GetDlgItem(dialog, dialogitem);
            SetFocus(hwnd);
            return true;
        }
    }
    return false; // key unhandled
};
```

为什么不在此处调用 `IsDialogMessage`？  你的问题与以前相同，你需要能够通知 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 代码你的代码是否已处理击键，`IsDialogMessage` 无法执行此操作。 还有另一个问题，因为如果重点 HWND 不在对话框内，`IsDialogMessage` 会拒绝处理助记键。

### <a name="instantiate-the-hwndhost-derived-class"></a>实例化 System.windows.interop.hwndhost> 派生类

最后，既然已准备好所有键和选项卡支持，你可以将 <xref:System.Windows.Interop.HwndHost> 放入更大的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。 如果主要应用程序是以 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]编写的，则将其放在正确的位置的最简单方法是将空 <xref:System.Windows.Controls.Border> 元素保留在要放置 <xref:System.Windows.Interop.HwndHost>的位置。 在此处创建一个名为 `insertHwndHostHere`的 <xref:System.Windows.Controls.Border>：

```xaml
<Window x:Class="WPFApplication1.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Windows Presentation Framework Application"
    Loaded="Window1_Loaded"
    >
    <StackPanel>
        <Button Content="WPF button"/>
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>
        <Button Content="WPF button"/>
    </StackPanel>
</Window>
```

接下来要做的就是在代码序列中查找一个很好的位置来实例化 <xref:System.Windows.Interop.HwndHost> 并将其连接到 <xref:System.Windows.Controls.Border>。 在此示例中，将其放在 <xref:System.Windows.Window> 派生类的构造函数中：

```csharp
public partial class Window1 : Window {
    public Window1() {
    }

    void Window1_Loaded(object sender, RoutedEventArgs e) {
        HwndHost host = new ManagedCpp.MyHwndHost();
        insertHwndHostHere.Child = host;
    }
}
```

这为你提供：

![运行的 WPF 应用程序的屏幕截图。](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a>另请参阅

- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
