---
title: 如何：使用 Windows 窗体 GroupBox 控件对控件分组
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: 718367e9da9efda20c79fbff3bd2f14f11c96ee1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531919"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="1fda2-102">如何：使用 Windows 窗体 GroupBox 控件对控件分组</span><span class="sxs-lookup"><span data-stu-id="1fda2-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="1fda2-103">Windows 窗体<xref:System.Windows.Forms.GroupBox>控制用于其他控件进行分组。</span><span class="sxs-lookup"><span data-stu-id="1fda2-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="1fda2-104">有三个与组控件的原因：</span><span class="sxs-lookup"><span data-stu-id="1fda2-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="1fda2-105">若要创建适用于清除用户界面相关的窗体元素的直观分组。</span><span class="sxs-lookup"><span data-stu-id="1fda2-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="1fda2-106">若要创建 （的单选按钮，例如） 以编程方式分组。</span><span class="sxs-lookup"><span data-stu-id="1fda2-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="1fda2-107">用于在设计时，请作为一个单元中移动控件。</span><span class="sxs-lookup"><span data-stu-id="1fda2-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="1fda2-108">若要创建一组控件</span><span class="sxs-lookup"><span data-stu-id="1fda2-108">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="1fda2-109">绘制<xref:System.Windows.Forms.GroupBox>窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="1fda2-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="1fda2-110">将其他控件添加到组中，绘制每个分组框内。</span><span class="sxs-lookup"><span data-stu-id="1fda2-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="1fda2-111">如果你有想要将括在组中的现有控件，可以选择所有控件，将它们剪切到剪贴板，再都选择<xref:System.Windows.Forms.GroupBox>控制，然后将它们粘贴到组框。</span><span class="sxs-lookup"><span data-stu-id="1fda2-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="1fda2-112">你还可以将其拖到组框。</span><span class="sxs-lookup"><span data-stu-id="1fda2-112">You can also drag them into the group box.</span></span>  
  
3.  <span data-ttu-id="1fda2-113">设置<xref:System.Windows.Forms.GroupBox.Text%2A>分组框为适当标题的属性。</span><span class="sxs-lookup"><span data-stu-id="1fda2-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fda2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fda2-114">See Also</span></span>  
 <xref:System.Windows.Forms.GroupBox>  
 [<span data-ttu-id="1fda2-115">GroupBox 控件</span><span class="sxs-lookup"><span data-stu-id="1fda2-115">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
