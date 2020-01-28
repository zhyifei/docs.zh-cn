---
title: 使用设计器在 TreeView 控件中添加和删除节点
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732252"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거

由于 Windows 窗体 <xref:System.Windows.Forms.TreeView> 控件以分层方式显示节点，因此在添加节点时，必须注意其父节点。

下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.TreeView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-add-or-remove-nodes-in-the-designer"></a>在设计器中添加或删除节点

1. <xref:System.Windows.Forms.TreeView> 컨트롤을 선택합니다.

2. 在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.TreeView.Nodes%2A>" 属性旁边的**省略号**按钮（!["Visual](./media/visual-studio-ellipsis-button.png)Studio 的属性窗口中的省略号按钮（...）"。

     此时将显示 " **TreeNode 节点编辑器**"。

3. 若要添加节点，根节点必须存在;如果不存在，则必须先通过单击 "**添加根**" 按钮添加一个根。 然后，可以通过选择根节点或任何其他节点，然后单击 "**添加子级**" 按钮来添加子节点。

4. 若要删除节点，请选择要删除的节点，然后单击 "**删除**" 按钮。

## <a name="see-also"></a>另请参阅

- [TreeView 컨트롤](treeview-control-windows-forms.md)
- [TreeView 컨트롤 개요](treeview-control-overview-windows-forms.md)
- [방법: Windows Forms TreeView 컨트롤의 아이콘 설정](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [방법: 클릭한 TreeView 노드 확인](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
