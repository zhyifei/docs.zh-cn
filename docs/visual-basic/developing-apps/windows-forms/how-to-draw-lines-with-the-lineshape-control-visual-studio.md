---
title: 如何：使用 LineShape 控件绘制直线 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 5e1a837578aab4b4609a58ffee46406b022b8f97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587340"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="134c2-102">如何：使用 LineShape 控件绘制直线 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="134c2-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="134c2-103">你可以使用<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件在设计时和运行时窗体或容器上绘制水平线、 垂直线或对角线行。</span><span class="sxs-lookup"><span data-stu-id="134c2-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="134c2-104">**请注意**你的计算机中出现可能会不同名称或位置的某些 Visual Studio 用户界面元素下面的说明。</span><span class="sxs-lookup"><span data-stu-id="134c2-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="134c2-105">这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。</span><span class="sxs-lookup"><span data-stu-id="134c2-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="134c2-106">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="134c2-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="134c2-107">若要在设计时绘制线条</span><span class="sxs-lookup"><span data-stu-id="134c2-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="134c2-108">拖动<xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件从**Visual Basic PowerPacks**选项卡中**工具箱**将拖动到窗体或容器的控件。</span><span class="sxs-lookup"><span data-stu-id="134c2-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="134c2-109">拖动调整大小并移动图柄大小和位置的行。</span><span class="sxs-lookup"><span data-stu-id="134c2-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="134c2-110">您还可以调整大小和通过更改定位直线`X1`， `X2`， `Y1`，和`Y2`中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="134c2-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="134c2-111">在**属性**窗口中，根据需要设置其他属性如`BorderStyle`或`BorderColor`若要更改的行的外观。</span><span class="sxs-lookup"><span data-stu-id="134c2-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="134c2-112">若要在运行时绘制线条</span><span class="sxs-lookup"><span data-stu-id="134c2-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="134c2-113">在“项目”菜单上，单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="134c2-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="134c2-114">在**添加引用**对话框中，选择**Microsoft.VisualBasic.PowerPacks.VS**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="134c2-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="134c2-115">在**代码编辑器**，添加`Imports`或`using`语句模块的顶部：</span><span class="sxs-lookup"><span data-stu-id="134c2-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="134c2-116">在 `Event` 过程中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="134c2-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="134c2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="134c2-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="134c2-118">Line 和 Shape 控件简介</span><span class="sxs-lookup"><span data-stu-id="134c2-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="134c2-119">如何：使用 OvalShape 和 RectangleShape 控件绘制形状</span><span class="sxs-lookup"><span data-stu-id="134c2-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
