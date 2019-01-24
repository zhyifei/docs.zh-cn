---
title: 如何：在 Windows 窗体 TextBox 控件中选择文本
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
ms.openlocfilehash: df2aec3ff108c0106f29e453a93b06c60e67c6af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649409"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="55099-102">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="55099-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="55099-103">您可以在 Windows 窗体中以编程方式选择文本<xref:System.Windows.Forms.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="55099-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="55099-104">例如，如果创建搜索特定字符串文本的函数，您可以选择要直观地发出警报找到的字符串中的位置的读取器的文本。</span><span class="sxs-lookup"><span data-stu-id="55099-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="55099-105">若要以编程方式选择文本</span><span class="sxs-lookup"><span data-stu-id="55099-105">To select text programmatically</span></span>  
  
1.  <span data-ttu-id="55099-106">设置<xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>到想要选择的文本开头的属性。</span><span class="sxs-lookup"><span data-stu-id="55099-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="55099-107"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>属性为一个数字，指示插入点内的文本字符串，则为 0 表示最左边的位置。</span><span class="sxs-lookup"><span data-stu-id="55099-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="55099-108">如果<xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>属性设置为值等于或大于的字符数在文本框中，插入点放在最后一个字符之后。</span><span class="sxs-lookup"><span data-stu-id="55099-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2.  <span data-ttu-id="55099-109">设置<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>属性设置为你想要选择的文本的长度。</span><span class="sxs-lookup"><span data-stu-id="55099-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="55099-110"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>属性是设置插入点的宽度的数字值。</span><span class="sxs-lookup"><span data-stu-id="55099-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="55099-111">设置<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>到之间的数字不是 0 将导致该要选择的字符数，从开始在当前插入点。</span><span class="sxs-lookup"><span data-stu-id="55099-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3.  <span data-ttu-id="55099-112">（可选）访问通过所选的文本<xref:System.Windows.Forms.TextBoxBase.SelectedText%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="55099-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="55099-113">选择下面的代码的文本内容框时控件的<xref:System.Windows.Forms.Control.Enter>事件发生。</span><span class="sxs-lookup"><span data-stu-id="55099-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="55099-114">此示例检查文本框中是否具有的值<xref:System.Windows.Forms.TextBox.Text%2A>属性不是`null`或空字符串。</span><span class="sxs-lookup"><span data-stu-id="55099-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="55099-115">当文本框中收到焦点时，选择在文本框中的当前文本。</span><span class="sxs-lookup"><span data-stu-id="55099-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="55099-116">`TextBox1_Enter`事件处理程序必须将绑定到控件; 有关详细信息，请参阅[如何：在运行时为 Windows 窗体创建事件处理程序](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="55099-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="55099-117">若要测试此示例中，按 Tab 键，直到文本框中获得焦点。</span><span class="sxs-lookup"><span data-stu-id="55099-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="55099-118">如果在文本框中单击，将取消选中文本。</span><span class="sxs-lookup"><span data-stu-id="55099-118">If you click in the text box, the text is unselected.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="55099-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="55099-119">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="55099-120">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="55099-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="55099-121">如何：控制 Windows 窗体 TextBox 控件中的插入点</span><span class="sxs-lookup"><span data-stu-id="55099-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="55099-122">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="55099-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="55099-123">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="55099-123">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="55099-124">如何：在字符串中放置引号</span><span class="sxs-lookup"><span data-stu-id="55099-124">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="55099-125">如何：查看 Windows 窗体 TextBox 控件中的多个行</span><span class="sxs-lookup"><span data-stu-id="55099-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="55099-126">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="55099-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
