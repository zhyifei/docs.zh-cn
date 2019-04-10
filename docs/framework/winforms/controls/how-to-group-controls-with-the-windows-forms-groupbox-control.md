---
title: 如何：使用 Windows 窗体 GroupBox 控件对控件分组
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: d2bad0020d18cd262bc2fe3489a00209308bd7b9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335870"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="70ed0-102">如何：使用 Windows 窗体 GroupBox 控件对控件分组</span><span class="sxs-lookup"><span data-stu-id="70ed0-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="70ed0-103">Windows 窗体<xref:System.Windows.Forms.GroupBox>控件用于分组其他控件。</span><span class="sxs-lookup"><span data-stu-id="70ed0-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="70ed0-104">有三个原因与组控件：</span><span class="sxs-lookup"><span data-stu-id="70ed0-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="70ed0-105">若要创建用于清除用户界面相关的窗体元素的直观分组。</span><span class="sxs-lookup"><span data-stu-id="70ed0-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="70ed0-106">若要创建以编程方式分组 （的单选按钮，例如）。</span><span class="sxs-lookup"><span data-stu-id="70ed0-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="70ed0-107">用于在设计时作为一个单元移动控件。</span><span class="sxs-lookup"><span data-stu-id="70ed0-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="70ed0-108">若要创建的一组控件</span><span class="sxs-lookup"><span data-stu-id="70ed0-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="70ed0-109">绘制<xref:System.Windows.Forms.GroupBox>窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="70ed0-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="70ed0-110">将其他控件添加到组中，绘制每个组框中。</span><span class="sxs-lookup"><span data-stu-id="70ed0-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="70ed0-111">如果你想要将括在组中的现有控件，可以选择所有控件，将它们剪切到剪贴板，再都选择<xref:System.Windows.Forms.GroupBox>控件，然后再将其粘贴到组框。</span><span class="sxs-lookup"><span data-stu-id="70ed0-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="70ed0-112">您还可以将它们拖到组。</span><span class="sxs-lookup"><span data-stu-id="70ed0-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="70ed0-113">设置<xref:System.Windows.Forms.GroupBox.Text%2A>分组框为适当标题的属性。</span><span class="sxs-lookup"><span data-stu-id="70ed0-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ed0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="70ed0-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="70ed0-115">GroupBox 控件</span><span class="sxs-lookup"><span data-stu-id="70ed0-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
