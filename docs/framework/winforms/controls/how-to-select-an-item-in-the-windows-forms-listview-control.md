---
title: "如何：选择 Windows 窗体 ListView 控件中的项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7acbda541000655ff96b70a2188169b7e8ccd9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="fa909-102">如何：选择 Windows 窗体 ListView 控件中的项</span><span class="sxs-lookup"><span data-stu-id="fa909-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="fa909-103">此示例演示如何以编程方式在 Windows 窗体中选择一个项<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="fa909-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="fa909-104">以编程方式选择项不会自动更改的焦点<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="fa909-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="fa909-105">为此，你将通常还想要将项设置为焦点时选择某一项。</span><span class="sxs-lookup"><span data-stu-id="fa909-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa909-106">示例</span><span class="sxs-lookup"><span data-stu-id="fa909-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa909-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="fa909-107">Compiling the Code</span></span>  
 <span data-ttu-id="fa909-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fa909-108">This example requires:</span></span>  
  
-   <span data-ttu-id="fa909-109">A<xref:System.Windows.Forms.ListView>控件名为`listView1`包含至少一个项。</span><span class="sxs-lookup"><span data-stu-id="fa909-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="fa909-110">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="fa909-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa909-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa909-111">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
