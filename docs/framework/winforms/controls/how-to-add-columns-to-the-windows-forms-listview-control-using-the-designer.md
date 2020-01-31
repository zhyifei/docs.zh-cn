---
title: 使用设计器向 ListView 控件添加列
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744607"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에 열 추가

当在**详细信息**视图中时，Windows 窗体 <xref:System.Windows.Forms.ListView> 控件可以为每个列表项显示多个列。 您可以使用这些列显示有关每个列表项的多种类型的信息。 例如，文件列表可以显示文件的名称、文件类型、大小和文件的上次修改日期。 有关创建列后对其进行填充的信息，请参阅[如何：用 Windows 窗体 ListView 控件在列中显示子项](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)。

下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.ListView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-add-columns-in-the-designer"></a>在设计器中添加列

1. 在 "**属性**" 窗口中，将控件的 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Details>。

2. 在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.ListView.Columns%2A>" 属性旁边的**省略号**按钮（![](./media/visual-studio-ellipsis-button.png)）属性窗口中的省略号按钮（...）。

     此时将显示 " **ColumnHeader 集合编辑器**"。

3. 使用 "**添加**" 按钮添加新列。 然后，可以选择列标题并设置其文本（列标题）、文本对齐方式和宽度。

## <a name="see-also"></a>另请参阅

- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤의 아이콘 표시](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
