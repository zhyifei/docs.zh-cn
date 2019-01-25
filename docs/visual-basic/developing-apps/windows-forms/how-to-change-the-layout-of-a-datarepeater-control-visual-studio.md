---
title: 如何：更改 DataRepeater 控件 (Visual Studio) 的布局
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: 3389daa6383444b48faab4c5383b281e44349bce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625596"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="785e6-102">如何：更改 DataRepeater 控件 (Visual Studio) 的布局</span><span class="sxs-lookup"><span data-stu-id="785e6-102">How to: Change the Layout of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="785e6-103"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件可以显示在 （项目垂直滚动） 的垂直或水平 （项目水平滚动） 方向。</span><span class="sxs-lookup"><span data-stu-id="785e6-103">The <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control can be displayed in either a vertical (items scroll vertically) or horizontal (items scroll horizontally) orientation.</span></span> <span data-ttu-id="785e6-104">可以通过更改更改在设计时或在运行时的方向<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="785e6-104">You can change the orientation at design time or at run time by changing the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property.</span></span> <span data-ttu-id="785e6-105">如果您更改<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性在运行时，可能还想要重设大小<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>和重新定位其子控件。</span><span class="sxs-lookup"><span data-stu-id="785e6-105">If you change the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property at run time, you may also want to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and reposition the child controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="785e6-106">如果在重新定位控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>在运行时，你将需要调用<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>和<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>开头和末尾重新定位控件的代码块的方法。</span><span class="sxs-lookup"><span data-stu-id="785e6-106">If you reposition controls on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> at run time, you will need to call the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> and <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> methods at the beginning and end of the code block that repositions the controls.</span></span>  
  
### <a name="to-change-the-layout-at-design-time"></a><span data-ttu-id="785e6-107">若要在设计时更改布局</span><span class="sxs-lookup"><span data-stu-id="785e6-107">To change the layout at design time</span></span>  
  
1.  <span data-ttu-id="785e6-108">在 Windows 窗体设计器中，选择<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="785e6-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="785e6-109">必须选择的外部边框<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>通过单击该控件，不是右上角的下半部分区域的控件<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>区域。</span><span class="sxs-lookup"><span data-stu-id="785e6-109">You must select the outer border of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control by clicking in the lower region of the control, not in the upper <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> region.</span></span>  
  
2.  <span data-ttu-id="785e6-110">在属性窗口中设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>属性设置为任一<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical>或<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>。</span><span class="sxs-lookup"><span data-stu-id="785e6-110">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property to either <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span></span>  
  
### <a name="to-change-the-layout-at-run-time"></a><span data-ttu-id="785e6-111">若要在运行时更改布局</span><span class="sxs-lookup"><span data-stu-id="785e6-111">To change the layout at run time</span></span>  
  
1.  <span data-ttu-id="785e6-112">将以下代码添加到按钮或菜单`Click`事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="785e6-112">Add the following code to a button or menu `Click` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  <span data-ttu-id="785e6-113">在大多数情况下，你将想要添加代码类似于示例部分中所显示的调整大小的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>和重新排列控件大小以适应新的方向。</span><span class="sxs-lookup"><span data-stu-id="785e6-113">In most cases, you will want to add code similar to that shown in the Example section to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and rearrange controls to fit the new orientation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="785e6-114">示例</span><span class="sxs-lookup"><span data-stu-id="785e6-114">Example</span></span>  
 <span data-ttu-id="785e6-115">下面的示例演示如何响应<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged>事件处理程序中的事件。</span><span class="sxs-lookup"><span data-stu-id="785e6-115">The following example shows how to respond to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> event in an event handler.</span></span> <span data-ttu-id="785e6-116">此示例要求具有<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>名为控件`DataRepeater1`窗体上其<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>包含两个<xref:System.Windows.Forms.TextBox>控件分别命名为`TextBox1`和`TextBox2`。</span><span class="sxs-lookup"><span data-stu-id="785e6-116">This example requires that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control named `DataRepeater1` on a form and that its <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contain two <xref:System.Windows.Forms.TextBox> controls named `TextBox1` and `TextBox2`.</span></span>  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="785e6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="785e6-117">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [<span data-ttu-id="785e6-118">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="785e6-118">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="785e6-119">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="785e6-119">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="785e6-120">如何：更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="785e6-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
