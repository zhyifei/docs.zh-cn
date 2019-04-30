---
title: 如何：在 TableLayoutPanel 控件中锚定和停靠子控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: a84b00e93354a9aaff074a570cee931591816161
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053051"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="890b0-102">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="890b0-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="890b0-103"><xref:System.Windows.Forms.TableLayoutPanel> 控件支持其子控件中的 <xref:System.Windows.Forms.Control.Anchor%2A> 和 <xref:System.Windows.Forms.Control.Dock%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="890b0-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="890b0-104">在 TableLayoutPanel 单元格中对齐子控件</span><span class="sxs-lookup"><span data-stu-id="890b0-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="890b0-105">在窗体上创建一个 <xref:System.Windows.Forms.TableLayoutPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="890b0-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2. <span data-ttu-id="890b0-106">设置的值<xref:System.Windows.Forms.TableLayoutPanel>控件的<xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>并<xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>属性设置为**1**。</span><span class="sxs-lookup"><span data-stu-id="890b0-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3. <span data-ttu-id="890b0-107">在 <xref:System.Windows.Forms.TableLayoutPanel> 控件中创建一个 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="890b0-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="890b0-108"><xref:System.Windows.Forms.Button> 占据单元格的左上角。</span><span class="sxs-lookup"><span data-stu-id="890b0-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4. <span data-ttu-id="890b0-109">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Left`。</span><span class="sxs-lookup"><span data-stu-id="890b0-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="890b0-110"><xref:System.Windows.Forms.Button> 控件移动，以便与单元格的左边框对齐。</span><span class="sxs-lookup"><span data-stu-id="890b0-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="890b0-111">此行为与其他容器控件的行为不同。</span><span class="sxs-lookup"><span data-stu-id="890b0-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="890b0-112">在其他容器控件中，设置 <xref:System.Windows.Forms.Control.Anchor%2A> 属性后子控件并不移动，而且锚定控件与父容器边界之间的距离在设置 <xref:System.Windows.Forms.Control.Anchor%2A> 属性后是固定的。</span><span class="sxs-lookup"><span data-stu-id="890b0-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5. <span data-ttu-id="890b0-113">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Top, Left`。</span><span class="sxs-lookup"><span data-stu-id="890b0-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="890b0-114"><xref:System.Windows.Forms.Button> 控件移动，以占据单元格的左上角。</span><span class="sxs-lookup"><span data-stu-id="890b0-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6. <span data-ttu-id="890b0-115">值的有重复步骤 5`Top, Right`移动<xref:System.Windows.Forms.Button>到单元格的右上角的控件。</span><span class="sxs-lookup"><span data-stu-id="890b0-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="890b0-116">使用 `Bottom, Left` 和 `Bottom, Right` 值重复步骤。</span><span class="sxs-lookup"><span data-stu-id="890b0-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="890b0-117">若要对齐 TableLayoutPanel 单元格中的某个子控件</span><span class="sxs-lookup"><span data-stu-id="890b0-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="890b0-118">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Left, Right`。</span><span class="sxs-lookup"><span data-stu-id="890b0-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="890b0-119">调整 <xref:System.Windows.Forms.Button> 控件的大小，以便在单元格中拉伸。</span><span class="sxs-lookup"><span data-stu-id="890b0-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="890b0-120">此行为与其他容器控件的行为不同。</span><span class="sxs-lookup"><span data-stu-id="890b0-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="890b0-121">在其他容器控件中，子控件不是调整<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为`Left, Right`或`Top, Bottom`。</span><span class="sxs-lookup"><span data-stu-id="890b0-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2. <span data-ttu-id="890b0-122">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Top, Bottom`。</span><span class="sxs-lookup"><span data-stu-id="890b0-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="890b0-123">调整 <xref:System.Windows.Forms.Button> 控件的大小，以便在单元格中自上而下进行拉伸。</span><span class="sxs-lookup"><span data-stu-id="890b0-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3. <span data-ttu-id="890b0-124">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Top, Bottom, Left, Right`。</span><span class="sxs-lookup"><span data-stu-id="890b0-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="890b0-125">调整 <xref:System.Windows.Forms.Button> 控件的大小以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="890b0-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4. <span data-ttu-id="890b0-126">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `None`。</span><span class="sxs-lookup"><span data-stu-id="890b0-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="890b0-127">调整 <xref:System.Windows.Forms.Button> 控件控件的大小并在单元格中居中。</span><span class="sxs-lookup"><span data-stu-id="890b0-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5. <span data-ttu-id="890b0-128">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性值更改为 <xref:System.Windows.Forms.DockStyle.Left>。</span><span class="sxs-lookup"><span data-stu-id="890b0-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="890b0-129"><xref:System.Windows.Forms.Button> 控件移动，以便与单元格的左边框对齐。</span><span class="sxs-lookup"><span data-stu-id="890b0-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="890b0-130"><xref:System.Windows.Forms.Button> 控件的宽度不变，但调整其高度以垂直填充单元格。</span><span class="sxs-lookup"><span data-stu-id="890b0-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="890b0-131">这与其他容器控件中发生的行为相同。</span><span class="sxs-lookup"><span data-stu-id="890b0-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6. <span data-ttu-id="890b0-132">将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性值更改为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="890b0-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="890b0-133">调整 <xref:System.Windows.Forms.Button> 控件的大小以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="890b0-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="890b0-134">示例</span><span class="sxs-lookup"><span data-stu-id="890b0-134">Example</span></span>  
 <span data-ttu-id="890b0-135">下图显示了在五个单独的 <xref:System.Windows.Forms.TableLayoutPanel> 单元格中锚定的五个按钮。</span><span class="sxs-lookup"><span data-stu-id="890b0-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="890b0-136">![TableLayoutPanel 锚定](./media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="890b0-136">![TableLayoutPanel Anchoring](./media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="890b0-137">下图显示了在四个单独的 <xref:System.Windows.Forms.TableLayoutPanel> 单元格的角落中锚定的四个按钮。</span><span class="sxs-lookup"><span data-stu-id="890b0-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="890b0-138">![TableLayoutPanel 锚定](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="890b0-138">![TableLayoutPanel Anchoring](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="890b0-139">下图显示了在三个单独的 <xref:System.Windows.Forms.TableLayoutPanel> 单元格中通过锚定而拉伸的三个按钮。</span><span class="sxs-lookup"><span data-stu-id="890b0-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="890b0-140">![TableLayoutPanel 锚定](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="890b0-140">![TableLayoutPanel Anchoring](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="890b0-141">下面的代码示例演示 <xref:System.Windows.Forms.TableLayoutPanel> 控件中 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值的所有组合。</span><span class="sxs-lookup"><span data-stu-id="890b0-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="890b0-142">编译代码</span><span class="sxs-lookup"><span data-stu-id="890b0-142">Compiling the Code</span></span>  
 <span data-ttu-id="890b0-143">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="890b0-143">This example requires:</span></span>  
  
- <span data-ttu-id="890b0-144">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="890b0-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="890b0-145">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="890b0-145">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="890b0-146">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="890b0-146">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890b0-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="890b0-147">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="890b0-148">TableLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="890b0-148">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
