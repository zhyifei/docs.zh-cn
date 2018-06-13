---
title: 如何：更改 DataRepeater 控件的布局 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: fa780ee40171143c17b5bdbda4a97179ed5f2151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590837"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="8bcfb-102">如何：更改 DataRepeater 控件的布局 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8bcfb-102">How to: Change the Layout of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="8bcfb-103"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件可以显示在 （项目垂直滚动） 的垂直或水平 （项目水平滚动） 方向。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-103">The <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control can be displayed in either a vertical (items scroll vertically) or horizontal (items scroll horizontally) orientation.</span></span> <span data-ttu-id="8bcfb-104">你可以在设计时或在运行时将方向更改通过更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-104">You can change the orientation at design time or at run time by changing the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property.</span></span> <span data-ttu-id="8bcfb-105">如果你更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性在运行时，你可能还想要调整大小<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>和重新定位其子控件。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-105">If you change the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property at run time, you may also want to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and reposition the child controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bcfb-106">如果在重新定位控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>在运行时，你将需要调用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>方法的开头和结尾的代码块，重新定位控件。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-106">If you reposition controls on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> at run time, you will need to call the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> and <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> methods at the beginning and end of the code block that repositions the controls.</span></span>  
  
### <a name="to-change-the-layout-at-design-time"></a><span data-ttu-id="8bcfb-107">若要在设计时更改布局</span><span class="sxs-lookup"><span data-stu-id="8bcfb-107">To change the layout at design time</span></span>  
  
1.  <span data-ttu-id="8bcfb-108">在 Windows 窗体设计器中，选择<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8bcfb-109">您必须选择控件外边框的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>通过单击该控件，不在上面的下半部分区域的控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>区域。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-109">You must select the outer border of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control by clicking in the lower region of the control, not in the upper <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> region.</span></span>  
  
2.  <span data-ttu-id="8bcfb-110">在属性窗口中，设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性为<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical>或<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-110">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property to either <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span></span>  
  
### <a name="to-change-the-layout-at-run-time"></a><span data-ttu-id="8bcfb-111">若要在运行时更改布局</span><span class="sxs-lookup"><span data-stu-id="8bcfb-111">To change the layout at run time</span></span>  
  
1.  <span data-ttu-id="8bcfb-112">将以下代码添加到按钮或菜单`Click`事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="8bcfb-112">Add the following code to a button or menu `Click` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  <span data-ttu-id="8bcfb-113">在大多数情况下，你将想要添加类似于在示例部分中显示要调整大小的代码<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>和重新排列控件以适应新的方向。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-113">In most cases, you will want to add code similar to that shown in the Example section to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and rearrange controls to fit the new orientation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bcfb-114">示例</span><span class="sxs-lookup"><span data-stu-id="8bcfb-114">Example</span></span>  
 <span data-ttu-id="8bcfb-115">下面的示例演示如何响应<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged>事件处理程序中的事件。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-115">The following example shows how to respond to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> event in an event handler.</span></span> <span data-ttu-id="8bcfb-116">此示例要求你拥有<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件名为`DataRepeater1`在窗体和，其<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>包含两个<xref:System.Windows.Forms.TextBox>控件名为`TextBox1`和`TextBox2`。</span><span class="sxs-lookup"><span data-stu-id="8bcfb-116">This example requires that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control named `DataRepeater1` on a form and that its <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contain two <xref:System.Windows.Forms.TextBox> controls named `TextBox1` and `TextBox2`.</span></span>  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8bcfb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bcfb-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>  
 [<span data-ttu-id="8bcfb-118">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="8bcfb-118">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="8bcfb-119">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="8bcfb-119">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="8bcfb-120">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="8bcfb-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
