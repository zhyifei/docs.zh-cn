---
title: "TextBox 控件概述（Windows 窗体）"
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
f1_keywords: TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d7312246c43157ca9cd6c7b41d2b110586721c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="aa81a-102">TextBox 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="aa81a-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="aa81a-103">若要获取用户输入或显示文本使用 Windows 窗体的文本框。</span><span class="sxs-lookup"><span data-stu-id="aa81a-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="aa81a-104"><xref:System.Windows.Forms.TextBox>控件通常用于可编辑文本，虽然也可使其成为只读的。</span><span class="sxs-lookup"><span data-stu-id="aa81a-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="aa81a-105">文本框可以显示多个行，为该控件的大小的文本换行并添加基本格式设置。</span><span class="sxs-lookup"><span data-stu-id="aa81a-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="aa81a-106"><xref:System.Windows.Forms.TextBox>控件提供单个格式样式显示或文本框控件中输入的文本。</span><span class="sxs-lookup"><span data-stu-id="aa81a-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="aa81a-107">若要显示多种类型的格式化文本，请使用<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="aa81a-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="aa81a-108">有关详细信息，请参阅[RichTextBox 控件概述](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="aa81a-108">For more information, see [RichTextBox Control Overview](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="aa81a-109">使用文本框控件</span><span class="sxs-lookup"><span data-stu-id="aa81a-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="aa81a-110">中包含由控件显示的文本<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aa81a-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="aa81a-111">默认情况下，你可以输入最多 2048年个字符，在文本框中。</span><span class="sxs-lookup"><span data-stu-id="aa81a-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="aa81a-112">如果你设置<xref:System.Windows.Forms.TextBox.Multiline%2A>属性`true`，你可以输入最多为 32 KB 的文本。</span><span class="sxs-lookup"><span data-stu-id="aa81a-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="aa81a-113"><xref:System.Windows.Forms.TextBox.Text%2A>属性可以设置在设计时使用属性窗口中，在运行时运行时在代码中，或根据用户的输入。</span><span class="sxs-lookup"><span data-stu-id="aa81a-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="aa81a-114">文本框中的当前内容可以在运行时检索通过阅读<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="aa81a-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="aa81a-115">下面的代码示例在运行时设置控件中的文本。</span><span class="sxs-lookup"><span data-stu-id="aa81a-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="aa81a-116">`InitializeMyControl`不会自动执行过程，必须调用它。</span><span class="sxs-lookup"><span data-stu-id="aa81a-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa81a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa81a-117">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="aa81a-118">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="aa81a-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aa81a-119">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="aa81a-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aa81a-120">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="aa81a-120">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="aa81a-121">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="aa81a-121">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="aa81a-122">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="aa81a-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aa81a-123">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="aa81a-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="aa81a-124">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="aa81a-124">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
