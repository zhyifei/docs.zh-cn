---
title: 如何：使用 LineShape 控件 (Visual Studio) 绘制直线
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 46360c01dfaf2c6fe199725a9ecfba2248c72d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596223"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="5d203-102">如何：使用 LineShape 控件 (Visual Studio) 绘制直线</span><span class="sxs-lookup"><span data-stu-id="5d203-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="5d203-103">可以使用<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件在设计时和运行时窗体或容器上绘制水平线、 垂直线或对角线的线条。</span><span class="sxs-lookup"><span data-stu-id="5d203-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="5d203-104">**请注意**您的计算机可能会显示不同的名称或位置的某些 Visual Studio 用户界面元素中的以下说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="5d203-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="5d203-105">这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。</span><span class="sxs-lookup"><span data-stu-id="5d203-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="5d203-106">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="5d203-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="5d203-107">若要在设计时绘制线条</span><span class="sxs-lookup"><span data-stu-id="5d203-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="5d203-108">拖动<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件从**Visual Basic PowerPacks**选项卡中**工具箱**拖动到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="5d203-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="5d203-109">拖动调整大小并移动图柄来调整大小和位置的行。</span><span class="sxs-lookup"><span data-stu-id="5d203-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="5d203-110">您还可以调整大小和更改来定位行`X1`， `X2`， `Y1`，和`Y2`中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="5d203-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="5d203-111">在中**属性**窗口中，根据需要设置其他属性等`BorderStyle`或`BorderColor`来更改行的外观。</span><span class="sxs-lookup"><span data-stu-id="5d203-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="5d203-112">若要在运行时绘制线条</span><span class="sxs-lookup"><span data-stu-id="5d203-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="5d203-113">在“项目”菜单上，单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="5d203-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="5d203-114">在中**添加引用**对话框中，选择**Microsoft.VisualBasic.PowerPacks.VS**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d203-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5d203-115">在中**代码编辑器**，添加`Imports`或`using`模块顶部的语句：</span><span class="sxs-lookup"><span data-stu-id="5d203-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="5d203-116">在 `Event` 过程中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5d203-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5d203-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d203-117">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.LineShape>
- [<span data-ttu-id="5d203-118">Line 和 Shape 控件简介</span><span class="sxs-lookup"><span data-stu-id="5d203-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
- [<span data-ttu-id="5d203-119">如何：使用 OvalShape 和 RectangleShape 控件绘制形状</span><span class="sxs-lookup"><span data-stu-id="5d203-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
