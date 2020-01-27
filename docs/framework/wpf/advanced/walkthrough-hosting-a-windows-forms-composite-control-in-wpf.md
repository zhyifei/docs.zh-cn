---
title: 在 WPF 中承载 Windows 窗体复合控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 16c09b4bb393fa830412385b4b405dd1fae9878b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745005"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>연습: WPF에서 Windows Forms 복합 컨트롤 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 애플리케이션을 만들기 위한 다양한 환경을 제공합니다. 但是，当您对 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 代码有大量投资时，在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中重复使用至少一些代码，而不是从头重新编写它会更有效。 最常见的情况是现有 Windows 窗体控件。 경우에 따라 이러한 컨트롤에 대한 소스 코드에 액세스하지 못할 수도 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中承载此类控件的简单过程。 例如，你可以将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用于大多数编程，同时承载专用 <xref:System.Windows.Forms.DataGridView> 控件。  
  
 本演练将指导你完成承载 Windows 窗体复合控件以在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中执行数据输入的应用程序。 복합 컨트롤은 DLL로 패키지됩니다. 이 일반적인 절차는 더 복잡한 애플리케이션 및 컨트롤로 확장할 수 있습니다. 本演练的设计与演练的外观和功能几乎完全相同[：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)。 주요 차이점은 호스팅 시나리오가 반대라는 점입니다.  
  
 이 연습은 두 개의 섹션으로 구분됩니다. 第一部分简要介绍 Windows 窗体复合控件的实现。 第二部分详细讨论如何在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中承载复合控件、从控件接收事件以及访问控件的某些属性。  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
- Windows Forms 복합 컨트롤 구현  
  
