---
title: 如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: d03355dbf7f8b9025e7d86e9930c6b96567b6b7d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43420012"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列
用户查看 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据时，有时需要频繁地引用单个列或列集。 例如，显示客户信息，其中包含许多列的表，请时很有用，以便在所有时间的同时使其他列的可见区域外滚动显示客户名称。  
  
 若要实现此行为，可冻结控件中的列。 冻结列时，也将冻结其左侧（在从右到左的语言脚本中为右侧）的所有列。 冻结的列保持不变，而所有其他列可以滚动。 如果启用了列重新排序，冻结的列被视为一组不同于未冻结的列。 用户可重新定位任一组中的列，但不能将列从一个组移到另一组。  
  
 下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-freeze-a-column-using-the-designer"></a>若要冻结的列使用设计器  
  
1.  单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后选择**编辑列**。  
  
2.  选择一列从**选定列**列表。  
  
3.  在中**列属性**网格中，设置<xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>属性设置为`true`。  
  
    > [!NOTE]
    >  通过选择添加时，还可以冻结列**冻结**框中**添加列**对话框。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>  
 [如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [如何：使用设计器在 Windows 窗体 DataGridView 控件中启用列重新排序](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 [如何： 为全球化 Windows 窗体中显示从右到左文本](https://msdn.microsoft.com/library/f0663385-2354-4c65-8676-706422283b14)  
 [如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
