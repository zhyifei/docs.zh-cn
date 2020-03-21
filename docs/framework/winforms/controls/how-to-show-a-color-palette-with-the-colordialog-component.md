---
title: 如何：使用 ColorDialog 组件显示调色板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141778"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>如何：使用 ColorDialog 组件显示调色板
[ColorDialog](colordialog-component-windows-forms.md)组件显示颜色调色板，并返回包含用户选择的颜色的属性。  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>使用 ColorDialog 组件选择颜色  
  
1. 使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法显示对话框。  
  
2. 使用<xref:System.Windows.Forms.DialogResult>属性确定对话框的关闭方式。  
  
3. <xref:System.Windows.Forms.ColorDialog.Color%2A>使用组件的属性<xref:System.Windows.Forms.ColorDialog>设置所选颜色。  
  
     在下面的示例中，<xref:System.Windows.Forms.Button>控件<xref:System.Windows.Forms.Control.Click>的事件处理程序将打开一个<xref:System.Windows.Forms.ColorDialog>组件。 当选择颜色并且用户单击 **"确定"** 时，<xref:System.Windows.Forms.Button>控件的背景颜色将设置为所选颜色。 该示例假定窗体具有控件<xref:System.Windows.Forms.Button>和<xref:System.Windows.Forms.ColorDialog>组件。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     （视觉 C#，视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog 组件](colordialog-component-windows-forms.md)
