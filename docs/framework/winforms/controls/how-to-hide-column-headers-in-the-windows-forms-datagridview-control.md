---
title: "如何：隐藏 Windows 窗体 DataGridView 控件中的列标题"
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
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18217f2edea5fde5f1f3b2d776cdacced15c73fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="35a53-102">如何：隐藏 Windows 窗体 DataGridView 控件中的列标题</span><span class="sxs-lookup"><span data-stu-id="35a53-102">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="35a53-103">有时你将想要显示<xref:System.Windows.Forms.DataGridView>无列标题。</span><span class="sxs-lookup"><span data-stu-id="35a53-103">Sometimes you will want to display a <xref:System.Windows.Forms.DataGridView> without column headers.</span></span> <span data-ttu-id="35a53-104">在<xref:System.Windows.Forms.DataGridView>控件，<xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A>属性值确定是否显示列标题。</span><span class="sxs-lookup"><span data-stu-id="35a53-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> property value determines whether the column headers are displayed.</span></span>  
  
### <a name="to-hide-the-column-headers"></a><span data-ttu-id="35a53-105">若要隐藏列标题</span><span class="sxs-lookup"><span data-stu-id="35a53-105">To hide the column headers</span></span>  
  
-   <span data-ttu-id="35a53-106">将 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="35a53-106">Set the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="35a53-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="35a53-107">Compiling the Code</span></span>  
 <span data-ttu-id="35a53-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="35a53-108">This example requires:</span></span>  
  
-   <span data-ttu-id="35a53-109">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="35a53-109">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="35a53-110">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="35a53-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a53-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35a53-111">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="35a53-112">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="35a53-112">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
