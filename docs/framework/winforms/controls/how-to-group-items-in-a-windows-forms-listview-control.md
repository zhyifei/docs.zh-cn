---
title: 列表查看控件中的组项目
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141986"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="2aee0-102">如何：对 Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="2aee0-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="2aee0-103">使用<xref:System.Windows.Forms.ListView>控件的分组功能，可以分组显示相关的项目集。</span><span class="sxs-lookup"><span data-stu-id="2aee0-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="2aee0-104">这些组在屏幕上由包含组标题的水平组标题分隔。</span><span class="sxs-lookup"><span data-stu-id="2aee0-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="2aee0-105">您可以使用<xref:System.Windows.Forms.ListView>组通过按字母顺序、按日期或通过任何其他逻辑分组对项目进行分组，使导航大型列表变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="2aee0-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="2aee0-106">下图显示了一些分组项目。</span><span class="sxs-lookup"><span data-stu-id="2aee0-106">The following image shows some grouped items.</span></span>  
  
 ![奇数和偶数列表视图组的屏幕截图。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 <span data-ttu-id="2aee0-108">要启用分组，必须首先在设计器中或以编程方式创建一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="2aee0-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="2aee0-109">定义组后，可以将项目分配给<xref:System.Windows.Forms.ListView>组。</span><span class="sxs-lookup"><span data-stu-id="2aee0-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="2aee0-110">您还可以以编程方式将项目从一个组移动到另一个组。</span><span class="sxs-lookup"><span data-stu-id="2aee0-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="2aee0-111">添加组</span><span class="sxs-lookup"><span data-stu-id="2aee0-111">To add groups</span></span>  
  
1. <span data-ttu-id="2aee0-112">使用 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 集合的 <xref:System.Windows.Forms.ListView.Groups%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2aee0-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="2aee0-113">删除组</span><span class="sxs-lookup"><span data-stu-id="2aee0-113">To remove groups</span></span>  
  
1. <span data-ttu-id="2aee0-114">使用<xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>集合<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>的<xref:System.Windows.Forms.ListView.Groups%2A>或 方法。</span><span class="sxs-lookup"><span data-stu-id="2aee0-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="2aee0-115">该方法<xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>删除单个组;因此，该方法将删除单个组。该方法<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>从列表中删除所有组。</span><span class="sxs-lookup"><span data-stu-id="2aee0-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2aee0-116">删除组不会删除该组中的项目。</span><span class="sxs-lookup"><span data-stu-id="2aee0-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="2aee0-117">将项目分配给组或在组之间移动项目</span><span class="sxs-lookup"><span data-stu-id="2aee0-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="2aee0-118">设置<xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType>单个项的属性。</span><span class="sxs-lookup"><span data-stu-id="2aee0-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="2aee0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2aee0-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="2aee0-120">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="2aee0-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="2aee0-121">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="2aee0-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="2aee0-122">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="2aee0-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
