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
ms.openlocfilehash: fcaf5da9958cf66fb63bd753dc94cba9c10f62f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096031"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="1be30-102">如何：使用 ColorDialog 组件显示调色板</span><span class="sxs-lookup"><span data-stu-id="1be30-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="1be30-103">[ColorDialog](colordialog-component-windows-forms.md)组件显示调色板的颜色，并返回包含用户选定的颜色的属性。</span><span class="sxs-lookup"><span data-stu-id="1be30-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="1be30-104">若要使用 ColorDialog 组件选择颜色</span><span class="sxs-lookup"><span data-stu-id="1be30-104">To choose a color using the ColorDialog component</span></span>  
  
1.  <span data-ttu-id="1be30-105">显示对话框框中使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="1be30-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="1be30-106">使用<xref:System.Windows.Forms.DialogResult>属性来确定如何关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="1be30-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="1be30-107">使用<xref:System.Windows.Forms.ColorDialog.Color%2A>属性的<xref:System.Windows.Forms.ColorDialog>组件设置所选的颜色。</span><span class="sxs-lookup"><span data-stu-id="1be30-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="1be30-108">在以下示例中，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序打开<xref:System.Windows.Forms.ColorDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="1be30-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="1be30-109">当一种颜色是所选与用户单击**确定**，则<xref:System.Windows.Forms.Button>控件的背景色设置为所选颜色。</span><span class="sxs-lookup"><span data-stu-id="1be30-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="1be30-110">该示例假定窗体具有<xref:System.Windows.Forms.Button>控件和一个<xref:System.Windows.Forms.ColorDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="1be30-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="1be30-111">(Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1be30-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1be30-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1be30-112">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="1be30-113">ColorDialog 组件</span><span class="sxs-lookup"><span data-stu-id="1be30-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
