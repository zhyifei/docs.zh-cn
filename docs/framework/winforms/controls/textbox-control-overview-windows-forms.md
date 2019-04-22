---
title: TextBox 控件概述（Windows 窗体）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162132"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="ec52f-102">TextBox 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="ec52f-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="ec52f-103">若要获取用户输入或显示文本使用 Windows 窗体的文本框。</span><span class="sxs-lookup"><span data-stu-id="ec52f-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="ec52f-104"><xref:System.Windows.Forms.TextBox>控件通常用于可编辑文本，尽管也可将其只读的。</span><span class="sxs-lookup"><span data-stu-id="ec52f-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="ec52f-105">文本框可以显示多个行，该控件的大小的文本换行并添加基本格式设置。</span><span class="sxs-lookup"><span data-stu-id="ec52f-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="ec52f-106"><xref:System.Windows.Forms.TextBox>控件提供了用于显示或输入到控件中的文本的格式样式。</span><span class="sxs-lookup"><span data-stu-id="ec52f-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="ec52f-107">若要显示多种类型的格式化文本，请使用<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ec52f-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="ec52f-108">有关详细信息，请参阅[RichTextBox 控件概述](richtextbox-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ec52f-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="ec52f-109">使用 TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="ec52f-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="ec52f-110">由控件显示的文本包含在<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ec52f-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="ec52f-111">默认情况下，您可以输入最多 2048年个字符，在文本框中。</span><span class="sxs-lookup"><span data-stu-id="ec52f-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="ec52f-112">如果您设置<xref:System.Windows.Forms.TextBox.Multiline%2A>属性设置为`true`，可以输入最多 32 KB 的文本。</span><span class="sxs-lookup"><span data-stu-id="ec52f-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="ec52f-113"><xref:System.Windows.Forms.TextBox.Text%2A>属性可以设置在设计时使用属性窗口中，在运行时在运行时在代码中，或用户的输入。</span><span class="sxs-lookup"><span data-stu-id="ec52f-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="ec52f-114">通过阅读，可以在运行时检索文本框的当前内容<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ec52f-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="ec52f-115">下面的代码示例在运行时设置控件中的文本。</span><span class="sxs-lookup"><span data-stu-id="ec52f-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="ec52f-116">`InitializeMyControl`过程将不会自动执行; 它必须在调用。</span><span class="sxs-lookup"><span data-stu-id="ec52f-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec52f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec52f-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="ec52f-118">如何：控制 Windows 窗体 TextBox 控件中的插入点</span><span class="sxs-lookup"><span data-stu-id="ec52f-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="ec52f-119">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="ec52f-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="ec52f-120">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="ec52f-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="ec52f-121">如何：在字符串中放置引号</span><span class="sxs-lookup"><span data-stu-id="ec52f-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="ec52f-122">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="ec52f-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="ec52f-123">如何：查看 Windows 窗体 TextBox 控件中的多个行</span><span class="sxs-lookup"><span data-stu-id="ec52f-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="ec52f-124">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="ec52f-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
