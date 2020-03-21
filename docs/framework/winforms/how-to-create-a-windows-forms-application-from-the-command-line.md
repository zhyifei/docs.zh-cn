---
title: 从命令行创建 Windows 窗体应用程序
titleSuffix: ''
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 7bd3add526a6b60d628b05d46eca22ce407c36b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181991"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>如何：从命令行创建 Windows 窗体应用程序

下面的过程介绍从命令行创建和运行 Windows 窗体应用程序所必须完成的基本步骤。 在 Visual Studio 中没有对这些过程的扩展支持。  另请参阅[演练：在 WPF 中托管 Windows 窗体控件](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)。
  
## <a name="procedure"></a>过程  
  
#### <a name="to-create-the-form"></a>若要创建窗体  
  
1. 在空代码文件中，键入以下`Imports`或`using`语句：  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. 声明从 Form`Form1`类继承的名为的类：
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. 为`Form1`创建 无参数构造函数。
  
     将在后续过程中向构造函数添加更多代码。
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. 将 `Main` 方法添加到类。
  
    1. 将<xref:System.STAThreadAttribute>应用 到`Main`C# 方法以指定 Windows 窗体应用程序是单线程单元。 （在 Visual Basic 中不需要该属性，因为默认情况下，使用 Visual Basic 开发的 Windows 窗体应用程序使用单线程单元模型。  
  
    2. 调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>以将操作系统样式应用于应用程序。  
  
    3. 创建一个窗体实例，并运行。  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>编译并运行该应用程序  
  
1. 在.NET Framework 命令提示符处，导航到创建 `Form1` 类的目录。  
  
2. 编译该窗体。  
  
    - 如果使用 C#，则键入：`csc form1.cs`  
  
         `-or-`  
  
    - 如果使用 Visual Basic，则键入：`vbc form1.vb`  
  
3. 在命令提示符处，键入：`Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>添加控件和处理事件

上一过程中的步骤演示了如何只创建一个可编译和运行的基本 Windows 窗体。 下一个过程中将显示如何创建控件并将其添加到窗体中，以及如何处理控件的事件。 有关可添加到 Windows 窗体的控件的详细信息，请参阅[Windows 窗体控件](./controls/index.md)。
  
 除了解如何创建 Windows 窗体应用程序外，还应了解基于事件的编程以及如何处理用户输入。 有关详细信息，请参阅在[Windows 窗体 中创建事件处理程序](creating-event-handlers-in-windows-forms.md)[和处理用户输入](./controls/handling-user-input.md)  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>若要声明一个按钮控件和处理其 click 事件  
  
1. 请声明一个名为 `button1` 的按钮控件。  
  
2. 在构造函数中，创建按钮，并设置其 <xref:System.Windows.Forms.Control.Size%2A>、<xref:System.Windows.Forms.Control.Location%2A> 和 <xref:System.Windows.Forms.Control.Text%2A> 属性。  
  
3. 向窗体添加按钮。  
  
     以下代码示例演示如何声明按钮控件：
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. 创建一个方法来处理该按钮的 <xref:System.Windows.Forms.Control.Click> 事件。  
  
5. 在 Click 事件处理程序中，显示带有消息“Hello World”的 <xref:System.Windows.Forms.MessageBox>。  
  
     以下代码示例演示如何处理按钮控件的单击事件：
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. 将 <xref:System.Windows.Forms.Control.Click> 事件与创建的方法相关联。  
  
     下面的代码示例演示如何将事件与方法相关联。  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. 编译并运行该应用程序，如之前过程中所述。  
  
## <a name="example"></a>示例  

以下代码示例是前面过程的完整示例：
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [更改 Windows 窗体外观](changing-the-appearance-of-windows-forms.md)
- [增强 Windows 窗体应用程序](./advanced/index.md)
- [Windows 窗体入门](getting-started-with-windows-forms.md)
