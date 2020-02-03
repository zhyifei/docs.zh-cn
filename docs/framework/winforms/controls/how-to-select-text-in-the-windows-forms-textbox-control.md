---
title: 在 TextBox 控件中选择文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 8a32e40f14ddae6f8ddcaa6d62337329df6fde26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745313"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="4d036-102">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="4d036-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="4d036-103">您可以在 Windows 窗体 <xref:System.Windows.Forms.TextBox> 控件中以编程方式选择文本。</span><span class="sxs-lookup"><span data-stu-id="4d036-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="4d036-104">例如，如果您创建一个函数，用于在文本中搜索特定字符串，则可以选择该文本以直观地向读者提醒找到的字符串位置。</span><span class="sxs-lookup"><span data-stu-id="4d036-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="4d036-105">以编程方式选择文本</span><span class="sxs-lookup"><span data-stu-id="4d036-105">To select text programmatically</span></span>  
  
1. <span data-ttu-id="4d036-106">将 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 属性设置为要选择的文本开头。</span><span class="sxs-lookup"><span data-stu-id="4d036-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="4d036-107"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 属性是一个数字，用于指示文本字符串中的插入点，0表示最左侧的位置。</span><span class="sxs-lookup"><span data-stu-id="4d036-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="4d036-108">如果将 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 属性设置为等于或大于文本框中字符数的值，则将插入点放在最后一个字符之后。</span><span class="sxs-lookup"><span data-stu-id="4d036-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="4d036-109">将 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 属性设置为要选择的文本长度。</span><span class="sxs-lookup"><span data-stu-id="4d036-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="4d036-110"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 属性是设置插入点宽度的数值。</span><span class="sxs-lookup"><span data-stu-id="4d036-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="4d036-111">如果将 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 设置为大于0的数字，则会从当前插入点开始选择要选择的字符数。</span><span class="sxs-lookup"><span data-stu-id="4d036-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="4d036-112">可有可无通过 <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> 属性访问所选文本。</span><span class="sxs-lookup"><span data-stu-id="4d036-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="4d036-113">下面的代码在控件的 <xref:System.Windows.Forms.Control.Enter> 事件发生时选择文本框的内容。</span><span class="sxs-lookup"><span data-stu-id="4d036-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="4d036-114">此示例检查文本框是否具有未 `null` 的 <xref:System.Windows.Forms.TextBox.Text%2A> 属性的值或空字符串。</span><span class="sxs-lookup"><span data-stu-id="4d036-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="4d036-115">当文本框接收到焦点时，文本框中的当前文本处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="4d036-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="4d036-116">必须将 `TextBox1_Enter` 事件处理程序绑定到控件;有关详细信息，请参阅[如何：在运行时为 Windows 窗体创建事件处理程序](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4d036-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="4d036-117">若要测试此示例，请按 Tab 键，直到文本框具有焦点。</span><span class="sxs-lookup"><span data-stu-id="4d036-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="4d036-118">如果在文本框中单击，则不会选择文本。</span><span class="sxs-lookup"><span data-stu-id="4d036-118">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4d036-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d036-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4d036-120">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="4d036-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4d036-121">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="4d036-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d036-122">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="4d036-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d036-123">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="4d036-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="4d036-124">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="4d036-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4d036-125">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="4d036-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4d036-126">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="4d036-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
