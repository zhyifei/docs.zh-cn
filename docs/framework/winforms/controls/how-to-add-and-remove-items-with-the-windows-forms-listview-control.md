---
title: 如何：使用 Windows 窗体 ListView 控件添加和移除项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 8a97d73b9b2c46d02ae0794ad66b20a04db58af6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327654"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="6b411-102">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="6b411-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="6b411-103">将项添加到 Windows 窗体的过程<xref:System.Windows.Forms.ListView>控件主要包括指定项并为其分配属性。</span><span class="sxs-lookup"><span data-stu-id="6b411-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="6b411-104">可在任何时间完成添加或删除列表项。</span><span class="sxs-lookup"><span data-stu-id="6b411-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="6b411-105">若要以编程方式添加项</span><span class="sxs-lookup"><span data-stu-id="6b411-105">To add items programmatically</span></span>  
  
1. <span data-ttu-id="6b411-106">使用<xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A>方法的<xref:System.Windows.Forms.ListView.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6b411-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="6b411-107">若要以编程方式删除项目</span><span class="sxs-lookup"><span data-stu-id="6b411-107">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="6b411-108">使用<xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>或<xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>方法的<xref:System.Windows.Forms.ListView.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6b411-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="6b411-109"><xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>方法中删除单个项;<xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>方法从列表中移除所有项。</span><span class="sxs-lookup"><span data-stu-id="6b411-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="6b411-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b411-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="6b411-111">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="6b411-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="6b411-112">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="6b411-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
