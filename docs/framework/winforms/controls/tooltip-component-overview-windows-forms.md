---
title: ToolTip 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 33a66e8ab5c8b09c5ed3dcf9dc60810a42d4d05d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724032"
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="78402-102">ToolTip 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="78402-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="78402-103">Windows 窗体 <xref:System.Windows.Forms.ToolTip> 组件在用户指向控件时显示文本。</span><span class="sxs-lookup"><span data-stu-id="78402-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="78402-104">ToolTip 可与任何控件关联。</span><span class="sxs-lookup"><span data-stu-id="78402-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="78402-105">此组件的示例用法： 若要在窗体上节省空间，可以在按钮上显示一个小图标，并使用 ToolTip 来解释按钮的功能。</span><span class="sxs-lookup"><span data-stu-id="78402-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="78402-106">使用工具提示组件</span><span class="sxs-lookup"><span data-stu-id="78402-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="78402-107">一个<xref:System.Windows.Forms.ToolTip>组件提供`ToolTip`到 Windows 窗体或其他容器上的多个控件的属性。</span><span class="sxs-lookup"><span data-stu-id="78402-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="78402-108">例如，如果您将某个<xref:System.Windows.Forms.ToolTip>窗体上的组件，可以显示"在此处键入名称"的<xref:System.Windows.Forms.TextBox>控制和"单击此处以保存更改"<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="78402-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="78402-109">主要方法<xref:System.Windows.Forms.ToolTip>组件都<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>和<xref:System.Windows.Forms.ToolTip.GetToolTip%2A>。</span><span class="sxs-lookup"><span data-stu-id="78402-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="78402-110">可以使用<xref:System.Windows.Forms.ToolTip.SetToolTip%2A>方法设置为控件显示的工具提示。</span><span class="sxs-lookup"><span data-stu-id="78402-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="78402-111">有关详细信息，请参阅[如何：在设计时为 Windows 窗体上控件设置工具提示](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="78402-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="78402-112">键属性是<xref:System.Windows.Forms.ToolTip.Active%2A>，它必须设置为`true`的工具提示显示，和<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>，用于设置的工具提示字符串所示的时间长度，多长时间，用户必须指向的工具提示显示，控件及其这将显示后续工具提示窗口。</span><span class="sxs-lookup"><span data-stu-id="78402-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="78402-113">有关详细信息，请参阅[如何：更改 Windows 窗体 ToolTip 组件的延迟](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)。</span><span class="sxs-lookup"><span data-stu-id="78402-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78402-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="78402-114">See also</span></span>
- <xref:System.Windows.Forms.ToolTip>
- [<span data-ttu-id="78402-115">如何：在设计时为 Windows 窗体上控件设置工具提示</span><span class="sxs-lookup"><span data-stu-id="78402-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="78402-116">如何：更改 Windows 窗体 ToolTip 组件的延迟</span><span class="sxs-lookup"><span data-stu-id="78402-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
