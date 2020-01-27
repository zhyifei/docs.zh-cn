---
title: 使用设计器冻结 DataGridView 控件中的列
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: af8e07d7b1b0524e33688fd9d879818aa13be041
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745677"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정
사용자가 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시된 데이터를 볼 때 단일 열이나 열 집합을 자주 참조해야 하는 경우가 있습니다. 例如，当你显示包含多个列的客户信息表时，你可以在任何时候显示客户名称，同时允许其他列在可见区域外滚动。

 이 동작을 얻기 위해 컨트롤에서 열을 고정할 수 있습니다. 열을 고정하는 경우 왼쪽(또는 오른쪽에서 왼쪽 언어 스크립트의 경우 오른쪽)에 있는 모든 열도 고정됩니다. 다른 모든 열을 스크롤할 수 있는 동안 고정된 열은 그대로 유지됩니다. 열 다시 정렬을 사용하는 경우 고정된 열은 고정되지 않은 열과 별개인 그룹으로 처리됩니다. 사용자는 각 그룹에서 열의 위치를 변경할 수 있지만 그룹 간에 열을 이동할 수는 없습니다.

 下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-freeze-a-column-using-the-designer"></a>使用设计器冻结列

1. 单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），然后选择 "**编辑列**"。

2. 从 "**选定的列**" 列表中选择一列。

3. 在 "**列属性**" 网格中，将 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 属性设置为 `true`。

    > [!NOTE]
    > 您还可以通过在 "**添加列**" 对话框中选择**冻结**框来添加该列。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- [如何：在 Windows 窗体中为全球化显示从右到左的文本](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
