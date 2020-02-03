---
title: 对对象进行分层
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736339"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="d1355-102">如何：在 Windows 窗体上的层对象</span><span class="sxs-lookup"><span data-stu-id="d1355-102">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="d1355-103">当你创建复杂的用户界面或使用多文档界面（MDI）窗体时，通常需要将控件和子窗体分层以创建更复杂的用户界面（UI）。</span><span class="sxs-lookup"><span data-stu-id="d1355-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="d1355-104">若要在组的上下文中移动和跟踪控件和窗口，请处理其*z 顺序*。</span><span class="sxs-lookup"><span data-stu-id="d1355-104">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="d1355-105">Z 顺序是窗体上的控件沿窗体的 z 轴（深度）的可视化分层。</span><span class="sxs-lookup"><span data-stu-id="d1355-105">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="d1355-106">Z 顺序顶部的窗口与所有其他窗口重叠。</span><span class="sxs-lookup"><span data-stu-id="d1355-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="d1355-107">所有其他窗口都与 z 顺序底部的窗口重叠。</span><span class="sxs-lookup"><span data-stu-id="d1355-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="d1355-108">在设计时将控件分层</span><span class="sxs-lookup"><span data-stu-id="d1355-108">To layer controls at design time</span></span>

1. <span data-ttu-id="d1355-109">在 Visual Studio 中，选择要分层的控件。</span><span class="sxs-lookup"><span data-stu-id="d1355-109">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="d1355-110">在 "**格式**" 菜单上，选择 "**顺序**"，然后选择 "**置于顶层**" 或 "置于**底层**"。</span><span class="sxs-lookup"><span data-stu-id="d1355-110">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="d1355-111">以编程方式对控件进行分层</span><span class="sxs-lookup"><span data-stu-id="d1355-111">To layer controls programmatically</span></span>

<span data-ttu-id="d1355-112">使用 <xref:System.Windows.Forms.Control.BringToFront%2A> 和 <xref:System.Windows.Forms.Control.SendToBack%2A> 方法来操作控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="d1355-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="d1355-113">例如，如果 <xref:System.Windows.Forms.TextBox> `txtFirstName`控件在另一控件的下面，并且你想要将其置于顶层，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="d1355-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> <span data-ttu-id="d1355-114">Windows 窗体支持*控件包含*。</span><span class="sxs-lookup"><span data-stu-id="d1355-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="d1355-115">控件包含涉及到在包含控件中放置许多控件，如 <xref:System.Windows.Forms.GroupBox> 控件中的大量 <xref:System.Windows.Forms.RadioButton> 控件。</span><span class="sxs-lookup"><span data-stu-id="d1355-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="d1355-116">然后，可以将控件分层到包含控件中。</span><span class="sxs-lookup"><span data-stu-id="d1355-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="d1355-117">移动组框也将移动控件，因为这些控件包含在其中。</span><span class="sxs-lookup"><span data-stu-id="d1355-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1355-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1355-118">See also</span></span>

- [<span data-ttu-id="d1355-119">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d1355-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="d1355-120">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="d1355-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="d1355-121">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="d1355-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="d1355-122">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="d1355-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
