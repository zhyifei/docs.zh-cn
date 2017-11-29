---
title: "如何：使用 Tab 键在形状之间切换 (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a39957ffaa67d6abeb6d394ae9826d42ad2230de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a><span data-ttu-id="b5ad5-102">如何：使用 Tab 键在形状之间切换 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="b5ad5-102">How to: Enable Tabbing Between Shapes (Visual Studio)</span></span>
<span data-ttu-id="b5ad5-103">Line 和 shape 控件不具有`TabStop`或`TabIndex`属性，但你仍然可以启用它们之间按 tab 键。</span><span class="sxs-lookup"><span data-stu-id="b5ad5-103">Line and shape controls do not have `TabStop` or `TabIndex` properties, but you can still enable tabbing among them.</span></span> <span data-ttu-id="b5ad5-104">在下面的示例中，按 CTRL 和 TAB 键将选项卡之间形状;按 TAB 键仅按钮之间将选项卡上。</span><span class="sxs-lookup"><span data-stu-id="b5ad5-104">In the following example, pressing both the CTRL and the TAB keys will tab between shapes; pressing only the TAB key will tab between the buttons.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5ad5-105">以下说明中的某些 Visual Studio 用户界面元素在计算机上出现的名称或位置可能会不同。</span><span class="sxs-lookup"><span data-stu-id="b5ad5-105">Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="b5ad5-106">这些元素取决于你所使用的 Visual Studio 版本和你所使用的设置。</span><span class="sxs-lookup"><span data-stu-id="b5ad5-106">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="b5ad5-107">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="b5ad5-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="to-enable-tabbing-among-shapes"></a><span data-ttu-id="b5ad5-108">若要启用按 tab 键在形状之间</span><span class="sxs-lookup"><span data-stu-id="b5ad5-108">To enable tabbing among shapes</span></span>  
  
1.  <span data-ttu-id="b5ad5-109">将三个<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>控件和第二个<xref:System.Windows.Forms.Button>控件从**工具箱**到窗体。</span><span class="sxs-lookup"><span data-stu-id="b5ad5-109">Drag three <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls and two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to a form.</span></span>  
  
2.  <span data-ttu-id="b5ad5-110">在**代码编辑器**，添加`Imports`或`using`语句模块的顶部：</span><span class="sxs-lookup"><span data-stu-id="b5ad5-110">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  <span data-ttu-id="b5ad5-111">在事件过程中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="b5ad5-111">Add the following code in an event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  <span data-ttu-id="b5ad5-112">添加下面的代码`Button1_PreviewKeyDown`事件过程：</span><span class="sxs-lookup"><span data-stu-id="b5ad5-112">Add the following code in the `Button1_PreviewKeyDown` event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b5ad5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5ad5-113">See Also</span></span>  
 [<span data-ttu-id="b5ad5-114">如何：使用 OvalShape 和 RectangleShape 控件绘制形状</span><span class="sxs-lookup"><span data-stu-id="b5ad5-114">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [<span data-ttu-id="b5ad5-115">如何：使用 LineShape 控件绘制直线</span><span class="sxs-lookup"><span data-stu-id="b5ad5-115">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [<span data-ttu-id="b5ad5-116">Line 和 Shape 控件简介</span><span class="sxs-lookup"><span data-stu-id="b5ad5-116">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
