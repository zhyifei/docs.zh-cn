---
title: 如何：控制 Windows 窗体 TextBox 控件中的插入点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: cb3e7e7a44391ec7ee34ad0659f4185bd2304d26
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714887"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="818a8-102">如何：控制 Windows 窗体 TextBox 控件中的插入点</span><span class="sxs-lookup"><span data-stu-id="818a8-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="818a8-103">在 Windows 窗体时<xref:System.Windows.Forms.TextBox>控件首先获得焦点时，文本框中的默认值插入操作是左侧的任何现有文本。</span><span class="sxs-lookup"><span data-stu-id="818a8-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="818a8-104">用户可以移动插入点使用键盘或鼠标。</span><span class="sxs-lookup"><span data-stu-id="818a8-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="818a8-105">如果在文本框中丢失，并重新获得焦点，插入点将用户任何位置上一次放置它。</span><span class="sxs-lookup"><span data-stu-id="818a8-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="818a8-106">在某些情况下，此行为可能给用户带来不便。</span><span class="sxs-lookup"><span data-stu-id="818a8-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="818a8-107">在文字处理应用程序，用户可能希望新字符出现在任何现有的文本之后。</span><span class="sxs-lookup"><span data-stu-id="818a8-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="818a8-108">在数据输入应用程序中，用户可能希望新字符来替换任何现有条目。</span><span class="sxs-lookup"><span data-stu-id="818a8-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="818a8-109"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>和<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>属性，你可以修改行为以满足您的目的。</span><span class="sxs-lookup"><span data-stu-id="818a8-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="818a8-110">若要控制在 TextBox 控件中的插入点</span><span class="sxs-lookup"><span data-stu-id="818a8-110">To control the insertion point in a TextBox control</span></span>  
  
1.  <span data-ttu-id="818a8-111">将 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="818a8-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="818a8-112">零放置插入点紧挨左边的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="818a8-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2.  <span data-ttu-id="818a8-113">（可选）设置<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>属性设置为你想要选择的文本的长度。</span><span class="sxs-lookup"><span data-stu-id="818a8-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="818a8-114">下面的代码始终返回为 0 的插入点。</span><span class="sxs-lookup"><span data-stu-id="818a8-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="818a8-115">`TextBox1_Enter`事件处理程序必须将绑定到控件; 有关详细信息，请参阅[在 Windows 窗体中创建事件处理程序](../creating-event-handlers-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="818a8-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="818a8-116">使插入点默认情况下可见</span><span class="sxs-lookup"><span data-stu-id="818a8-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="818a8-117"><xref:System.Windows.Forms.TextBox>插入点，则新的窗体仅当在默认情况下可见<xref:System.Windows.Forms.TextBox>控件是 tab 键顺序中的第一行。</span><span class="sxs-lookup"><span data-stu-id="818a8-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="818a8-118">否则，插入点将显示仅当为<xref:System.Windows.Forms.TextBox>使用键盘或鼠标焦点。</span><span class="sxs-lookup"><span data-stu-id="818a8-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="818a8-119">若要使文本框插入点在新的窗体上的默认情况下可见</span><span class="sxs-lookup"><span data-stu-id="818a8-119">To make the text box insertion point visible by default on a new form</span></span>  
  
-   <span data-ttu-id="818a8-120">设置<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.Control.TabIndex%2A>属性设置为`0`。</span><span class="sxs-lookup"><span data-stu-id="818a8-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="818a8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="818a8-121">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="818a8-122">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="818a8-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="818a8-123">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="818a8-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="818a8-124">如何：创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="818a8-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="818a8-125">如何：在字符串中放置引号</span><span class="sxs-lookup"><span data-stu-id="818a8-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="818a8-126">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="818a8-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="818a8-127">如何：查看 Windows 窗体 TextBox 控件中的多个行</span><span class="sxs-lookup"><span data-stu-id="818a8-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="818a8-128">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="818a8-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
