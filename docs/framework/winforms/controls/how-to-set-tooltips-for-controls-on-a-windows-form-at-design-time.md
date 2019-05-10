---
title: 如何：在设计时为 Windows 窗体上的控件设置 ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211690"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="4491e-102">如何：在设计时为 Windows 窗体上的控件设置工具提示</span><span class="sxs-lookup"><span data-stu-id="4491e-102">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="4491e-103">可以设置<xref:System.Windows.Forms.ToolTip>字符串在代码中或在 Visual Studio 中的 Windows 窗体设计器中。</span><span class="sxs-lookup"><span data-stu-id="4491e-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="4491e-104">有关详细信息<xref:System.Windows.Forms.ToolTip>组件，请参阅[ToolTip 组件概述](tooltip-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4491e-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="4491e-105">以编程方式设置工具提示</span><span class="sxs-lookup"><span data-stu-id="4491e-105">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="4491e-106">添加控件，将显示工具提示。</span><span class="sxs-lookup"><span data-stu-id="4491e-106">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="4491e-107">使用<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>方法的<xref:System.Windows.Forms.ToolTip>组件。</span><span class="sxs-lookup"><span data-stu-id="4491e-107">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="4491e-108">在设计器中设置工具提示</span><span class="sxs-lookup"><span data-stu-id="4491e-108">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="4491e-109">在 Visual Studio 中，添加<xref:System.Windows.Forms.ToolTip>组件到窗体。</span><span class="sxs-lookup"><span data-stu-id="4491e-109">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="4491e-110">选择将显示工具提示，或将其添加到窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="4491e-110">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="4491e-111">在中**属性**窗口中，将**ToolTip1 上的工具提示**为相应的文本字符串的值。</span><span class="sxs-lookup"><span data-stu-id="4491e-111">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="4491e-112">若要以编程方式删除工具提示</span><span class="sxs-lookup"><span data-stu-id="4491e-112">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="4491e-113">使用<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>方法的<xref:System.Windows.Forms.ToolTip>组件。</span><span class="sxs-lookup"><span data-stu-id="4491e-113">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="4491e-114">在设计器中删除一个工具提示</span><span class="sxs-lookup"><span data-stu-id="4491e-114">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="4491e-115">在 Visual Studio 中，选择显示工具提示的控件。</span><span class="sxs-lookup"><span data-stu-id="4491e-115">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="4491e-116">在中**属性**窗口中，删除中的文本**ToolTip1 上的工具提示**。</span><span class="sxs-lookup"><span data-stu-id="4491e-116">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4491e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4491e-117">See also</span></span>

- [<span data-ttu-id="4491e-118">ToolTip 组件概述</span><span class="sxs-lookup"><span data-stu-id="4491e-118">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="4491e-119">如何：更改 Windows 窗体 ToolTip 组件的延迟</span><span class="sxs-lookup"><span data-stu-id="4491e-119">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="4491e-120">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="4491e-120">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
