---
title: 如何：设计非常适合本地化的 Windows 窗体布局
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: c1aa62413e1c9cc29507b7b0ed5cbf1c5fcea26a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928558"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>如何：设计非常适合本地化的 Windows 窗体布局
创建可供进行本地化的窗体极大地加速了国际市场的开发。 可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件实现在控件因 <xref:System.Windows.Forms.Control.Text%2A> 属性值更改而调整大小时正常响应的布局。  
  
## <a name="example"></a>示例  
 此窗体演示如何创建在将显示的字符串值翻译成其它语言时按比例进行调整的布局。 这一翻译过程称为*本地化*。 有关详细信息，请参阅[本地化](../../../standard/globalization-localization/localization.md)。  
  
 Visual Studio 中对此任务提供广泛支持。  另请参阅演练： [创建调整本地化](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))比例的布局。  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a>其他资源

1. [如何：在 TableLayoutPanel 控件中对齐和拉伸控件](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [如何：跨越 TableLayoutPanel 控件中的行和列](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [如何：编辑 TableLayoutPanel 控件中的列和行](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [演练：使用 Windows 窗体控件上的智能标记执行常见任务](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [演练：通过填充、边距和 AutoSize 属性排放 Windows 窗体控件](windows-forms-controls-padding-autosize.md)  
  
8. [如何：支持使用 AutoSize 和 TableLayoutPanel 控件进行 Windows 窗体本地化](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))  
  
9. [演练：创建用于数据输入的大小可调的 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [本地化](../../../standard/globalization-localization/localization.md)
