---
title: 如何：对 Windows 窗体 ListView 控件中的项进行分组
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
ms.openlocfilehash: b4cd2b9ed23f377912270d33b1415ad39c9e80c0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966635"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="411f6-102">如何：对 Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="411f6-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="411f6-103">通过<xref:System.Windows.Forms.ListView>控件的分组功能, 您可以在组中显示相关的项集。</span><span class="sxs-lookup"><span data-stu-id="411f6-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="411f6-104">这些组按包含组标题的水平组标头在屏幕上进行分隔。</span><span class="sxs-lookup"><span data-stu-id="411f6-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="411f6-105">你可以使用<xref:System.Windows.Forms.ListView>组, 通过按字母顺序、日期或任何其他逻辑分组对项进行分组来更轻松地导航大型列表。</span><span class="sxs-lookup"><span data-stu-id="411f6-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="411f6-106">下图显示了某些分组项。</span><span class="sxs-lookup"><span data-stu-id="411f6-106">The following image shows some grouped items.</span></span>  
  
 ![奇数甚至是 ListView 组的屏幕截图。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="411f6-108">若要启用分组, 必须先在设计器中或以编程方式创建一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="411f6-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="411f6-109">定义组后, 可以将项分配<xref:System.Windows.Forms.ListView>给组。</span><span class="sxs-lookup"><span data-stu-id="411f6-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="411f6-110">还可以通过编程方式将项从一个组移到另一个组。</span><span class="sxs-lookup"><span data-stu-id="411f6-110">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="411f6-111"><xref:System.Windows.Forms.ListView>[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]当应用程序<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>调用方法时, 组才可用。</span><span class="sxs-lookup"><span data-stu-id="411f6-111"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="411f6-112">在早期的操作系统上, 与组相关的任何代码都不起作用, 并且不会显示这些组。</span><span class="sxs-lookup"><span data-stu-id="411f6-112">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="411f6-113">有关详细信息，请参阅 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="411f6-113">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="411f6-114">添加组</span><span class="sxs-lookup"><span data-stu-id="411f6-114">To add groups</span></span>  
  
1. <span data-ttu-id="411f6-115">使用 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 集合的 <xref:System.Windows.Forms.ListView.Groups%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="411f6-115">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="411f6-116">删除组</span><span class="sxs-lookup"><span data-stu-id="411f6-116">To remove groups</span></span>  
  
1. <span data-ttu-id="411f6-117">使用集合的<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>或方法 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> <xref:System.Windows.Forms.ListView.Groups%2A> 。</span><span class="sxs-lookup"><span data-stu-id="411f6-117">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="411f6-118">方法移除单个组<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> ; 方法从列表中移除所有组。 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A></span><span class="sxs-lookup"><span data-stu-id="411f6-118">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="411f6-119">删除组不会删除该组中的项目。</span><span class="sxs-lookup"><span data-stu-id="411f6-119">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="411f6-120">向组分配项或在组之间移动项</span><span class="sxs-lookup"><span data-stu-id="411f6-120">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="411f6-121">设置各项的属性。<xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="411f6-121">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="411f6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="411f6-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="411f6-123">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="411f6-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="411f6-124">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="411f6-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="411f6-125">如何：通过 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="411f6-125">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