- WPF 호스트 애플리케이션 구현  
  
 有关本演练中阐释的任务的完整代码列表，请参阅[在 WPF 中承载 Windows 窗体复合控件示例](https://go.microsoft.com/fwlink/?LinkID=159999)。  
  
## <a name="prerequisites"></a>先决条件  

이 연습을 완료하려면 Visual Studio가 필요합니다.
  
## <a name="implementing-the-windows-forms-composite-control"></a>Windows Forms 복합 컨트롤 구현  
 本示例中使用的 Windows 窗体复合控件是一个简单的数据输入窗体。 이 폼에서는 사용자의 이름 및 주소를 사용한 다음 사용자 지정 이벤트를 사용하여 해당 정보를 호스트에 반환합니다. 다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.  

 下图显示了一个 Windows 窗体复合控件：  

 ![显示简单 Windows 窗体控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a>프로젝트 만들기  
 프로젝트를 시작하려면  
  
1. 启动 Visual Studio，然后打开 "**新建项目**" 对话框。  
  
2. 在 "窗口" 类别中，选择 " **Windows 窗体控件库**" 模板。  
  
3. 새 프로젝트의 이름을 `MyControls`로 지정합니다.  
  
4. 对于 "位置"，指定一个便于命名的顶层文件夹，如 `WpfHostingWindowsFormsControl`。 나중에 이 폴더에 호스트 애플리케이션을 넣습니다.  
  
5. **확인**을 클릭하여 프로젝트를 만듭니다. 默认项目包含一个名为 `UserControl1`的控件。  
  
6. 在解决方案资源管理器中，将 `UserControl1` 重命名为 `MyControl1`。  
  
 프로젝트에는 다음과 같은 시스템 DLL에 대한 참조가 있어야 합니다. 이러한 DLL이 기본적으로 포함되지 않은 경우 프로젝트에 추가합니다.  
  
- System  
  
- System.Data  
  
- System.Drawing  
  
- System.Windows.Forms  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>폼에 컨트롤 추가  
 폼에 컨트롤을 추가하려면  
  
- 在设计器中打开 `MyControl1`。  
  
 在窗体上，添加五个 <xref:System.Windows.Forms.Label> 控件及其相应的 <xref:System.Windows.Forms.TextBox> 控件，并将其调整大小并按上图所示。 在此示例中，<xref:System.Windows.Forms.TextBox> 控件被命名为：  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 添加两个标记为 **"确定" 和 "** **取消**" 的 <xref:System.Windows.Forms.Button> 控件。 在此示例中，按钮名称分别 `btnOK` 和 `btnCancel`。  
  
### <a name="implementing-the-supporting-code"></a>지원 코드 구현  
 코드 보기에서 폼을 엽니다. 控件通过引发自定义 `OnButtonClick` 事件将收集的数据返回到其主机。 데이터는 이벤트 인수 개체에 포함되어 있습니다. 다음 코드에서는 이벤트 및 대리자 선언을 보여 줍니다.  
  
 `MyControl1` 클래스에 다음 코드를 추가합니다.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 `MyControlEventArgs` 类包含要返回给主机的信息。

 다음 클래스를 폼에 추가합니다.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 当用户单击 **"确定" 或 "** **取消**" 按钮时，<xref:System.Windows.Forms.Control.Click> 事件处理程序将创建一个包含数据的 `MyControlEventArgs` 对象，并引发 `OnButtonClick` 事件。 这两个处理程序的唯一区别在于事件参数的 `IsOK` 属性。 이 속성을 통해 호스트는 클릭한 단추를 확인할 수 있습니다. 它设置为 "**确定"** 按钮 `true`，`false` "**取消**" 按钮。 다음 코드에서는 두 개의 단추 처리기를 보여 줍니다.

 `MyControl1` 클래스에 다음 코드를 추가합니다.

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>어셈블리에 강력한 이름을 지정하고 어셈블리 빌드
 对于要由 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序引用的程序集，该程序集必须具有强名称。 若要创建强名称，请使用 Sn.exe 创建密钥文件并将其添加到你的项目中。

1. Visual Studio 명령 프롬프트를 엽니다. 为此，请单击 "**开始**" 菜单，然后选择 "**所有程序/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio 命令提示**"。 그러면 사용자 지정된 환경 변수가 있는 콘솔 창이 시작됩니다.

2. 在命令提示符下，使用 `cd` 命令来打开项目文件夹。

3. 다음 명령을 실행하여 MyControls.snk라는 키 파일을 생성합니다.

    ```console
    Sn.exe -k MyControls.snk
    ```

4. 若要在项目中包含密钥文件，请在解决方案资源管理器中右键单击项目名称，然后单击 "**属性**"。 在 "项目设计器" 中，单击 "**签名**" 选项卡，选中 "为**程序集签名**" 复选框，然后浏览到密钥文件。

5. 솔루션을 빌드합니다. 빌드하면 MyControls.dll이라는 DLL이 생성됩니다.

## <a name="implementing-the-wpf-host-application"></a>WPF 호스트 애플리케이션 구현
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 主机应用程序使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件来承载 `MyControl1`。 应用程序将处理 `OnButtonClick` 事件以接收来自控件的数据。 它还包含一个选项按钮集合，使你能够从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序更改控件的某些属性。 다음 그림에서는 완료된 애플리케이션을 보여 줍니다.

下图显示了完整的应用程序，包括嵌入在 WPF 应用程序中的控件：

 ![显示嵌入在 WPF 页中的控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>프로젝트 만들기
 프로젝트를 시작하려면

1. 打开 Visual Studio，然后选择 "**新建项目**"。

2. 在 "窗口" 类别中，选择 " **WPF 应用程序**" 模板。

3. 새 프로젝트의 이름을 `WpfHost`로 지정합니다.

4. 위치에는 MyControls 프로젝트를 포함하는 동일한 최상위 폴더를 지정합니다.

5. **확인**을 클릭하여 프로젝트를 만듭니다.

 还需要添加对包含 `MyControl1` 和其他程序集的 DLL 的引用。

1. 在解决方案资源管理器中右键单击项目名称，然后选择 "**添加引用**"。

2. 单击 "**浏览**" 选项卡，然后浏览到包含 mycontrols.dll 的文件夹。 이 연습에서 이 폴더는 MyControls\bin\Debug입니다.

3. 选择 "Mycontrols.dll"，然后单击 **"确定"** 。

4. 添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。

### <a name="implementing-the-basic-layout"></a>기본 레이아웃 구현
 主机应用程序的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 是在 Mainwindow.xaml 中实现的。 此文件包含用于定义布局的 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 标记，并承载 Windows 窗体控件。 애플리케이션은 세 가지 영역으로 구분됩니다.

- "**控件属性**" 面板，其中包含选项按钮的集合，您可以使用这些按钮来修改所承载控件的各种属性。

- "**控制面板**" 中的数据，其中包含多个 <xref:System.Windows.Controls.TextBlock> 元素，这些元素显示从寄宿控件返回的数据。

- 호스트된 컨트롤 자체.

 기본 레이아웃은 다음과 같은 XAML로 표시됩니다. 本示例中省略了宿主 `MyControl1` 所需的标记，但稍后将对此进行讨论。

 MainWindow.xaml의 XAML을 다음 코드로 바꿉니다. 如果使用 Visual Basic，请将类更改为 `x:Class="MainWindow"`。

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 第一个 <xref:System.Windows.Controls.StackPanel> 元素包含多组 <xref:System.Windows.Controls.RadioButton> 控件，这些控件可用于修改所承载控件的各种默认属性。 后跟一个承载 `MyControl1`的 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。 最后一个 <xref:System.Windows.Controls.StackPanel> 元素包含多个显示由寄宿控件返回的数据的 <xref:System.Windows.Controls.TextBlock> 元素。 元素的顺序以及 "<xref:System.Windows.Controls.DockPanel.Dock%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性 "设置将承载的控件嵌入到窗口中，无间隔或失真。

#### <a name="hosting-the-control"></a>컨트롤 호스팅
 之前的 XAML 的以下编辑版本侧重于承载 `MyControl1`所需的元素。

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 `xmlns` 命名空间映射特性创建对包含所承载控件的 `MyControls` 命名空间的引用。 此映射使你能够以 `<mcl:MyControl1>`形式表示 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的 `MyControl1`。

 XAML의 두 요소가 호스팅을 처리합니다.

- `WindowsFormsHost` 表示 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素，使用该元素可以在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中承载 Windows 窗体控件。

- `mcl:MyControl1`（表示 `MyControl1`）将添加到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子集合。 因此，此 Windows 窗体控件将呈现为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口的一部分，您可以从应用程序与控件进行通信。

### <a name="implementing-the-code-behind-file"></a>코드 숨김 파일 구현
 代码隐藏文件（Mainwindow.xaml 或 MainWindow.xaml.cs）包含实现上一部分所述的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 功能的过程代码。 기본 작업은 다음과 같습니다.

- 将事件处理程序附加到 `MyControl1`的 `OnButtonClick` 事件。

- 根据设置选项按钮集合的方式修改 `MyControl1`的各种属性。

- 컨트롤에서 수집한 데이터 표시.

#### <a name="initializing-the-application"></a>애플리케이션 초기화
 初始化代码包含在窗口的 <xref:System.Windows.FrameworkElement.Loaded> 事件的事件处理程序中，并将事件处理程序附加到控件的 `OnButtonClick` 事件。

 在 Mainwindow.xaml 或 MainWindow.xaml.cs 中，将以下代码添加到 `MainWindow` 类。

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 由于前面所述的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 将 `MyControl1` 添加到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子元素集合中，因此可以将 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 强制转换为获取对 `MyControl1`的引用。 然后，可以使用该引用将事件处理程序附加到 `OnButtonClick`。

 除了提供对控件本身的引用外，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 公开了许多控件属性，您可以从应用程序中对其进行操作。 초기화 코드는 나중에 애플리케이션에서 사용할 수 있도록 private 전역 변수에 해당 값을 할당합니다.

 因此，您可以轻松访问 `MyControls` DLL 中的类型，将以下 `Imports` 或 `using` 语句添加到文件的顶部。

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>OnButtonClick 이벤트 처리
 当用户单击控件的任一按钮时，`MyControl1` 引发 `OnButtonClick` 事件。

 `MainWindow` 클래스에 다음 코드를 추가합니다.

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 文本框中的数据将打包到 `MyControlEventArgs` 对象中。 如果用户单击 **"确定"** 按钮，事件处理程序将提取数据并将其显示在下面的面板中 `MyControl1`。

#### <a name="modifying-the-controls-properties"></a>컨트롤의 속성 수정
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素公开几个托管控件的默认属性。 결과적으로 애플리케이션의 스타일과 더 가깝게 일치하도록 컨트롤의 모양을 변경할 수 있습니다. 왼쪽 패널의 옵션 단추 집합을 사용하여 사용자는 여러 가지 색 및 글꼴 속성을 수정할 수 있습니다. 每组按钮都具有 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件的处理程序，该处理程序检测用户的选项按钮选择并更改控件上的相应属性。

 `MainWindow` 클래스에 다음 코드를 추가합니다.

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 애플리케이션을 빌드 및 실행합니다. 在 Windows 窗体复合控件中添加一些文本，然后单击 **"确定"** 。 텍스트가 레이블에 나타납니다. 컨트롤에 대한 효과를 확인하려면 다른 라디오 단추를 클릭합니다.  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
