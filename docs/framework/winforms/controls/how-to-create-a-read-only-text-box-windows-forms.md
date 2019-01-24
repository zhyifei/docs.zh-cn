---
title: 如何：创建只读文本框 （Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 89d331f6c7fad5880aff031eb808199292e493a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670331"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="d6b3f-102">如何：创建只读文本框 （Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="d6b3f-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="d6b3f-103">可以将可编辑的 Windows 窗体文本框中转换为只读的控件。</span><span class="sxs-lookup"><span data-stu-id="d6b3f-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="d6b3f-104">例如，在文本框中可能显示一个值，通常编辑，但可能目前，由于应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="d6b3f-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="d6b3f-105">若要创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="d6b3f-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="d6b3f-106">设置<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="d6b3f-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="d6b3f-107">属性设置为`true`，用户仍可以向下滚动并突出文本在文本框中显示但不允许更改。</span><span class="sxs-lookup"><span data-stu-id="d6b3f-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="d6b3f-108">一个**副本**命令将一个文本框中, 正常运行，但**剪切**并**粘贴**命令不是。</span><span class="sxs-lookup"><span data-stu-id="d6b3f-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6b3f-109"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>属性只影响在运行时的用户交互。</span><span class="sxs-lookup"><span data-stu-id="d6b3f-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="d6b3f-110">您可以仍更改文本框的内容以编程方式在运行时通过更改<xref:System.Windows.Forms.TextBox.Text%2A>属性文本框的。</span><span class="sxs-lookup"><span data-stu-id="d6b3f-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b3f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6b3f-111">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="d6b3f-112">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="d6b3f-112">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="d6b3f-113">如何：控制 Windows 窗体 TextBox 控件中的插入点</span><span class="sxs-lookup"><span data-stu-id="d6b3f-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="d6b3f-114">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="d6b3f-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d6b3f-115">如何：在字符串中放置引号</span><span class="sxs-lookup"><span data-stu-id="d6b3f-115">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="d6b3f-116">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="d6b3f-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d6b3f-117">如何：查看 Windows 窗体 TextBox 控件中的多个行</span><span class="sxs-lookup"><span data-stu-id="d6b3f-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d6b3f-118">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="d6b3f-118">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
