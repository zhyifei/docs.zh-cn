---
title: "如何：使用 FontDialog 组件显示字体列表"
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
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd04a44e6f6e3df26a643a8937e20e232e7471a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="a1047-102">如何：使用 FontDialog 组件显示字体列表</span><span class="sxs-lookup"><span data-stu-id="a1047-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="a1047-103">[FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)组件允许用户选择一种字体，以及更改其显示方面，例如其权重和大小。</span><span class="sxs-lookup"><span data-stu-id="a1047-103">The [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="a1047-104">在对话框中选定的字体中返回<xref:System.Windows.Forms.FontDialog.Font%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="a1047-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="a1047-105">因此，若要利用用户选定的字体非常简单，只需像读取属性。</span><span class="sxs-lookup"><span data-stu-id="a1047-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="a1047-106">若要选择使用 FontDialog 组件的字体属性</span><span class="sxs-lookup"><span data-stu-id="a1047-106">To select font properties using the FontDialog Component</span></span>  
  
1.  <span data-ttu-id="a1047-107">显示对话框框中使用<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="a1047-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="a1047-108">使用<xref:System.Windows.Forms.DialogResult>属性来确定如何关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a1047-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="a1047-109">使用<xref:System.Windows.Forms.FontDialog.Font%2A>属性来设置所需的字体。</span><span class="sxs-lookup"><span data-stu-id="a1047-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="a1047-110">在示例中，<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Click>事件处理程序将打开<xref:System.Windows.Forms.FontDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="a1047-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="a1047-111">一种字体如果已选择，并且用户单击**确定**、<xref:System.Windows.Forms.FontDialog.Font%2A>属性<xref:System.Windows.Forms.TextBox>窗体上的控件设置为选定的字体。</span><span class="sxs-lookup"><span data-stu-id="a1047-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="a1047-112">该示例假定你的窗体具有<xref:System.Windows.Forms.Button>控件，<xref:System.Windows.Forms.TextBox>控件，和一个<xref:System.Windows.Forms.FontDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="a1047-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
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
  
     <span data-ttu-id="a1047-113">（[!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 和 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]）将以下代码放在窗体构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a1047-113">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a1047-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1047-114">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="a1047-115">FontDialog 组件</span><span class="sxs-lookup"><span data-stu-id="a1047-115">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
