---
title: 如何：在运行时在控件集合中进行添加或移除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 369946581847b4bdcf8bc658aeb94b14c529061c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182280"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>如何：在运行时在控件集合中进行添加或移除
应用程序开发中的常见任务是向窗体上的任何容器控件（如<xref:System.Windows.Forms.Panel>或<xref:System.Windows.Forms.GroupBox>控件，甚至窗体本身）添加控件并删除控件。 在设计时，可直接将控件拖到面板或分组框上。 在运行时，这些控件维护一个 `Controls` 集合，该集合会跟踪集合中放置了哪些控件。  
  
> [!NOTE]
> 以下代码示例适用于其中维护了一个控件集合的任何控件。  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>以编程方式向集合添加控件  
  
1. 创建要添加的控件实例。  
  
2. 设置新控件的属性。  
  
3. 将控件添加到父控件的 `Controls` 集合。  
  
     以下代码示例演示如何创建控件的<xref:System.Windows.Forms.Button>实例。 它需要具有<xref:System.Windows.Forms.Panel>控件的窗体，并且正在创建的`NewPanelButton_Click`按钮的事件处理方法已存在。  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a>以编程方式从集合移除控件  
  
1. 从事件中移除事件处理程序。 在可视化基本版中，使用"删除处理程序语句"关键字;在"可视基本"中，使用["删除处理程序语句"](../../../visual-basic/language-reference/statements/removehandler-statement.md)关键字。在 C# 中，使用[-# 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)。  
  
2. 使用 `Remove` 方法，从面板的 `Controls` 集合中删除所需控件。  
  
3. 调用<xref:System.Windows.Forms.Control.Dispose%2A>方法以释放控件使用的所有资源。  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Panel>
- [Panel 控件](panel-control-windows-forms.md)
