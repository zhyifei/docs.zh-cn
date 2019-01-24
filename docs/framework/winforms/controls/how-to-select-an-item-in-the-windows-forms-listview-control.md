---
title: 如何：Windows 窗体 ListView 控件中选择一项
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
ms.openlocfilehash: ed3e68fbe77f194ed04d15f99a48657a32a13b50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644711"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="0070d-102">如何：Windows 窗体 ListView 控件中选择一项</span><span class="sxs-lookup"><span data-stu-id="0070d-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="0070d-103">此示例演示如何以编程方式在 Windows 窗体中选择一项<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="0070d-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="0070d-104">以编程方式选择某个项不会自动更改焦点<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="0070d-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="0070d-105">出于此原因，你通常还需要设置的项，因为聚焦时选择某一项。</span><span class="sxs-lookup"><span data-stu-id="0070d-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0070d-106">示例</span><span class="sxs-lookup"><span data-stu-id="0070d-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0070d-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="0070d-107">Compiling the Code</span></span>  
 <span data-ttu-id="0070d-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="0070d-108">This example requires:</span></span>  
  
-   <span data-ttu-id="0070d-109">一个<xref:System.Windows.Forms.ListView>名为控件`listView1`，其中包含至少一个项。</span><span class="sxs-lookup"><span data-stu-id="0070d-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="0070d-110">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="0070d-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0070d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="0070d-111">See also</span></span>
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
