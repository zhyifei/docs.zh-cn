---
title: "如何：向 Windows 窗体添加控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d9075c93181b68828a307924259a9170c046baa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-controls-to-windows-forms"></a>如何：向 Windows 窗体添加控件
大多数窗体旨在通过将控件添加到窗体表面，以定义用户界面 (UI) 中。 A*控件*是用于显示信息或接受用户输入的窗体上的组件。 有关控件的详细信息，请参阅[Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-draw-a-control-on-a-form"></a>若要绘制窗体上控件  
  
1.  打开窗体。 有关详细信息，请参阅[如何： 显示 Windows 窗体设计器中](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。  
  
2.  在**工具箱**，单击你想要添加到你的窗体的控件。  
  
3.  在表单上，单击希望要位于，该控件的左上角拖到所需的控件，使其位于右下角的位置。  
  
     该控件添加到具有指定的位置和大小的窗体。  
  
    > [!NOTE]
    >  每个控件具有定义的默认大小。 你可以向窗体控件的默认大小添加控件，通过拖动从**工具箱**到窗体。  
  
### <a name="to-drag-a-control-to-a-form"></a>若要将控件拖动到窗体  
  
1.  打开窗体。 有关详细信息，请参阅[如何： 显示 Windows 窗体设计器中](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。  
  
2.  在**工具箱**，单击所需的控件并将其拖到窗体。  
  
     该控件添加到窗体中在其默认大小中的指定位置。  
  
    > [!NOTE]
    >  你可以双击中的控件**工具箱**将其添加到在其默认大小的窗体的左上角。  
  
     你可以在运行时动态将控件添加到窗体中。 在下面的代码示例中，<xref:System.Windows.Forms.TextBox>控件将被添加到窗体时<xref:System.Windows.Forms.Button>控件被单击。  
  
    > [!NOTE]
    >  以下过程，则需要存在带有的窗体**按钮**控件， `Button1`、 已放置在其上。  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>以编程方式添加到窗体控件  
  
1.  处理按钮的方法中`Click`设置控件的窗体的类，类似于以下要添加到您的控制变量的引用插入代码中的事件`Location`，然后添加该控件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  你还可以添加代码以初始化控件的其他属性。  
  
    > [!IMPORTANT]
    >  通过引用了恶意，您可能会公开您的本地计算机通过网络安全风险`UserControl`。 这仅会在恶意的用户创建破坏性的自定义控件，跟你错误地将其添加到你的项目的情况下是问题。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [如何：重设 Windows 窗体上控件的大小](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [如何：设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
