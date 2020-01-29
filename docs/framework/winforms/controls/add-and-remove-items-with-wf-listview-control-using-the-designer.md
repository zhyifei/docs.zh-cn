---
title: 使用设计器使用 ListView 控件添加和移除项
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732299"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 추가 및 제거

将项添加到 Windows 窗体 <xref:System.Windows.Forms.ListView> 控件的过程主要包含指定项并为其分配属性。 可以随时添加或删除列表项。

下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.ListView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-add-or-remove-items-using-the-designer"></a>使用设计器添加或删除项

1. <xref:System.Windows.Forms.ListView> 컨트롤을 선택합니다.

2. 在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.ListView.Items%2A>" 属性旁边的**省略号**按钮（!["Visual](./media/visual-studio-ellipsis-button.png)Studio 的属性窗口中的省略号按钮（...）"。

     此时将显示 " **ListViewItem 集合编辑器**"。

3. 若要添加项目，请单击 "**添加**" 按钮。 然后，可以设置新项的属性，例如 <xref:System.Windows.Forms.ListView.Text%2A> 和 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 属性。

4. 若要删除某个项，请选择该项，然后单击 "**删除**" 按钮。

## <a name="see-also"></a>另请参阅

- [ListView 컨트롤 개요](listview-control-overview-windows-forms.md)
- [방법: Windows Forms ListView 컨트롤에 열 추가](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [방법: Windows Forms ListView 컨트롤의 아이콘 표시](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [방법: Windows Forms ListView 컨트롤에서 항목 그룹화](how-to-group-items-in-a-windows-forms-listview-control.md)
