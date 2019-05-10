---
title: 如何：为 Windows 窗体 DataGridView 控件中的新行指定默认值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: 879c035366c4686ceff3250a63c6ae8d8d3cfec4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651951"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e81e6-102">如何：为 Windows 窗体 DataGridView 控件中的新行指定默认值</span><span class="sxs-lookup"><span data-stu-id="e81e6-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e81e6-103">应用程序填充默认值为新添加的行时，可以进行数据输入更方便。</span><span class="sxs-lookup"><span data-stu-id="e81e6-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="e81e6-104">与<xref:System.Windows.Forms.DataGridView>类，您可以填充默认值与<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>事件。</span><span class="sxs-lookup"><span data-stu-id="e81e6-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="e81e6-105">当用户输入新记录的行时，引发此事件。</span><span class="sxs-lookup"><span data-stu-id="e81e6-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="e81e6-106">当你的代码处理此事件时，可以填充具有所选的值的所需单元格。</span><span class="sxs-lookup"><span data-stu-id="e81e6-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="e81e6-107">下面的代码示例演示如何指定默认值的新行使用<xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>事件。</span><span class="sxs-lookup"><span data-stu-id="e81e6-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e81e6-108">示例</span><span class="sxs-lookup"><span data-stu-id="e81e6-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e81e6-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="e81e6-109">Compiling the Code</span></span>  
 <span data-ttu-id="e81e6-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e81e6-110">This example requires:</span></span>  
  
- <span data-ttu-id="e81e6-111">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="e81e6-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="e81e6-112">一个`NewCustomerId`函数，用于生成唯一`CustomerID`值。</span><span class="sxs-lookup"><span data-stu-id="e81e6-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
- <span data-ttu-id="e81e6-113">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e81e6-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81e6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e81e6-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="e81e6-115">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="e81e6-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e81e6-116">在 Windows 窗体 DataGridView 控件中对新记录使用行</span><span class="sxs-lookup"><span data-stu-id="e81e6-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
