---
title: 使用设计器在 DataGridView 控件中启用列重新排序
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 14dc1081a8608c6e6add67f641c4b55825d2fc81
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626966"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器在 Windows 窗体的 DataGridView 控件中启用列重新排序
查看 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据时，用户有时需要比较特定列中的值。 如果在控件中广泛地分隔列，则这会很不方便，尤其是在用户必须水平来回滚动以便查看他们感兴趣的所有列时。 您可以通过使您的用户能够对列进行重新排序，使比较列值的任务变得更容易。 启用列重新排序后，用户可以通过用鼠标拖动列标题来将列移动到新位置。

 下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-enable-column-reordering"></a>启用列重新排序

- 单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的设计器操作标志符号（![小黑色箭头](./media/designer-actions-glyph.gif)），然后选择 "**启用列重新排序**"。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [如何：使用设计器在 Windows 窗体 DataGridView 控件中冻结列](freeze-columns-in-the-datagrid-using-the-designer.md)
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
