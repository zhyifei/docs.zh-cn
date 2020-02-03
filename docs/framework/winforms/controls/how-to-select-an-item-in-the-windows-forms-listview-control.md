---
title: 选择 ListView 控件中的项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743228"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="11c6a-102">如何：选择 Windows 窗体 ListView 控件中的项</span><span class="sxs-lookup"><span data-stu-id="11c6a-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="11c6a-103">此示例演示如何以编程方式选择 Windows 窗体 <xref:System.Windows.Forms.ListView> 控件中的项。</span><span class="sxs-lookup"><span data-stu-id="11c6a-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="11c6a-104">以编程方式选择项并不会自动将焦点更改为 <xref:System.Windows.Forms.ListView> 控件。</span><span class="sxs-lookup"><span data-stu-id="11c6a-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="11c6a-105">出于此原因，在选择项时，通常还需要将项设置为聚焦项。</span><span class="sxs-lookup"><span data-stu-id="11c6a-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11c6a-106">示例</span><span class="sxs-lookup"><span data-stu-id="11c6a-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11c6a-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="11c6a-107">Compiling the Code</span></span>  
 <span data-ttu-id="11c6a-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="11c6a-108">This example requires:</span></span>  
  
- <span data-ttu-id="11c6a-109">一个名为 `listView1` 的 <xref:System.Windows.Forms.ListView> 控件，其中至少包含一项。</span><span class="sxs-lookup"><span data-stu-id="11c6a-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="11c6a-110">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="11c6a-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c6a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11c6a-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
