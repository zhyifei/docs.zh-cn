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
ms.openlocfilehash: f616436671da449e4f7b47c0a5d0c1b576584a1a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312301"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="26a00-102">如何：对 Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="26a00-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="26a00-103">使用的分组功能<xref:System.Windows.Forms.ListView>控件，可以在组中显示的项的相关的集。</span><span class="sxs-lookup"><span data-stu-id="26a00-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="26a00-104">由包含组标题的水平组标头在屏幕上分隔这些组。</span><span class="sxs-lookup"><span data-stu-id="26a00-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="26a00-105">可以使用<xref:System.Windows.Forms.ListView>组以使大型列表对项目分组按字母顺序，按日期，或任何其他逻辑分组的导航。</span><span class="sxs-lookup"><span data-stu-id="26a00-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="26a00-106">下图显示了一些分组的项。</span><span class="sxs-lookup"><span data-stu-id="26a00-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="26a00-107">![ListView 组](./media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="26a00-107">![ListView Groups](./media/listviewgroups.gif "ListViewGroups")</span></span>  
<span data-ttu-id="26a00-108">ListView 的分组项</span><span class="sxs-lookup"><span data-stu-id="26a00-108">ListView grouped items</span></span>  
  
 <span data-ttu-id="26a00-109">若要启用分组，必须先创建一个或多个组在设计器中或以编程方式。</span><span class="sxs-lookup"><span data-stu-id="26a00-109">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="26a00-110">定义的组后，可将分配<xref:System.Windows.Forms.ListView>项目到组。</span><span class="sxs-lookup"><span data-stu-id="26a00-110">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="26a00-111">您还可以移动的项从一个组到另一个以编程方式。</span><span class="sxs-lookup"><span data-stu-id="26a00-111">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> <span data-ttu-id="26a00-112">组是仅适用于[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]当应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="26a00-112">groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="26a00-113">在早期操作系统上与组相关的任何代码不起作用和组将不会出现。</span><span class="sxs-lookup"><span data-stu-id="26a00-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="26a00-114">有关详细信息，请参阅 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="26a00-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="26a00-115">若要添加组</span><span class="sxs-lookup"><span data-stu-id="26a00-115">To add groups</span></span>  
  
1. <span data-ttu-id="26a00-116">使用 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 集合的 <xref:System.Windows.Forms.ListView.Groups%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="26a00-116">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="26a00-117">若要删除组</span><span class="sxs-lookup"><span data-stu-id="26a00-117">To remove groups</span></span>  
  
1. <span data-ttu-id="26a00-118">使用<xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>或<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>方法的<xref:System.Windows.Forms.ListView.Groups%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="26a00-118">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="26a00-119"><xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>方法中删除单个组;<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>方法从列表中移除所有组。</span><span class="sxs-lookup"><span data-stu-id="26a00-119">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="26a00-120">删除组不会删除该组中的项。</span><span class="sxs-lookup"><span data-stu-id="26a00-120">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="26a00-121">若要将项分配给组或组之间移动项</span><span class="sxs-lookup"><span data-stu-id="26a00-121">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="26a00-122">设置<xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType>各个项的属性。</span><span class="sxs-lookup"><span data-stu-id="26a00-122">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="26a00-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="26a00-123">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="26a00-124">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="26a00-124">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="26a00-125">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="26a00-125">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="26a00-126">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="26a00-126">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
