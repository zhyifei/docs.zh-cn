---
title: 如何：显示字体列表使用 FontDialog 组件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 4036b6e12d8c4df2c4edfd5df293160d9197b61a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717058"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="320e0-102">如何：显示字体列表使用 FontDialog 组件</span><span class="sxs-lookup"><span data-stu-id="320e0-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="320e0-103">[FontDialog](fontdialog-component-windows-forms.md)组件让用户可以选择一种字体，以及更改其显示方面，例如其权重和大小。</span><span class="sxs-lookup"><span data-stu-id="320e0-103">The [FontDialog](fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="320e0-104">在对话框中选择的字体中返回<xref:System.Windows.Forms.FontDialog.Font%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="320e0-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="320e0-105">因此，利用用户选择的字体的非常简单，就像读取属性。</span><span class="sxs-lookup"><span data-stu-id="320e0-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="320e0-106">若要选择字体属性使用 FontDialog 组件</span><span class="sxs-lookup"><span data-stu-id="320e0-106">To select font properties using the FontDialog Component</span></span>  
  
1.  <span data-ttu-id="320e0-107">显示对话框框中使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="320e0-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="320e0-108">使用<xref:System.Windows.Forms.DialogResult>属性来确定如何关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="320e0-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="320e0-109">使用<xref:System.Windows.Forms.FontDialog.Font%2A>属性来设置所需的字体。</span><span class="sxs-lookup"><span data-stu-id="320e0-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="320e0-110">在以下示例中，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序打开<xref:System.Windows.Forms.FontDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="320e0-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="320e0-111">当一种字体是所选与用户单击**确定**，则<xref:System.Windows.Forms.FontDialog.Font%2A>属性的<xref:System.Windows.Forms.TextBox>窗体上的控件设置为所选字体。</span><span class="sxs-lookup"><span data-stu-id="320e0-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="320e0-112">该示例假定窗体具有<xref:System.Windows.Forms.Button>控件，<xref:System.Windows.Forms.TextBox>控件，和一个<xref:System.Windows.Forms.FontDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="320e0-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="320e0-113">(Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="320e0-113">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="320e0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="320e0-114">See also</span></span>
- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="320e0-115">FontDialog 组件</span><span class="sxs-lookup"><span data-stu-id="320e0-115">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
