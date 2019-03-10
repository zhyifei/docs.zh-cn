---
title: 如何：拉伸 ToolStripTextBox 以填充 ToolStrip （Windows 窗体） 的其余宽度
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 7a557a3d278c2b6d8d083b2ebf8c8129bc498afa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702758"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="97e5c-102">如何：拉伸 ToolStripTextBox 以填充 ToolStrip （Windows 窗体） 的其余宽度</span><span class="sxs-lookup"><span data-stu-id="97e5c-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="97e5c-103">当您将设置<xref:System.Windows.Forms.ToolStrip.Stretch%2A>的属性<xref:System.Windows.Forms.ToolStrip>控制对`true`，该控件填充其容器端到端，并调整其容器调整大小时。</span><span class="sxs-lookup"><span data-stu-id="97e5c-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="97e5c-104">在此配置中，您可能会很有帮助的控件中，如拉伸项<xref:System.Windows.Forms.ToolStripTextBox>、 以填充可用空间和调整时该控件调整大小的大小。</span><span class="sxs-lookup"><span data-stu-id="97e5c-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="97e5c-105">此拉伸很有用，例如，如果你想要实现的外观和行为类似于在 Microsoft® Internet Explorer 的地址栏。</span><span class="sxs-lookup"><span data-stu-id="97e5c-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97e5c-106">示例</span><span class="sxs-lookup"><span data-stu-id="97e5c-106">Example</span></span>  
 <span data-ttu-id="97e5c-107">下面的代码示例提供了派生自的类<xref:System.Windows.Forms.ToolStripTextBox>调用`ToolStripSpringTextBox`。</span><span class="sxs-lookup"><span data-stu-id="97e5c-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="97e5c-108">此类重写<xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A>方法来计算父级的可用宽度<xref:System.Windows.Forms.ToolStrip>减去所有其他项的组合的宽度后进行控制。</span><span class="sxs-lookup"><span data-stu-id="97e5c-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="97e5c-109">此代码示例还提供了<xref:System.Windows.Forms.Form>类和一个`Program`类演示新的行为。</span><span class="sxs-lookup"><span data-stu-id="97e5c-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97e5c-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="97e5c-110">Compiling the Code</span></span>  
 <span data-ttu-id="97e5c-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="97e5c-111">This example requires:</span></span>  
  
-   <span data-ttu-id="97e5c-112">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="97e5c-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e5c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="97e5c-113">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="97e5c-114">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="97e5c-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="97e5c-115">如何：在 StatusStrip 中以交互方式使用 Spring 属性</span><span class="sxs-lookup"><span data-stu-id="97e5c-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
