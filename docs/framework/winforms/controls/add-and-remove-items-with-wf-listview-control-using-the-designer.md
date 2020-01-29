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
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="71ba5-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="71ba5-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="71ba5-103">将项添加到 Windows 窗体 <xref:System.Windows.Forms.ListView> 控件的过程主要包含指定项并为其分配属性。</span><span class="sxs-lookup"><span data-stu-id="71ba5-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="71ba5-104">可以随时添加或删除列表项。</span><span class="sxs-lookup"><span data-stu-id="71ba5-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="71ba5-105">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.ListView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="71ba5-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="71ba5-106">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="71ba5-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="71ba5-107">使用设计器添加或删除项</span><span class="sxs-lookup"><span data-stu-id="71ba5-107">To add or remove items using the designer</span></span>

1. <span data-ttu-id="71ba5-108"><xref:System.Windows.Forms.ListView> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71ba5-108">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="71ba5-109">在 "**属性**" 窗口中，单击 "<xref:System.Windows.Forms.ListView.Items%2A>" 属性旁边的**省略号**按钮（!["Visual](./media/visual-studio-ellipsis-button.png)Studio 的属性窗口中的省略号按钮（...）"。</span><span class="sxs-lookup"><span data-stu-id="71ba5-109">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="71ba5-110">此时将显示 " **ListViewItem 集合编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="71ba5-110">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="71ba5-111">若要添加项目，请单击 "**添加**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="71ba5-111">To add an item, click the **Add** button.</span></span> <span data-ttu-id="71ba5-112">然后，可以设置新项的属性，例如 <xref:System.Windows.Forms.ListView.Text%2A> 和 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="71ba5-112">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="71ba5-113">若要删除某个项，请选择该项，然后单击 "**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="71ba5-113">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="71ba5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71ba5-114">See also</span></span>

- [<span data-ttu-id="71ba5-115">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="71ba5-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="71ba5-116">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="71ba5-116">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="71ba5-117">방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="71ba5-117">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="71ba5-118">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="71ba5-118">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="71ba5-119">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="71ba5-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="71ba5-120">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="71ba5-120">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
