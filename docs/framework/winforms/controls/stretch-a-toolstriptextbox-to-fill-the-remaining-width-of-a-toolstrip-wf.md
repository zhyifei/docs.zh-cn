---
title: 如何：拉伸 ToolStripTextBox 以填充 ToolStrip 的其余宽度
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742840"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>如何：拉伸 ToolStripTextBox 以填充 ToolStrip 的其余宽度（Windows 窗体）
将 <xref:System.Windows.Forms.ToolStrip> 控件的 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 属性设置为 `true`时，控件将从端向端填充其容器，并在其容器调整大小时调整其大小。 在此配置中，你可能会发现在控件中拉伸项（如 <xref:System.Windows.Forms.ToolStripTextBox>）可以填充可用空间并在控件调整大小时调整大小。 例如，如果想要获得与 Microsoft® Internet Explorer 中的地址栏类似的外观和行为，此拉伸很有用。  
  
## <a name="example"></a>示例  
 下面的代码示例提供了一个派生自 `ToolStripSpringTextBox`<xref:System.Windows.Forms.ToolStripTextBox> 的类。 此类将重写 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 方法，以便在减去所有其他项的组合宽度之后计算父级 <xref:System.Windows.Forms.ToolStrip> 控件的可用宽度。 此代码示例还提供了一个 <xref:System.Windows.Forms.Form> 类和一个 `Program` 类来演示新行为。  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [如何：在 StatusStrip 中以交互方式使用 Spring 属性](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
