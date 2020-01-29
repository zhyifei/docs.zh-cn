---
title: 带有分组框控件的组控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736651"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="08576-102">如何：使用 Windows 窗体 GroupBox 控件对控件分组</span><span class="sxs-lookup"><span data-stu-id="08576-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="08576-103">Windows 窗体 <xref:System.Windows.Forms.GroupBox> 控件用于对其他控件进行分组。</span><span class="sxs-lookup"><span data-stu-id="08576-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="08576-104">分组控件有三个原因：</span><span class="sxs-lookup"><span data-stu-id="08576-104">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="08576-105">为清晰的用户界面创建相关窗体元素的可视分组。</span><span class="sxs-lookup"><span data-stu-id="08576-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="08576-106">创建编程分组（例如，单选按钮）。</span><span class="sxs-lookup"><span data-stu-id="08576-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="08576-107">用于在设计时将控件作为一个单元移动。</span><span class="sxs-lookup"><span data-stu-id="08576-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="08576-108">创建一组控件</span><span class="sxs-lookup"><span data-stu-id="08576-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="08576-109">在窗体上绘制 <xref:System.Windows.Forms.GroupBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="08576-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="08576-110">将其他控件添加到分组框，并在组框中绘制每个控件。</span><span class="sxs-lookup"><span data-stu-id="08576-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="08576-111">如果要将现有控件置于分组框中，则可以选择所有控件，将它们剪切到剪贴板，选择 <xref:System.Windows.Forms.GroupBox> 的控件，然后将其粘贴到 "分组" 框。</span><span class="sxs-lookup"><span data-stu-id="08576-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="08576-112">您还可以将其拖动到分组框中。</span><span class="sxs-lookup"><span data-stu-id="08576-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="08576-113">将组框的 "<xref:System.Windows.Forms.GroupBox.Text%2A>" 属性设置为相应的标题。</span><span class="sxs-lookup"><span data-stu-id="08576-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08576-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08576-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="08576-115">GroupBox 控件</span><span class="sxs-lookup"><span data-stu-id="08576-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
