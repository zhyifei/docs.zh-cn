---
title: 如何：在设计时为 Windows 窗体上的控件设置工具提示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 7f698a517fbf72ceafde4a117b4d92dd9d352834
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964394"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="9e508-102">如何：在设计时为 Windows 窗体上的控件设置工具提示</span><span class="sxs-lookup"><span data-stu-id="9e508-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="9e508-103">可以设置<xref:System.Windows.Forms.ToolTip>字符串在代码中或在 Windows 窗体设计器中。</span><span class="sxs-lookup"><span data-stu-id="9e508-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="9e508-104">有关详细信息<xref:System.Windows.Forms.ToolTip>组件，请参阅[ToolTip 组件概述](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9e508-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e508-105">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="9e508-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9e508-106">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="9e508-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9e508-107">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="9e508-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="9e508-108">若要以编程方式设置工具提示</span><span class="sxs-lookup"><span data-stu-id="9e508-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="9e508-109">添加控件，将显示工具提示。</span><span class="sxs-lookup"><span data-stu-id="9e508-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="9e508-110">使用<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>方法的<xref:System.Windows.Forms.ToolTip>组件。</span><span class="sxs-lookup"><span data-stu-id="9e508-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="9e508-111">若要在设计器中设置工具提示</span><span class="sxs-lookup"><span data-stu-id="9e508-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="9e508-112">将 <xref:System.Windows.Forms.ToolTip> 组件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="9e508-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="9e508-113">选择将显示工具提示，或将其添加到窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="9e508-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="9e508-114">在中**属性**窗口中，将**ToolTip1 上的工具提示**为相应的文本字符串的值。</span><span class="sxs-lookup"><span data-stu-id="9e508-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e508-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e508-115">See Also</span></span>  
 [<span data-ttu-id="9e508-116">ToolTip 组件概述</span><span class="sxs-lookup"><span data-stu-id="9e508-116">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="9e508-117">如何：更改 Windows 窗体 ToolTip 组件的延迟</span><span class="sxs-lookup"><span data-stu-id="9e508-117">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [<span data-ttu-id="9e508-118">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="9e508-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
