---
title: 如何：创建只读文本框（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530141"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="e388b-102">如何：创建只读文本框（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="e388b-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="e388b-103">可以将可编辑的 Windows 窗体文本框转换为只读的控件。</span><span class="sxs-lookup"><span data-stu-id="e388b-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="e388b-104">例如，在文本框中可能会显示一个值，通常编辑，但可能不是由于应用程序的状态的当前。</span><span class="sxs-lookup"><span data-stu-id="e388b-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="e388b-105">若要创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="e388b-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="e388b-106">设置<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="e388b-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="e388b-107">属性设置为`true`，用户仍可以向下滚动并突出显示但不允许更改文本框中的文本。</span><span class="sxs-lookup"><span data-stu-id="e388b-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="e388b-108">A**复制**命令在文本框中，将能正常运行但**剪切**和**粘贴**命令不可。</span><span class="sxs-lookup"><span data-stu-id="e388b-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e388b-109"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>属性仅会影响在运行时的用户交互。</span><span class="sxs-lookup"><span data-stu-id="e388b-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="e388b-110">你仍可更改文本框内容以编程方式在运行时更改<xref:System.Windows.Forms.TextBox.Text%2A>的文本框中的属性。</span><span class="sxs-lookup"><span data-stu-id="e388b-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e388b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e388b-111">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="e388b-112">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="e388b-112">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="e388b-113">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="e388b-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e388b-114">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="e388b-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e388b-115">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="e388b-115">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="e388b-116">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="e388b-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e388b-117">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="e388b-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="e388b-118">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="e388b-118">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
