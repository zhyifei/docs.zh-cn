---
title: 如何：在 Windows 窗体中访问键控集合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: 59e5cea29ee520b1f13f8fae98ae4042cc86fef7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538721"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a><span data-ttu-id="e863e-102">如何：在 Windows 窗体中访问键控集合</span><span class="sxs-lookup"><span data-stu-id="e863e-102">How to: Access Keyed Collections in Windows Forms</span></span>
-   <span data-ttu-id="e863e-103">可通过键访问单个集合项。</span><span class="sxs-lookup"><span data-stu-id="e863e-103">You can access individual collection items by key.</span></span> <span data-ttu-id="e863e-104">此功能已添加到 Windows 窗体应用程序通常使用的许多集合类。</span><span class="sxs-lookup"><span data-stu-id="e863e-104">This functionality has been added to many collection classes that are typically used by Windows Forms applications.</span></span> <span data-ttu-id="e863e-105">以下列表显示了一些具有可访问键控的集合的集合类：</span><span class="sxs-lookup"><span data-stu-id="e863e-105">The following list shows some of the collection classes that have accessible keyed collections:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 <span data-ttu-id="e863e-106">与集合中的项关联的密钥通常是项的名称。</span><span class="sxs-lookup"><span data-stu-id="e863e-106">The key associated with an item in a collection is typically the name of the item.</span></span> <span data-ttu-id="e863e-107">下面的过程演示如何使用集合类来执行常见任务。</span><span class="sxs-lookup"><span data-stu-id="e863e-107">The following procedures show you how to use collection classes to perform common tasks.</span></span>  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a><span data-ttu-id="e863e-108">若要查找并将焦点移至控件集合中的嵌套控件</span><span class="sxs-lookup"><span data-stu-id="e863e-108">To find and give focus to a nested control in a control collection</span></span>  
  
-   <span data-ttu-id="e863e-109">使用<xref:System.Windows.Forms.Control.ControlCollection.Find%2A>和<xref:System.Windows.Forms.Control.Focus%2A>方法以指定要查找并设置焦点的控件的名称。</span><span class="sxs-lookup"><span data-stu-id="e863e-109">Use the <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> and <xref:System.Windows.Forms.Control.Focus%2A> methods to specify the name of the control to find and give focus to.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a><span data-ttu-id="e863e-110">若要访问图像集合中的图像</span><span class="sxs-lookup"><span data-stu-id="e863e-110">To access an image in an image collection</span></span>  
  
-   <span data-ttu-id="e863e-111">使用<xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A>属性来指定想要访问的图像的名称。</span><span class="sxs-lookup"><span data-stu-id="e863e-111">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> property to specify the name of the image you want to access.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a><span data-ttu-id="e863e-112">要设置为已选定选项卡的选项卡页</span><span class="sxs-lookup"><span data-stu-id="e863e-112">To set a tab page as the selected tab</span></span>  
  
-   <span data-ttu-id="e863e-113">使用<xref:System.Windows.Forms.TabControl.SelectedTab%2A>属性连同<xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A>属性来指定要将设置为已选定选项卡的选项卡页的名称。</span><span class="sxs-lookup"><span data-stu-id="e863e-113">Use the <xref:System.Windows.Forms.TabControl.SelectedTab%2A> property together with the <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> property to specify the name of the tab page to set as the selected tab.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e863e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e863e-114">See Also</span></span>  
 [<span data-ttu-id="e863e-115">Windows 窗体入门</span><span class="sxs-lookup"><span data-stu-id="e863e-115">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="e863e-116">如何：使用 Windows 窗体 ImageList 组件添加或删除图像</span><span class="sxs-lookup"><span data-stu-id="e863e-116">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
