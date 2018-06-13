---
title: 如何：拉伸 ToolStripTextBox 以填充 ToolStrip 的其余宽度（Windows 窗体）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537715"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="c3e4e-102">如何：拉伸 ToolStripTextBox 以填充 ToolStrip 的其余宽度（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c3e4e-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="c3e4e-103">当你将设置<xref:System.Windows.Forms.ToolStrip.Stretch%2A>属性<xref:System.Windows.Forms.ToolStrip>控制转移到`true`，控件填充其容器端到端，并调整其大小调整大小时其容器。</span><span class="sxs-lookup"><span data-stu-id="c3e4e-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="c3e4e-104">在此配置中，你可能发现它可以在控件中，如拉伸项<xref:System.Windows.Forms.ToolStripTextBox>、 以填充可用空间和在调整大小时控件时调整大小。</span><span class="sxs-lookup"><span data-stu-id="c3e4e-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="c3e4e-105">此拉伸很有用，例如，如果你想要实现的外观和行为类似于在 Microsoft® Internet Explorer 的地址栏。</span><span class="sxs-lookup"><span data-stu-id="c3e4e-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3e4e-106">示例</span><span class="sxs-lookup"><span data-stu-id="c3e4e-106">Example</span></span>  
 <span data-ttu-id="c3e4e-107">下面的代码示例提供从派生的类<xref:System.Windows.Forms.ToolStripTextBox>调用`ToolStripSpringTextBox`。</span><span class="sxs-lookup"><span data-stu-id="c3e4e-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="c3e4e-108">此类重写<xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A>方法来计算可用宽度的父级<xref:System.Windows.Forms.ToolStrip>后对所有其他项的组合的宽度已减去进行控制。</span><span class="sxs-lookup"><span data-stu-id="c3e4e-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="c3e4e-109">此代码示例还提供了<xref:System.Windows.Forms.Form>类和一个`Program`为了演示此新行为的类。</span><span class="sxs-lookup"><span data-stu-id="c3e4e-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c3e4e-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="c3e4e-110">Compiling the Code</span></span>  
 <span data-ttu-id="c3e4e-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c3e4e-111">This example requires:</span></span>  
  
-   <span data-ttu-id="c3e4e-112">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c3e4e-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e4e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3e4e-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c3e4e-114">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="c3e4e-114">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="c3e4e-115">如何：在 StatusStrip 中以交互方式使用 Spring 属性</span><span class="sxs-lookup"><span data-stu-id="c3e4e-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
