---
title: 控件和组件创作疑难解答
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
ms.openlocfilehash: 9100d6dc41f982af340d747ad447009a183b3c7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-control-and-component-authoring"></a>控件和组件创作疑难解答
本主题列出了开发组件和控件时遇到的常见问题。 有关详细信息，请参阅[使用组件编程](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)。  
  
-   无法将控件添加到工具箱  
  
-   无法调试 Windows 窗体用户控件或组件  
  
-   在继承的控件或组件中引发了两次事件  
  
-   设计时错误：“创建组件‘组件名称’失败”  
  
-   STAThreadAttribute  
  
-   组件图标未出现在工具箱中  
  
## <a name="cannot-add-control-to-toolbox"></a>无法将控件添加到工具箱  
 如果要将在另一项目中创建的自定义控件或第三方控件添加到“工具箱”中，必须手动操作。 如果当前项目中包含控件或组件，它应自动显示在“工具箱”中。 有关详细信息，请参阅[演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)。  
  
#### <a name="to-add-a-control-to-the-toolbox"></a>将控件添加到工具箱  
  
1.  右键单击“工具箱”，并从快捷菜单中选择“选择项”。  
  
2.  在“选择工具箱项”对话框中，添加组件：  
  
    -   如果要添加 .NET Framework 组件或控件，请单击“.NET Framework 组件”选项卡。  
  
         - 或 -  
  
    -   如果要添加 COM 组件或 ActiveX 控件，请单击“COM 组件”选项卡。  
  
3.  如果对话框中列出了该控件，请务必将它选中，然后单击“确定”。  
  
     该控件即会添加到“工具箱”中。  
  
4.  如果对话框中未列出该控件，请执行以下操作：  
  
    1.  单击“浏览”按钮。  
  
    2.  浏览到包含 .dll 文件（它包含控件）的文件夹。  
  
    3.  选择 .dll 文件并单击“打开”。  
  
         控件即会出现在对话框中。  
  
    4.  确认选中该控件，然后单击“确定”。  
  
         控件即会添加到“工具箱”中。  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a>无法调试 Windows 窗体用户控件或组件  
 如果你的控件派生自<xref:System.Windows.Forms.UserControl>类，可以调试使用测试容器的运行时行为。 有关详细信息，请参阅[如何：测试 UserControl 的运行时行为](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)。  
  
 其他自定义控件和组件不是独立的项目。 它们必须由 Windows 窗体项目这样的应用程序承载。 若要调试控件或组件，必须将其添加到 Windows 窗体项目。  
  
#### <a name="to-debug-a-control-or-component"></a>调试控件或组件  
  
1.  在“生成”菜单中，单击“生成解决方案”来生成解决方案。  
  
2.  在“文件”菜单中，选择“添加”，然后选择“新建项目”，将测试项目添加到应用程序中。  
  
3.  在“添加新项目”对话框中选择“Windows 应用程序”作为项目类型。  
  
4.  在“解决方案资源管理器”中，右键单击新项目的“引用”节点。 在快捷菜单上单击“添加引用”，为包含控件或组件的项目添加引用。  
  
5.  在测试项目中创建控件或组件的实例。 如果组件在“工具箱”中，则可将其拖动到设计器图面，或者以编程方式创建实例，如下面的代码示例所示。  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     现在即可像平常一样调试控件或组件。  
  
 有关调试的详细信息，请参阅[在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)和[演练：在设计时调试自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)。  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a>在继承的控件或组件中引发了两次事件  
 这可能是由于重复的 `Handles` 子句引起的。 有关详细信息，请参阅[有关 Visual Basic 中继承的事件处理程序的疑难解答](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)。  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a>设计时错误：“创建组件‘组件名称’失败”  
 组件或控件必须提供一个不带参数的默认构造函数。 设计环境创建组件或控件的实例时，不会尝试为使用参数的构造函数重载提供任何参数。  
  
## <a name="stathreadattribute"></a>STAThreadAttribute  
 <xref:System.STAThreadAttribute>通知公共语言运行时 (CLR) Windows 窗体使用单线程单元模式。 如果没有对 Windows 窗体应用程序的 `Main` 方法应用此特性，则可能会出现意外的行为。 例如，背景图像可能不会出现等控件<xref:System.Windows.Forms.ListView>。 某些控件也可能需要此属性才能正确地实现自动完成和拖放行为。  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a>组件图标未出现在工具箱中  
 当你使用<xref:System.Drawing.ToolboxBitmapAttribute>将图标与你自定义组件相关联，位图将不会出现在工具箱中自动生成组件。 若要查看位图，请使用“选择工具箱项”对话框重载控件。 有关详细信息，请参阅[如何：为控件提供工具箱位图](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)。  
  
## <a name="see-also"></a>请参阅  
 [设计时开发 Windows 窗体控件](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [演练：使用自定义组件自动填充工具箱](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [如何：测试 UserControl 的运行时行为](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 [演练：设计时调试自定义 Windows 窗体控件](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 [组件创作](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 [设计时开发的疑难解答](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [使用组件编程](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)
