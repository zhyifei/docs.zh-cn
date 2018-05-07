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
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>如何：拉伸 ToolStripTextBox 以填充 ToolStrip 的其余宽度（Windows 窗体）
当你将设置<xref:System.Windows.Forms.ToolStrip.Stretch%2A>属性<xref:System.Windows.Forms.ToolStrip>控制转移到`true`，控件填充其容器端到端，并调整其大小调整大小时其容器。 在此配置中，你可能发现它可以在控件中，如拉伸项<xref:System.Windows.Forms.ToolStripTextBox>、 以填充可用空间和在调整大小时控件时调整大小。 此拉伸很有用，例如，如果你想要实现的外观和行为类似于在 Microsoft® Internet Explorer 的地址栏。  
  
## <a name="example"></a>示例  
 下面的代码示例提供从派生的类<xref:System.Windows.Forms.ToolStripTextBox>调用`ToolStripSpringTextBox`。 此类重写<xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A>方法来计算可用宽度的父级<xref:System.Windows.Forms.ToolStrip>后对所有其他项的组合的宽度已减去进行控制。 此代码示例还提供了<xref:System.Windows.Forms.Form>类和一个`Program`为了演示此新行为的类。  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [ToolStrip 控件体系结构](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [如何：在 StatusStrip 中以交互方式使用 Spring 属性](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
