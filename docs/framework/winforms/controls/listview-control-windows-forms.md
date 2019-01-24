---
title: ListView 控件（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- lists
- checked list items [Windows Forms], Windows Forms controls
- user interface [Windows Forms], creating
- lists [Windows Forms], items with icons
- icons [Windows Forms], listing with items
- list views
- ListView control [Windows Forms]
- list controls [Windows Forms], List view
ms.assetid: 9f71cf5c-82da-488a-a04e-ef52c0817187
ms.openlocfilehash: 4472d2a46b27c75d06c5e4cd6fbab18842ed111c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591937"
---
# <a name="listview-control-windows-forms"></a><span data-ttu-id="7aa2a-102">ListView 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="7aa2a-102">ListView Control (Windows Forms)</span></span>
<span data-ttu-id="7aa2a-103">Windows 窗体 `ListView` 控件显示带图标的项列表。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-103">The Windows Forms `ListView` control displays a list of items with icons.</span></span> <span data-ttu-id="7aa2a-104">你可以使用列表视图创建类似 Windows 资源管理器右窗格的用户界面。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-104">You can use a list view to create a user interface like the right pane of Windows Explorer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7aa2a-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="7aa2a-105">In This Section</span></span>  
 [<span data-ttu-id="7aa2a-106">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="7aa2a-106">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 <span data-ttu-id="7aa2a-107">描述此控件及其主要功能和属性。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-107">Describes this control and its key features and properties.</span></span>  
  
 [<span data-ttu-id="7aa2a-108">如何：添加和删除使用 Windows 窗体 ListView 控件的项</span><span class="sxs-lookup"><span data-stu-id="7aa2a-108">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-109">描述如何从列表视图中添加或移除项。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-109">Describes how to add or remove items from a list view.</span></span>  
  
 [<span data-ttu-id="7aa2a-110">如何：将列添加到 Windows 窗体 ListView 控件</span><span class="sxs-lookup"><span data-stu-id="7aa2a-110">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-111">描述如何创建列，以显示每个列表项的相关信息。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-111">Describes how to create columns in order to display information about each list item.</span></span>  
  
 [<span data-ttu-id="7aa2a-112">如何：Windows 窗体 ListView 控件中显示图标</span><span class="sxs-lookup"><span data-stu-id="7aa2a-112">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-113">描述如何将列表视图与用于显示大图标或小图标的适当图像列表相关联。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-113">Describes how to associate a list view with an appropriate image list for displaying large or small icons.</span></span>  
  
 [<span data-ttu-id="7aa2a-114">如何：在使用 Windows 窗体 ListView 控件的列中显示子项</span><span class="sxs-lookup"><span data-stu-id="7aa2a-114">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-115">描述如何在列中显示每个列表项的相关信息。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-115">Describes how to display information about each list item in columns.</span></span>  
  
 [<span data-ttu-id="7aa2a-116">如何：Windows 窗体 ListView 控件中选择一项</span><span class="sxs-lookup"><span data-stu-id="7aa2a-116">How to: Select an Item in the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-117">描述如何以编程方式选择项。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-117">Describes how to programmatically select an item.</span></span>  
  
 [<span data-ttu-id="7aa2a-118">如何：Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="7aa2a-118">How to: Group Items in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-119">描述如何创建按分类顺序显示的组以及如何将项分配给每个组。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-119">Describes how to create groups for categorized display and how to assign items to each group.</span></span>  
  
 <span data-ttu-id="7aa2a-120">此功能仅适用于 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-120">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="7aa2a-121">如何：启用 Windows 窗体 ListView 控件中的磁贴视图</span><span class="sxs-lookup"><span data-stu-id="7aa2a-121">How to: Enable Tile View in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-122">描述如何将项显示为图块，其中每个图块由一个大图标和多行文本组成。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-122">Describes how to display items as tiles, each of which is comprised of a large icon and multiple lines of text.</span></span>  
  
 <span data-ttu-id="7aa2a-123">此功能仅适用于 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-123">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="7aa2a-124">如何：Windows 窗体 ListView 控件中显示插入标记</span><span class="sxs-lookup"><span data-stu-id="7aa2a-124">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="7aa2a-125">描述如何实现拖放操作的用户反馈，反馈中用插入标记指示每个鼠标指针位置的放置位置。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-125">Describes how to implement user-feedback for drag-and-drop operations in which an insertion mark indicates the drop location for each mouse-pointer position.</span></span>  
  
 <span data-ttu-id="7aa2a-126">此功能仅适用于 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-126">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="7aa2a-127">如何：向 ListView 控件添加搜索功能</span><span class="sxs-lookup"><span data-stu-id="7aa2a-127">How to: Add Search Capabilities to a ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 <span data-ttu-id="7aa2a-128">介绍如何以编程方式使用文本搜索或屏幕坐标查找项。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-128">Describes how to programmatically find an item using either text search or screen coordinates.</span></span>  
  
-   [<span data-ttu-id="7aa2a-129">如何：启用使用设计器的 Windows 窗体 ListView 控件中的磁贴视图</span><span class="sxs-lookup"><span data-stu-id="7aa2a-129">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>](enable-tile-view-in-a-wf-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7aa2a-130">如何：添加和删除项与使用设计器在 Windows 窗体 ListView 控件</span><span class="sxs-lookup"><span data-stu-id="7aa2a-130">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>](add-and-remove-items-with-wf-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7aa2a-131">如何：将列添加到使用设计器在 Windows 窗体 ListView 控件</span><span class="sxs-lookup"><span data-stu-id="7aa2a-131">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>](how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7aa2a-132">如何：使用设计器的 Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="7aa2a-132">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>](how-to-group-items-in-a-windows-forms-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="7aa2a-133">演练：创建带有 ListView 和 TreeView 控件使用设计器的资源管理器样式界面</span><span class="sxs-lookup"><span data-stu-id="7aa2a-133">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>](creating-an-explorer-style-interface-with-the-listview-and-treeview.md)  
  
## <a name="reference"></a><span data-ttu-id="7aa2a-134">参考</span><span class="sxs-lookup"><span data-stu-id="7aa2a-134">Reference</span></span>  
 <span data-ttu-id="7aa2a-135"><xref:System.Windows.Forms.ListView> 类</span><span class="sxs-lookup"><span data-stu-id="7aa2a-135"><xref:System.Windows.Forms.ListView> class</span></span>  
 <span data-ttu-id="7aa2a-136">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-136">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7aa2a-137">相关章节</span><span class="sxs-lookup"><span data-stu-id="7aa2a-137">Related Sections</span></span>  
 [<span data-ttu-id="7aa2a-138">如何：将自定义信息添加到 TreeView 或 ListView 控件 （Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="7aa2a-138">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 <span data-ttu-id="7aa2a-139">描述如何继承列表视图中的项或树视图中的节点，以添加所需的任何字段、方法或构造函数。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-139">Describes how to inherit from an item in a list view or a node in a tree view in order to add any fields, methods, or constructors you need.</span></span>  
  
 [<span data-ttu-id="7aa2a-140">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="7aa2a-140">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 <span data-ttu-id="7aa2a-141">说明图像列表是什么，以及其主要功能和属性。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-141">Explains what an image list is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="7aa2a-142">如何：用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="7aa2a-142">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="7aa2a-143">提供具有多个窗格的 Windows 窗体的布局说明。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-143">Gives instructions for laying out a Windows Form with multiple panes.</span></span>  
  
 [<span data-ttu-id="7aa2a-144">Windows XP 功能和 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7aa2a-144">Windows XP Features and Windows Forms Controls</span></span>](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 <span data-ttu-id="7aa2a-145">介绍如何充分利用适用于 <xref:System.Windows.Forms.ListView> 控件的 Windows XP 特定功能。</span><span class="sxs-lookup"><span data-stu-id="7aa2a-145">Explains how to take advantage of Windows XP-specific features that apply to the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa2a-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aa2a-146">See also</span></span>
- [<span data-ttu-id="7aa2a-147">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="7aa2a-147">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
