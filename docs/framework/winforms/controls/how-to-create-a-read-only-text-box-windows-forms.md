---
title: 如何：创建只读文本框
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 17ae9524009c687cd62fb315f842e188e120ac68
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731271"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="db720-102">如何：创建只读文本框（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="db720-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="db720-103">可以将可编辑 Windows 窗体文本框转换为只读控件。</span><span class="sxs-lookup"><span data-stu-id="db720-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="db720-104">例如，文本框可能会显示一个值，该值通常是编辑的，但由于应用程序的状态，它当前可能不存在。</span><span class="sxs-lookup"><span data-stu-id="db720-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="db720-105">创建只读文本框</span><span class="sxs-lookup"><span data-stu-id="db720-105">To create a read-only text box</span></span>

1. <span data-ttu-id="db720-106">将 <xref:System.Windows.Forms.TextBox> 控件的 <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 属性设置为 "`true`"。</span><span class="sxs-lookup"><span data-stu-id="db720-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="db720-107">将属性设置为 `true`，用户仍可以滚动和突出显示文本框中的文本，而无需进行更改。</span><span class="sxs-lookup"><span data-stu-id="db720-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="db720-108">"**复制**" 命令在文本框中起作用，但 "**剪切**" 和 "**粘贴**" 命令不是这样。</span><span class="sxs-lookup"><span data-stu-id="db720-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db720-109"><xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> 属性仅在运行时影响用户交互。</span><span class="sxs-lookup"><span data-stu-id="db720-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="db720-110">你仍可以通过更改文本框的 "<xref:System.Windows.Forms.TextBox.Text%2A>" 属性，在运行时以编程方式更改文本框内容。</span><span class="sxs-lookup"><span data-stu-id="db720-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="db720-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db720-111">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="db720-112">TextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="db720-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="db720-113">如何：在 Windows 窗体 TextBox 控件中控制插入点</span><span class="sxs-lookup"><span data-stu-id="db720-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="db720-114">如何：使用 Windows 窗体 TextBox 控件创建密码文本框</span><span class="sxs-lookup"><span data-stu-id="db720-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="db720-115">如何：在字符串中添加引号</span><span class="sxs-lookup"><span data-stu-id="db720-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="db720-116">如何：在 Windows 窗体 TextBox 控件中选择文本</span><span class="sxs-lookup"><span data-stu-id="db720-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="db720-117">如何：在 Windows 窗体 TextBox 控件中查看多个行</span><span class="sxs-lookup"><span data-stu-id="db720-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="db720-118">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="db720-118">TextBox Control</span></span>](textbox-control-windows-forms.md)
