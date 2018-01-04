---
title: "如何：为 Windows 窗体 DataGridView 控件中的新行指定默认值"
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
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26f2ab0247c9d13a90560337c103a970afc8996c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="aba23-102">如何：为 Windows 窗体 DataGridView 控件中的新行指定默认值</span><span class="sxs-lookup"><span data-stu-id="aba23-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="aba23-103">当应用程序在默认填充新添加的行的值时，可以使数据输入更方便。</span><span class="sxs-lookup"><span data-stu-id="aba23-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="aba23-104">与<xref:System.Windows.Forms.DataGridView>类，你可以填充默认值与<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>事件。</span><span class="sxs-lookup"><span data-stu-id="aba23-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="aba23-105">当用户输入新记录的行时，引发此事件。</span><span class="sxs-lookup"><span data-stu-id="aba23-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="aba23-106">当你的代码处理此事件时，你可以填充具有你选择的值的所需单元格。</span><span class="sxs-lookup"><span data-stu-id="aba23-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="aba23-107">下面的代码示例演示如何指定使用的新行的默认值<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>事件。</span><span class="sxs-lookup"><span data-stu-id="aba23-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aba23-108">示例</span><span class="sxs-lookup"><span data-stu-id="aba23-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aba23-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="aba23-109">Compiling the Code</span></span>  
 <span data-ttu-id="aba23-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="aba23-110">This example requires:</span></span>  
  
-   <span data-ttu-id="aba23-111">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="aba23-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="aba23-112">A`NewCustomerId`函数，用于生成唯一`CustomerID`值。</span><span class="sxs-lookup"><span data-stu-id="aba23-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="aba23-113">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="aba23-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba23-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="aba23-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [<span data-ttu-id="aba23-115">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="aba23-115">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="aba23-116">在 Windows 窗体 DataGridView 控件中对新记录使用行</span><span class="sxs-lookup"><span data-stu-id="aba23-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
