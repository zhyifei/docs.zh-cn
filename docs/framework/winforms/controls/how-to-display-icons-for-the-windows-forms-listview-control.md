---
title: 如何：显示 Windows 窗体 ListView 控件的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 8e4ae744eecbe894767114179dd63651828b191b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318606"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="0c93a-102">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="0c93a-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="0c93a-103">Windows 窗体<xref:System.Windows.Forms.ListView>控件可以显示来自三个图像列表的图标。</span><span class="sxs-lookup"><span data-stu-id="0c93a-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="0c93a-104">列表、 详细信息，以及 SmallIcon 视图中显示图像的图像列表中指定<xref:System.Windows.Forms.ListView.SmallImageList%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0c93a-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="0c93a-105">图标视图将从图像列表中指定的图像显示<xref:System.Windows.Forms.ListView.LargeImageList%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0c93a-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="0c93a-106">列表视图还可以显示一组额外的图标，在中设置<xref:System.Windows.Forms.ListView.StateImageList%2A>属性旁边的大或小图标。</span><span class="sxs-lookup"><span data-stu-id="0c93a-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="0c93a-107">有关图像列表的详细信息，请参阅[ImageList 组件](imagelist-component-windows-forms.md)和[如何：添加或删除图像与 Windows 窗体 ImageList 组件](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。</span><span class="sxs-lookup"><span data-stu-id="0c93a-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="0c93a-108">在列表视图中显示图像</span><span class="sxs-lookup"><span data-stu-id="0c93a-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="0c93a-109">设置相应的属性 —<xref:System.Windows.Forms.ListView.SmallImageList%2A>， <xref:System.Windows.Forms.ListView.LargeImageList%2A>，或<xref:System.Windows.Forms.ListView.StateImageList%2A>— 对现有<xref:System.Windows.Forms.ImageList>你想要使用的组件。</span><span class="sxs-lookup"><span data-stu-id="0c93a-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="0c93a-110">可以在属性窗口中，使用在设计器或在代码中设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="0c93a-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="0c93a-111">设置<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>或<xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A>每个都有一个关联的图标的列表项的属性。</span><span class="sxs-lookup"><span data-stu-id="0c93a-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="0c93a-112">可以设置这些属性，在代码中，或在**列表视图项集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="0c93a-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="0c93a-113">若要打开**列表视图项集合编辑器**，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.ListView.Items%2A>上的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="0c93a-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="0c93a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c93a-114">See also</span></span>

- [<span data-ttu-id="0c93a-115">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="0c93a-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="0c93a-116">如何：添加和删除使用 Windows 窗体 ListView 控件的项</span><span class="sxs-lookup"><span data-stu-id="0c93a-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0c93a-117">如何：将列添加到 Windows 窗体 ListView 控件</span><span class="sxs-lookup"><span data-stu-id="0c93a-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0c93a-118">如何：将自定义信息添加到 TreeView 或 ListView 控件 （Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0c93a-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="0c93a-119">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="0c93a-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
