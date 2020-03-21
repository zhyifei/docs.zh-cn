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
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="76d19-102">如何：使用 ColorDialog 组件显示调色板</span><span class="sxs-lookup"><span data-stu-id="76d19-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="76d19-103">[ColorDialog](colordialog-component-windows-forms.md)组件显示颜色调色板，并返回包含用户选择的颜色的属性。</span><span class="sxs-lookup"><span data-stu-id="76d19-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="76d19-104">使用 ColorDialog 组件选择颜色</span><span class="sxs-lookup"><span data-stu-id="76d19-104">To choose a color using the ColorDialog component</span></span>  
  
1. <span data-ttu-id="76d19-105">使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法显示对话框。</span><span class="sxs-lookup"><span data-stu-id="76d19-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="76d19-106">使用<xref:System.Windows.Forms.DialogResult>属性确定对话框的关闭方式。</span><span class="sxs-lookup"><span data-stu-id="76d19-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="76d19-107"><xref:System.Windows.Forms.ColorDialog.Color%2A>使用组件的属性<xref:System.Windows.Forms.ColorDialog>设置所选颜色。</span><span class="sxs-lookup"><span data-stu-id="76d19-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="76d19-108">在下面的示例中，<xref:System.Windows.Forms.Button>控件<xref:System.Windows.Forms.Control.Click>的事件处理程序将打开一个<xref:System.Windows.Forms.ColorDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="76d19-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="76d19-109">当选择颜色并且用户单击 **"确定"** 时，<xref:System.Windows.Forms.Button>控件的背景颜色将设置为所选颜色。</span><span class="sxs-lookup"><span data-stu-id="76d19-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="76d19-110">该示例假定窗体具有控件<xref:System.Windows.Forms.Button>和<xref:System.Windows.Forms.ColorDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="76d19-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="76d19-111">（视觉 C#，视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="76d19-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="76d19-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76d19-112">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="76d19-113">ColorDialog 组件</span><span class="sxs-lookup"><span data-stu-id="76d19-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
