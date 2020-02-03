---
title: 数据绑定 DataGridView 控件中的自动生成列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 860e640e095537358d2f8778c810aa577e9d7ff0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746231"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="71588-102">如何：在数据绑定 Windows 窗体 DataGridView 控件中自动生成列</span><span class="sxs-lookup"><span data-stu-id="71588-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="71588-103">下面的代码示例演示如何在 <xref:System.Windows.Forms.DataGridView> 控件中显示绑定数据源中的列。</span><span class="sxs-lookup"><span data-stu-id="71588-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="71588-104">当 `true` <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 属性值（默认值）时，将为数据源表中的每个列创建一个 <xref:System.Windows.Forms.DataGridViewColumn>。</span><span class="sxs-lookup"><span data-stu-id="71588-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="71588-105">如果在设置 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 属性时 <xref:System.Windows.Forms.DataGridView> 控件已经有列，则将现有绑定列与数据源中的列进行比较，并在每次匹配时保留。</span><span class="sxs-lookup"><span data-stu-id="71588-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="71588-106">未绑定的列始终保留。</span><span class="sxs-lookup"><span data-stu-id="71588-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="71588-107">删除了数据源中没有匹配项的绑定列。</span><span class="sxs-lookup"><span data-stu-id="71588-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="71588-108">在控件中没有匹配项的数据源中的列将生成新的 <xref:System.Windows.Forms.DataGridViewColumn> 对象，这些对象将添加到 <xref:System.Windows.Forms.DataGridView.Columns%2A> 集合的末尾。</span><span class="sxs-lookup"><span data-stu-id="71588-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71588-109">示例</span><span class="sxs-lookup"><span data-stu-id="71588-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71588-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="71588-110">Compiling the Code</span></span>  
 <span data-ttu-id="71588-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="71588-111">This example requires:</span></span>  
  
- <span data-ttu-id="71588-112">名为 <xref:System.Windows.Forms.DataGridView> 的 `customersDataGridView` 控件。</span><span class="sxs-lookup"><span data-stu-id="71588-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
- <span data-ttu-id="71588-113">名为 `customersDataSet` 的 <xref:System.Data.DataSet> 对象，它具有名为 `Customers`的表。</span><span class="sxs-lookup"><span data-stu-id="71588-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
- <span data-ttu-id="71588-114">对 <xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、<xref:System.Data?displayProperty=nameWithType> 和 <xref:System.Xml?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="71588-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71588-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71588-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="71588-116">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="71588-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="71588-117">如何：从 Windows 窗体 DataGridView 控件中删除自动生成的列</span><span class="sxs-lookup"><span data-stu-id="71588-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
