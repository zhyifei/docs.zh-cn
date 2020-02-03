---
title: ListView 控件
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
ms.openlocfilehash: 009739f78f334d09a9f7e4f0e9f171669014b909
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745144"
---
# <a name="listview-control-windows-forms"></a><span data-ttu-id="1751d-102">ListView 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="1751d-102">ListView Control (Windows Forms)</span></span>
<span data-ttu-id="1751d-103">Windows 窗体 `ListView` 控件显示带图标的项列表。</span><span class="sxs-lookup"><span data-stu-id="1751d-103">The Windows Forms `ListView` control displays a list of items with icons.</span></span> <span data-ttu-id="1751d-104">你可以使用列表视图创建类似 Windows 资源管理器右窗格的用户界面。</span><span class="sxs-lookup"><span data-stu-id="1751d-104">You can use a list view to create a user interface like the right pane of Windows Explorer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1751d-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="1751d-105">In This Section</span></span>  
 [<span data-ttu-id="1751d-106">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="1751d-106">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)  
 <span data-ttu-id="1751d-107">描述此控件及其主要功能和属性。</span><span class="sxs-lookup"><span data-stu-id="1751d-107">Describes this control and its key features and properties.</span></span>  
  
 [<span data-ttu-id="1751d-108">如何：使用 Windows 窗体 ListView 控件添加和删除项</span><span class="sxs-lookup"><span data-stu-id="1751d-108">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-109">描述如何从列表视图中添加或移除项。</span><span class="sxs-lookup"><span data-stu-id="1751d-109">Describes how to add or remove items from a list view.</span></span>  
  
 [<span data-ttu-id="1751d-110">如何：向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="1751d-110">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-111">描述如何创建列，以显示每个列表项的相关信息。</span><span class="sxs-lookup"><span data-stu-id="1751d-111">Describes how to create columns in order to display information about each list item.</span></span>  
  
 [<span data-ttu-id="1751d-112">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="1751d-112">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-113">描述如何将列表视图与用于显示大图标或小图标的适当图像列表相关联。</span><span class="sxs-lookup"><span data-stu-id="1751d-113">Describes how to associate a list view with an appropriate image list for displaying large or small icons.</span></span>  
  
 [<span data-ttu-id="1751d-114">如何：使用 Windows 窗体 ListView 控件在列中显示子项</span><span class="sxs-lookup"><span data-stu-id="1751d-114">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-115">描述如何在列中显示每个列表项的相关信息。</span><span class="sxs-lookup"><span data-stu-id="1751d-115">Describes how to display information about each list item in columns.</span></span>  
  
 [<span data-ttu-id="1751d-116">如何：选择 Windows 窗体 ListView 控件中的项</span><span class="sxs-lookup"><span data-stu-id="1751d-116">How to: Select an Item in the Windows Forms ListView Control</span></span>](how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-117">描述如何以编程方式选择项。</span><span class="sxs-lookup"><span data-stu-id="1751d-117">Describes how to programmatically select an item.</span></span>  
  
 [<span data-ttu-id="1751d-118">如何：在 Windows 窗体 ListView 控件中对项进行分组</span><span class="sxs-lookup"><span data-stu-id="1751d-118">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-119">描述如何创建按分类顺序显示的组以及如何将项分配给每个组。</span><span class="sxs-lookup"><span data-stu-id="1751d-119">Describes how to create groups for categorized display and how to assign items to each group.</span></span>  
  
 [<span data-ttu-id="1751d-120">如何：在 Windows 窗体 ListView 控件中启用平铺视图</span><span class="sxs-lookup"><span data-stu-id="1751d-120">How to: Enable Tile View in a Windows Forms ListView Control</span></span>](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-121">描述如何将项显示为图块，其中每个图块由一个大图标和多行文本组成。</span><span class="sxs-lookup"><span data-stu-id="1751d-121">Describes how to display items as tiles, each of which is comprised of a large icon and multiple lines of text.</span></span>  
  
 [<span data-ttu-id="1751d-122">如何：在 Windows 窗体 ListView 控件中显示插入标记</span><span class="sxs-lookup"><span data-stu-id="1751d-122">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="1751d-123">描述如何实现拖放操作的用户反馈，反馈中用插入标记指示每个鼠标指针位置的放置位置。</span><span class="sxs-lookup"><span data-stu-id="1751d-123">Describes how to implement user-feedback for drag-and-drop operations in which an insertion mark indicates the drop location for each mouse-pointer position.</span></span>  
  
 [<span data-ttu-id="1751d-124">如何：向 ListView 控件添加搜索功能</span><span class="sxs-lookup"><span data-stu-id="1751d-124">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)  
 <span data-ttu-id="1751d-125">介绍如何以编程方式使用文本搜索或屏幕坐标查找项。</span><span class="sxs-lookup"><span data-stu-id="1751d-125">Describes how to programmatically find an item using either text search or screen coordinates.</span></span>  
  
- [<span data-ttu-id="1751d-126">如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图</span><span class="sxs-lookup"><span data-stu-id="1751d-126">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>](enable-tile-view-in-a-wf-listview-control-using-the-designer.md)  
  
- [<span data-ttu-id="1751d-127">如何：使用设计器用 Windows 窗体 ListView 控件添加和删除项</span><span class="sxs-lookup"><span data-stu-id="1751d-127">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>](add-and-remove-items-with-wf-listview-control-using-the-designer.md)  
  
- [<span data-ttu-id="1751d-128">如何：使用设计器向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="1751d-128">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>](how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer.md)  
  
- [<span data-ttu-id="1751d-129">如何：使用设计器在 Windows 窗体 ListView 控件中对项进行分组</span><span class="sxs-lookup"><span data-stu-id="1751d-129">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>](how-to-group-items-in-a-windows-forms-listview-control-using-the-designer.md)  
  
- [<span data-ttu-id="1751d-130">演练：使用设计器创建带有 ListView 和 TreeView 控件的资源管理器样式界面</span><span class="sxs-lookup"><span data-stu-id="1751d-130">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>](creating-an-explorer-style-interface-with-the-listview-and-treeview.md)  
  
## <a name="reference"></a><span data-ttu-id="1751d-131">参考</span><span class="sxs-lookup"><span data-stu-id="1751d-131">Reference</span></span>  
 <span data-ttu-id="1751d-132"><xref:System.Windows.Forms.ListView> 类</span><span class="sxs-lookup"><span data-stu-id="1751d-132"><xref:System.Windows.Forms.ListView> class</span></span>  
 <span data-ttu-id="1751d-133">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="1751d-133">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1751d-134">相关章节</span><span class="sxs-lookup"><span data-stu-id="1751d-134">Related Sections</span></span>  
 [<span data-ttu-id="1751d-135">如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息</span><span class="sxs-lookup"><span data-stu-id="1751d-135">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 <span data-ttu-id="1751d-136">描述如何继承列表视图中的项或树视图中的节点，以添加所需的任何字段、方法或构造函数。</span><span class="sxs-lookup"><span data-stu-id="1751d-136">Describes how to inherit from an item in a list view or a node in a tree view in order to add any fields, methods, or constructors you need.</span></span>  
  
 [<span data-ttu-id="1751d-137">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="1751d-137">ImageList Component</span></span>](imagelist-component-windows-forms.md)  
 <span data-ttu-id="1751d-138">说明图像列表是什么，以及其主要功能和属性。</span><span class="sxs-lookup"><span data-stu-id="1751d-138">Explains what an image list is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="1751d-139">如何：使用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="1751d-139">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="1751d-140">提供具有多个窗格的 Windows 窗体的布局说明。</span><span class="sxs-lookup"><span data-stu-id="1751d-140">Gives instructions for laying out a Windows Form with multiple panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1751d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1751d-141">See also</span></span>

- [<span data-ttu-id="1751d-142">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="1751d-142">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
